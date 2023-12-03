# Testing

## *[pupilfirst link](https://www.pupilfirst.school/courses/1804/curriculum)*

### **JEST**: <https://jestjs.io/>

- installation
  
  ```bash
  npm install jest --save-dev
  ```

- create ```__tests__``` folder for tests
  - The folder will contain ```.js``` files containing tests for the application
  - every `.js` file will contain multiple ***test suites --> test cases***
- Creating a ***test suite***
  
  ```js
  describe("Test suite name", () => {
    // write your test cases here
  })
  ```

- Creating a ***test case***

  ```js
  // inside test suite
  test("Test case name", () => {
    // test your functionalities
    expect(true).toBe(true)
  })
  ```

- Run test
  - inside your package.json add script

    ```json
    "test": "jest"
    ```

  - to run

    ```bash
    npm test
    ```

### [Git Hooks](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks)

#### client-side hook (pre-commit hook)

##### Husky : <https://www.npmjs.com/package/husky>

- installation

  ```bash
  npm install husky --save-dev
  ```

- add following script to `package.json` and run it once:

  ```json
  "prepare": "husky install"
  ```

  ```bash
  npm prepare
  ```

  > Note: The `husky install` should run in the directory where `.git` folder is located.
  >Note: instead of `husky install` we can do `husky install sampleFolder/.husky` then the `.husky` folder will be created in the `sampleFolder`.

- To add pre-commit hook for testing:

  ```bash
  npx husky add .husky/pre-commit "npm test"
  ```

  >Note: if `.husky` folder is present in another folder then do `cd folder-path && npm test`

- add ***lint-staged*** for formatting the staged code  
  lint-staged : <https://www.npmjs.com/package/lint-staged>  
  prettier : <https://prettier.io/>

  - installation
  
    ```bash
    npm install lint-staged prettier --save-dev
    ```
  
  - eslint config

    ```bash
    npm init @eslint/config
    ```

  - `package.json` configuration --> add:

    ```json
    "lint-staged": {
      "*.js": [
        "eslint",
        "prettier --write ."
      ]
    }
    ```

- add pre-commit hook for lint-staged:

  ```bash
  npx husky add .husky/pre-commit "npx lint-staged"
  ```
  
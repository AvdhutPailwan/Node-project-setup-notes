# Node-project-setup-notes

## GitHub CLI to remember your login credentials

<https://github.com/cli/cli#installation>

## ESLint : <https://eslint.org/>

- install it globally by  

  ```bash
  npm install -g eslint
  ```

  - global installation means that you don't need an npm package in your project folder it installs in your system
- install ```eslint``` vscode extension
- after you initialized the npm in your project folder by:

  ```bash
  npm init
  ```

  to configure eslint do:  

  ```bash
  eslint --init
  ```

- ```.eslintrc.json``` file contains the configurations for the linting of the code
  
## NPM configurations

### Setting defaults to package.json

You can use config set commands to configure the default values that a new package.json starts with. Run the following on the terminal using YOUR NAME and YOUR EMAIL ADDRESS:

```bash
npm config set init-author-name "Jane Doe" --location=global
```

```bash
npm config set init-author-email "jane.doe@example.com" --location=global
```

You can test whether these settings have been accepted by running:

```bash
npm config ls
```

To write/change/see configurations go to ```package.json```

## Some common things which get used in javascript development

- ```fs``` module
  - used for file system operations
- ```streams```
  - used when dealing with huge data processing
    it is efficient to use streams
- ```readline``` module
  - to read input from command line
- ```minimist``` package
  - to read command line arguments

## Testing

### *[pupilfirst link](https://www.pupilfirst.school/courses/1804/curriculum)*

#### **JEST**: <https://jestjs.io/>

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

# Node-project-setup-notes

## GitHub CLI to remember your login credentials

<https://github.com/cli/cli#installation>

## ESLint

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
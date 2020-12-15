# eslint-config-labnol

ESLint and Prettier configuration for Digital Inspiration projects

## Installation

```sh
npm install --save-dev eslint-config-labnol
```

## Usage

Then add the extends to your .eslintrc.js file:

The ESLint rules go directly under "rules" while prettier options go under "prettier/prettier". Note that prettier rules overwrite anything in my config (trailing comma, and single quote), so you'll need to include those as well.

```js
module.exports = {
  extends: 'labnol',
  rules: {
    'no-debugger': 'off',
    'no-await-in-loop': 'warning',
    'prettier/prettier': [
      'error',
      {
        printWidth: 120,
        trailingComma: 'es5',
        singleQuote: true,
      },
    ],
  },
};
```

## ESlint and Prettier in VS Code

Update your VS Code settings to run the linter action on saving the file.

```json
{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "[javascript]": {
    "editor.formatOnSave": false
  },
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true,
    "source.organizeImports": true
  },
  "files.autoSave": "onFocusChange",
  "eslint.validate": ["javascript", "javascriptreact"]
}
```

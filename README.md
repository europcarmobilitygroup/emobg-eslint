# Europcar Mobility Group ECMAScript code quality setup
Library provides flexible linting (ESLint `9.x.x`) setups for JavaScript and TypeScript projects. 
It is designed to support both JavaScript and TypeScript, allowing developers to choose the configuration that best fits their needs.

## Description
Includes separate configurations for ES6 and TypeScript, pre-configured with popular ESLint rules and best practices used by Europcar Mobility Group Front-end department.

## Usage
The library offers two main configurations for `eslint.config.js`
- JavaScript only Configuration

```JS
const eslintProjectOverrides = {
  //
};

const eslintES6 = require('@emobg/eslint/config/es6.js');

module.exports = [{
  files: ["**/*.js"],
  ...eslintES6,
  rules: {
    ...eslintES6.rules,
    ...eslintProjectOverrides,
  },
  languageOptions: {
    ...eslintES6.languageOptions,
  },
}];
```

- JavaScript + TypeScript Configuration

```JS
const eslintProjectOverrides = {
  //
};

const eslintES6 = require('@emobg/eslint/config/es6.js');
const eslintTS = require('@emobg/eslint/config/ts.js');

module.exports = [{
  files: ["**/*.ts"],
  ignores: ["**/*.d.ts",],
  ...eslintES6,
  ...eslintTS,
  plugins: { ...eslintTS.plugins },
  rules: {
    ...eslintES6.rules,
    ...eslintTS.rules,
    ...eslintProjectOverrides,
  },
  languageOptions: {
    ...eslintES6.languageOptions,
    ...eslintTS.languageOptions,
  },
}];
```

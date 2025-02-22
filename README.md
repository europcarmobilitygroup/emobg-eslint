# Europcar Mobility Group ECMAScript code quality setup
Library provides flexible linting (ESLint `9.x.x`) configuration for front-end projects. 
It is designed to support both JavaScript and TypeScript, allowing developers to choose the configuration that best fits their needs.

## Usage
The library offers two main configurations for `eslint.config.js`
- JavaScript only Configuration

```JS
const eslintProjectOverrides = {
  //
};

const { eslintES6 } = require('@emobg/eslint');

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

const { eslintES6, eslintTS } = require('@emobg/eslint');

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

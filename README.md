# Europcar Mobility Group ECMAScript code quality setup
ESLint `9.x.x` configuration for ES6 & TypeScript standardising code quality

## Description
A reusable and customizable ESLint configuration package.
Includes separate configurations for ES6 and TypeScript, pre-configured with popular ESLint rules and best practices used by Europcar Mobility Group Front-end department.

## Usage
eslint.config.js

```
  const eslintProjectOverrides = {
  //
  };

  const eslintES6 = require('@emobg/eslint/configs/es6.config.js');
  const eslintTS = require('@emobg/eslint/configs/ts.config.js');

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
---
title: Migration guide - Switch from TSLint to ESLint
description: Use this guide to migrate the project from TSLint to ESLint.
last_updated: Mar 24, 2023
template: module-migration-guide-template
---

This document provides instructions for migrating from TSLint to ESLint in your Spryker project.

## Overview

TSLint support was discontinued as of December 1, 2020. The solution is migration to ESLint as the default linter for TypeScript and JavaScript.

*Estimated migration time: 1h*

## 1) Update dependencies

1. In `package.json`: 
    - Add or update the following dependencies to the new version:

      ```json
      {
          "@spryker/frontend-config.eslint": "~0.1.0",
          "@typescript-eslint/eslint-plugin": "~5.54.0",
          "@typescript-eslint/parser": "~5.54.0",
          "eslint": "~8.35.0",
          "prettier": "~2.8.4"
      }
      ```

    - Remove the following dependencies:

        ```json
        {
            "@spryker/frontend-config.tslint": "x.x.x",
            "tslint": "x.x.x"
        }
        ```
     
    - Update the following commands:

        ```json
        {
            "yves:tslint": "node ./frontend/libs/tslint",
            "yves:tslint:fix": "node ./frontend/libs/tslint --fix"
        }
        ```
      
        Must be

        ```json
        {
            "yves:lint": "eslint --no-error-on-unmatched-pattern ./src/Pyz/Yves/**/Theme/**/*.{js,ts}",
            "yves:lint:fix": "eslint --no-error-on-unmatched-pattern --fix ./src/Pyz/Yves/**/Theme/**/*.{js,ts}"
        }
        ```

2. Update and install package dependencies:

```bash
rm -rf node_modules
npm install
```

{% info_block warningBox "Verification" %}

Ensure that the `package-lock.json` file and the `node_modules` folder have been updated.

{% endinfo_block %}

## 2) Create or update configuration files

1. Create `.eslintrc.json` file:

```json
{
    "root": true,
    "extends": ["./node_modules/@spryker/frontend-config.eslint/.eslintrc.js", "plugin:@typescript-eslint/recommended"],
    "parser": "@typescript-eslint/parser",
    "parserOptions": {
        "ecmaVersion": 2020,
        "sourceType": "module",
        "project": "./tsconfig.yves.json"
    },
    "plugins": ["deprecation"],
    "ignorePatterns": [
        "docker/",
        "public/*/assets/",
        "**/dist/",
        "**/node_modules/",
        "vendor/",
        "src/Pyz/Zed/*/Presentation/Components/"
    ],
    "rules": {
        "accessor-pairs": ["error", { "setWithoutGet": true, "enforceForClassMembers": false }],
        "@typescript-eslint/no-empty-function": ["error", { "allow": ["methods"] }],
        "@typescript-eslint/no-magic-numbers": [
            "error",
            {
                "ignore": [-1, 0, 1],
                "ignoreDefaultValues": true,
                "ignoreClassFieldInitialValues": true,
                "ignoreArrayIndexes": true,
                "ignoreEnums": true,
                "ignoreReadonlyClassProperties": true
            }
        ],
        "deprecation/deprecation": "warn"
    }
}
```

2. If the project uses CI, adjust `.github/workflows/ci.yml`:

```yaml
jobs:
  #...
  validation:
    #...
    steps:
      #...
      - name: TS lint
        run: node ./frontend/libs/tslint --format stylish
      # Must be
      - name: ES lint
        run: npm run yves:lint
```

## 3) Remove unnecessary files

1. `.eslintrc.js`
2. `tslint.json`
3. `frontend/libs/tslint.js`

## 4) Check project `.js` and `.ts` files

- Check all project `.js` and `.ts` files for `tslint:` comments and replace them with `eslint-` if they are still relevant.
- Execute the `npm run yves:lint` command and check result.

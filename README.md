# Pocket Lint Cheat Sheet:

*These package/linter dependency versions might not be the most recent, so remember to update your package.json!*

---

## Config Settings
### [Non-Typescript](https://github.com/ryee-dev/pocket-lint/tree/master/non-typescript)
### [Typescript](https://github.com/ryee-dev/pocket-lint/tree/master/typescript)

### package.json

<table>
    <tr>
        <th>
            <strong>Typescript</strong>
        </th>
        <th>
            <strong>Non-typescript</strong>
        </th>
    </tr>
    <tr>
        <td>
            <pre>
{
  "dependencies": {
    "react": "@latest",
    "react-dom": "@latest",
    "react-scripts-ts": "@latest",
  },
  "devDependencies": {
    "@types/jest": "@latest",
    "@types/node": "@latest",
    "@types/react": "@latest",
    "@types/react-dom": "@latest",
    "prettier": "@latest",
    "stylelint": "@latest",
    "stylelint-config-prettier": "@latest",
    "stylelint-config-recommended": "@latest",
    "stylelint-config-styled-components": "@latest",
    "stylelint-processor-styled-components": "@latest",
    "tslint-config-airbnb": "@latest",
    "tslint-config-prettier": "@latest",
    "tslint-plugin-prettier": "@latest",
    "tslint-react": "@latest",
    "typescript": "@latest"
  }
}
            </pre>
        </td>
        <td>
            <pre>
{
  "dependencies": {
    "react": "@latest",
    "react-dom": "@latest",
    "react-scripts": "@latest"
  },
  "devDependencies": {
    "eslint": "@latest",
    "eslint-config-airbnb": "@latest",
    "eslint-config-prettier": "@latest",
    "eslint-plugin-import": "@latest",
    "eslint-plugin-jsx-a11y": "@latest",
    "eslint-plugin-prettier": "@latest",
    "eslint-plugin-react": "@latest",
    "prettier": "@latest",
    "stylelint": "@latest",
    "stylelint-config-prettier": "@latest",
    "stylelint-config-recommended": "@latest",
    "stylelint-config-styled-components": "@latest",
    "stylelint-processor-styled-components": "@latest",
  }
}
            </pre>
        </td>
    </tr>
</table>

## eslint/tslint

<table>
    <tr>
        <th>
            <strong>tslint.json</strong>
        </th>
        <th>
            <strong>.eslintrc</strong>
        </th>
    </tr>
    <tr>
        <td>
            <pre>
{
  "extends": ["tslint:recommended", "tslint-react"],
  "rules": {
    "arrow-parens": false,
    "arrow-return-shorthand": [false],
    "comment-format": [true, "check-space"],
    "import-blacklist": [true, "rxjs"],
    "interface-over-type-literal": false,
    "interface-name": false,
    "max-line-length": [true, 120],
    "member-access": false,
    "member-ordering": [true, { "order": "fields-first" }],
    "newline-before-return": false,
    "no-any": false,
    "no-empty-interface": false,
    "no-import-side-effect": [true],
    "no-inferrable-types": [true, "ignore-params", "ignore-properties"],
    "no-invalid-this": [true, "check-function-in-method"],
    "no-null-keyword": false,
    "no-require-imports": false,
    "no-submodule-imports": [true, "@src", "rxjs"],
    "no-this-assignment": [true, { "allow-destructuring": true }],
    "no-trailing-whitespace": true,
    "no-unused-variable": [true, "react"],
    "object-literal-sort-keys": false,
    "object-literal-shorthand": false,
    "one-variable-per-declaration": [false],
    "only-arrow-functions": [true, "allow-declarations"],
    "ordered-imports": [false],
    "prefer-method-signature": false,
    "prefer-template": [true, "allow-single-concat"],
    "quotemark": [true, "single", "jsx-double"],
    "semicolon": [true, "always"],
    "trailing-comma": [true, {
      "singleline": "never",
      "multiline": {
        "objects": "always",
        "arrays": "always",
        "functions": "never",
        "typeLiterals": "ignore"
      },
      "esSpecCompliant": true
    }],
    "triple-equals": [true, "allow-null-check"],
    "type-literal-delimiter": true,
    "typedef": [true,"parameter", "property-declaration"],
    "variable-name": [true, "ban-keywords", "check-format", "allow-pascal-case", "allow-leading-underscore"],
    // tslint-react
    "jsx-no-lambda": false
  }
}
            </pre>
        </td>
        <td>
            <pre>
{
  "root": true,
  "extends": ["airbnb", "plugin:prettier/recommended", "prettier/react"],
  "env": {
    "browser": true
  },
  "rules": {
    "no-unused-expressions": ["error", {
      "allowTaggedTemplates": true
    }],
    "react/jsx-filename-extension": [1, {
      "extensions": [".js", ".jsx"]
    }],
    "semi": ["error", "always"],
    "react/prop-types": 0
  }
}
            </pre>
        </td>
    </tr>
</table>

## additional linter settings

<table>
    <tr>
        <th>
            <strong>.prettierrc</strong>
        </th>
        <th>
            <strong>.stylelintrc</strong>
        </th>
        <th>
            <strong>tsconfig.json</strong>
    </tr>
    <tr>
        <td>
            <pre>
{
  "printWidth": 80,
  "semi": true,
  "singleQuote": true,
  "trailingComma": "all"
}
            </pre>
        </td>
        <td>
            <pre>
{
  "processors": ["stylelint-processor-styled-components"],
  "extends": [
    "stylelint-config-recommended",
    "stylelint-config-styled-components",
    "stylelint-config-prettier"
  ]
}
            </pre>
        </td>
        <td>
            <pre>
              {
  "compilerOptions": {
    "baseUrl": ".",
    "outDir": "build/dist",
    "module": "esnext",
    "target": "es5",
    "lib": ["es6", "dom", "esnext.asynciterable"],
    "sourceMap": true,
    "allowJs": true,
    "jsx": "react",
    "moduleResolution": "node",
    "rootDir": "src",
    "forceConsistentCasingInFileNames": true,
    "noImplicitReturns": true,
    "noImplicitThis": true,
    "noImplicitAny": true,
    "strictNullChecks": true,
    "suppressImplicitAnyIndexErrors": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "plugins": [{
      "name": "typescript-styled-plugin"
    }],
    "paths": {
      "~/*": ["*"]
    }
  },
  "exclude": [
    "node_modules",
    "build",
    "scripts",
    "acceptance-tests",
    "webpack",
    "jest",
    "src/setupTests.ts"
  ]
}
            </pre>
        </td>
    </tr>
</table>
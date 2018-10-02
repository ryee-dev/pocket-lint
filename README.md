# Pocket Lint Cheat Sheet:

# [Typescript](https://github.com/ryee-dev/pocket-lint/tree/master/typescript) | [Non-Typescript](https://github.com/ryee-dev/pocket-lint/tree/master/non-typescript)

---


## Typescript Project Config

### package.json
*(These package/linter dependency versions might not be the most recent, so remember to update your dependencies!)*

Check which dependencies are out-of-date using: `yarn upgrade-interactive`

```json
{
  "name": "tslint-eslint-crats",
  "version": "0.1.0",
  "private": true,
  "license": "MIT",
  "dependencies": {
    "react": "16.5.2",
    "react-dom": "16.5.2",
    "react-scripts-ts": "3.1.0"
  },
  "scripts": {
    "build": "react-scripts-ts build",
    "eject": "react-scripts-ts eject",
    "start": "react-scripts-ts start",
    "test": "react-scripts-ts test --env=jsdom"
  },
  "devDependencies": {
    "@types/jest": "23.3.2",
    "@types/node": "10.11.3",
    "@types/react": "16.4.14",
    "@types/react-dom": "16.0.8",
    "eslint": "5.6.1",
    "eslint-config-airbnb": "17.1.0",
    "eslint-config-prettier": "3.1.0",
    "eslint-plugin-import": "2.14.0",
    "eslint-plugin-jest": "21.24.0",
    "eslint-plugin-jsx-a11y": "6.1.1",
    "eslint-plugin-prettier": "2.7.0",
    "eslint-plugin-react": "7.11.1",
    "eslint-plugin-typescript": "0.12.0",
    "eslint-plugin-unicorn": "6.0.1",
    "prettier": "1.14.3",
    "tslint": "5.11.0",
    "tslint-config-airbnb": "5.11.0",
    "tslint-config-prettier": "1.15.0",
    "tslint-plugin-prettier": "2.0.0",
    "typescript": "3.1.1",
    "typescript-eslint-parser": "19.0.2"
  }
}

```

`yarn add -D eslint eslint-config-airbnb eslint-config-prettier eslint-plugin-import eslint-plugin-jest eslint-plugin-jsx-a11y eslint-plugin-prettier eslint-plugin-react eslint-plugin-typescript eslint-plugin-unicorn prettier tslint tslint-config-airbnb tslint-config-prettier tslint-plugin-prettier typescript-eslint-parser stylelint stylelint-config-prettier stylelint-config-recommended stylelint-config-styled-components stylelint-processor-styled-components tslib`

### tsconfig.json
```json
{
  "compilerOptions": {
    "outDir": "build/lib",
    "module": "commonjs",
    "target": "es5",
    "lib": ["es5", "es6", "es7", "es2017", "dom"],
    "sourceMap": true,
    "allowJs": false,
    "jsx": "react",
    "moduleResolution": "node",
    "rootDir": "src",
    "baseUrl": "src",
    "forceConsistentCasingInFileNames": true,
    "noImplicitReturns": true,
    "noImplicitThis": true,
    "noImplicitAny": true,
    "strictNullChecks": true,
    "suppressImplicitAnyIndexErrors": true,
    "noUnusedLocals": true,
    "declaration": true,
    "allowSyntheticDefaultImports": true,
    "experimentalDecorators": true
  },
  "include": ["src/**/*"],
  "exclude": ["node_modules", "build", "scripts"]
}
```

or

```json
{
  "compilerOptions": {
    "baseUrl": "./", // enables project relative paths config
    "paths": { // define paths mappings
      "@src/*": ["src/*"] // will enable -> import { ... } from '@src/components'
      // in webpack you need to add -> resolve: { alias: { '@src': PATH_TO_SRC } }
    },
    "outDir": "dist/", // target for compiled files
    "allowSyntheticDefaultImports": true, // no errors with commonjs modules interop
    "esModuleInterop": true,
    "allowJs": true, // include js files
    "checkJs": true, // typecheck js files
    "declaration": false, // don't emit declarations
    "emitDecoratorMetadata": true,
    "experimentalDecorators": true,
    "forceConsistentCasingInFileNames": true,
    "importHelpers": true, // importing helper functions from tslib
    "noEmitHelpers": true, // disable emitting inline helper functions
    "jsx": "react", // process JSX
    "lib": [
      "dom",
      "es2016",
      "es2017.object"
    ],
    "target": "es5", // "es2015" for ES6+ engines
    "module": "commonjs", // "es2015" for tree-shaking
    "moduleResolution": "node",
    "noEmitOnError": true,
    "noFallthroughCasesInSwitch": true,
    "noImplicitAny": true,
    "noImplicitReturns": true,
    "noImplicitThis": true,
    "noUnusedLocals": true,
    "strict": true,
    "pretty": true,
    "removeComments": true,
    "sourceMap": true
  },
  "include": [
    "src/**/*"
  ],
  "exclude": [
    "node_modules",
    "src/**/*.spec.*"
  ]
}
```

### tslint.json

```json
{
  "rulesDirectory": ["tslint-plugin-prettier"],
  "extends": [
    "tslint:recommended",
    "tslint-config-airbnb",
    "tslint-react",
    "tslint-config-prettier"
  ],
  "linterOptions": {
    "exclude": ["config/**/*.js", "node_modules/**/*.ts"]
  },
  "rules": {
    "prettier": true
  }
}
```

### .eslintrc

```json
{
  "extends": [
    "airbnb",
    "prettier",
    "prettier/react",
    "plugin:prettier/recommended",
    "plugin:jest/recommended",
    "plugin:unicorn/recommended"
  ],
  "plugins": ["prettier", "jest", "unicorn"],
  "parserOptions": {
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "env": {
    "es6": true,
    "browser": true,
    "jest": true
  },
  "rules": {
    "react/jsx-filename-extension": "off",
    "unicorn/filename-case": "off",
    "import/extensions": { "ts": "never", "tsx": "never" },
    "no-use-before-define": "warn",
    "no-param-reassign": "warn"
  },
  "settings": {
    "import/resolver": {
      "node": {
        "extensions": [".js", ".jsx", ".ts", ".tsx"]
      }
    }
  },
  "overrides": [
    {
      "files": ["**/*.ts", "**/*.tsx"],
      "parser": "typescript-eslint-parser",
      "rules": {
        "no-undef": "off"
      }
    }
  ]
}
```

### .prettierrc

```json
{
  "printWidth": 80,
  "tabWidth": 2,
  "useTabs": false,
  "semi": true,
  "singleQuote": true,
  "trailingComma": "none",
  "bracketSpacing": true,
  "jsxBracketSameLine": false
}
```

### .stylelintrc

```json
{
  "processors": ["stylelint-processor-styled-components"],
  "extends": [
    "stylelint-config-recommended",
    "stylelint-config-styled-components",
    "stylelint-config-prettier"
  ]
}
```

---

## Non-Typescript Project Config

### Dependencies

`yarn add -D eslint eslint-config-airbnb eslint-config-prettier eslint-plugin-import eslint-plugin-jest eslint-plugin-jsx-a11y eslint-plugin-prettier eslint-plugin-react eslint-plugin-unicorn prettier stylelint stylelint-config-prettier stylelint-config-recommended stylelint-config-styled-components stylelint-processor-styled-components`

### .eslintrc

```json
{
  "extends": [
    "airbnb",
    "prettier",
    "prettier/react",
    "plugin:prettier/recommended",
    "plugin:jest/recommended",
    "plugin:unicorn/recommended"
  ],
  "plugins": ["react", "prettier", "jest", "unicorn"],
  "parserOptions": {
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "env": {
    "es6": true,
    "node": true,
    "browser": true,
    "jest": true
  },
  "rules": {
    "react/jsx-filename-extension": "off",
    "unicorn/filename-case": "off",
    "import/extensions": { "js": "never", "jsx": "never" },
    "no-use-before-define": "warn",
    "no-param-reassign": "warn"
  },
  "settings": {
    "import/resolver": {
      "node": {
        "extensions": [".js", ".jsx"]
      }
    }
  }
}
```

### .prettierrc

```json
{
  "printWidth": 80,
  "tabWidth": 2,
  "useTabs": false,
  "semi": true,
  "singleQuote": true,
  "trailingComma": "none",
  "bracketSpacing": true,
  "jsxBracketSameLine": false
}
```

### .stylelintrc

```json
{
  "processors": ["stylelint-processor-styled-components"],
  "extends": [
    "stylelint-config-recommended",
    "stylelint-config-styled-components",
    "stylelint-config-prettier"
  ]
}
```

## Sources

- https://github.com/azdanov/tslint-eslint-crats
- https://github.com/styled-components/stylelint-processor-styled-components
- https://github.com/sw-yx/react-typescript-cheatsheet
- https://github.com/piotrwitek/react-redux-typescript-guide


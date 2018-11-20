# Pocket Lint Cheat Sheet:

# [Typescript](https://github.com/ryee-dev/pocket-lint/tree/master/typescript) | [Non-Typescript](https://github.com/ryee-dev/pocket-lint/tree/master/non-typescript)

---


## Typescript Project Config

### package.json
*(These package/linter dependency versions might not be the most recent, so remember to update your dependencies!)*

Check which dependencies are out-of-date using: `yarn upgrade-interactive`

---

### Dependencies to add

`yarn add -D eslint-config-airbnb eslint-config-prettier eslint-plugin-import eslint-plugin-jest eslint-plugin-jsx-a11y eslint-plugin-prettier eslint-plugin-react eslint-plugin-typescript eslint-plugin-unicorn prettier tslint tslint-config-airbnb tslint-config-prettier tslint-plugin-prettier typescript-eslint-parser stylelint stylelint-config-prettier stylelint-config-recommended stylelint-config-styled-components stylelint-processor-styled-components tslib`

---

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
    "baseUrl": "./",
    "paths": { 
      "@src/*": ["src/*"] 
    },
    "outDir": "dist/",
    "allowSyntheticDefaultImports": true,
    "esModuleInterop": true,
    "allowJs": true,
    "checkJs": true,
    "declaration": false,
    "emitDecoratorMetadata": true,
    "experimentalDecorators": true,
    "forceConsistentCasingInFileNames": true,
    "importHelpers": true, 
    "noEmitHelpers": true,
    "jsx": "react", 
    "lib": [
      "dom",
      "es2016",
      "es2017.object"
    ],
    "target": "es5", 
    "module": "commonjs", 
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

---

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

---

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

---

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

---

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
---


## Non-Typescript Project Config

### Dependencies

`yarn add -D eslint eslint-config-airbnb eslint-config-prettier eslint-plugin-import eslint-plugin-jest eslint-plugin-jsx-a11y eslint-plugin-prettier eslint-plugin-react eslint-plugin-unicorn prettier stylelint stylelint-config-prettier stylelint-config-recommended stylelint-config-styled-components stylelint-processor-styled-components`

---

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

---

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

---

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

## A HUGE thanks to the following resources

- https://github.com/azdanov/tslint-eslint-crats
- https://github.com/styled-components/stylelint-processor-styled-components
- https://github.com/sw-yx/react-typescript-cheatsheet
- https://github.com/piotrwitek/react-redux-typescript-guide
- https://piotrwitek.github.io/react-redux-typescript-guide/
- https://levelup.gitconnected.com/ultimate-react-component-patterns-with-typescript-2-8-82990c516935
- https://charleslbryant.gitbooks.io/hello-react-and-typescript/content/DefinePropsAndStateTypes.html

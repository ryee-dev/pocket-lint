# Typescript Project Config

### Dependencies to add

`yarn add -D tslint tslint-config-airbnb tslint-config-prettier tslint-plugin-prettier eslint-config-prettier eslint-plugin-react-hooks @typescript-eslint/parser @typescript-eslint/eslint-plugin prettier stylelint stylelint-config-prettier stylelint-config-recommended stylelint-config-styled-components stylelint-processor-styled-components`

---

## recommended configs

### tsconfig.json

```json
{
  "compilerOptions": {
    "target": "esnext",
    "module": "esnext",
    "lib": ["dom", "es6", "es2017", "esnext"],
    "sourceMap": true,
    "outDir": "build/",
    "moduleResolution": "node",
    "declaration": false,
    "composite": false,
    "strict": true,
    "noImplicitAny": true,
    "strictNullChecks": true,
    "strictFunctionTypes": true,
    "noImplicitThis": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "noImplicitReturns": true,
    "noFallthroughCasesInSwitch": true,
    "allowSyntheticDefaultImports": true,
    "esModuleInterop": true,
    "newLine": "LF",

    "experimentalDecorators": true,
    "skipLibCheck": true,

    "allowJs": false,
    "jsx": "react",
    "rootDir": "src",
    "baseUrl": "src",
    "forceConsistentCasingInFileNames": true,
    "suppressImplicitAnyIndexErrors": true,
    "paths": {
      "*": ["src/*", "node_modules/*"]
    }
  },
  "include": ["src/**/*"],
  "exclude": ["node_modules", "build", "dist", "scripts"]
}
```

---

### .eslintrc

```json
{
  "extends": [
    "plugin:@typescript-eslint/recommended",
    "airbnb",
    "prettier",
    "prettier/@typescript-eslint",
    "prettier/react",
    "plugin:prettier/recommended",
    "plugin:jest/recommended",
    "plugin:unicorn/recommended"
  ],
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaFeatures": {
      "jsx": false
    },
    "project": "./tsconfig.json"
  },
  "plugins": [
    "@typescript-eslint",
    "@typescript-eslint/tslint",
    "prettier",
    "jest",
    "unicorn"
  ],
  "env": {
    "node": true,
    "es6": true,
    "browser": true,
    "jest": true
  },
  "rules": {
    "@typescript-eslint/class-name-casing": "warn",
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
  "trailingComma": "es5",
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

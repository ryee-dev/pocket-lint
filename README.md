# Pocket Lint Cheat Sheet:

### non-typescript

###### package.json
```json
{
  "dependencies": {
    "babel-plugin-styled-components": "1.7.1",
    "styled-components": "^3.4.9"
  },
  "devDependencies": {
    "eslint": "^5.6.0",
    "eslint-config-airbnb": "^17.1.0",
    "eslint-config-prettier": "^3.0.1",
    "eslint-plugin-import": "^2.14.0",
    "eslint-plugin-jsx-a11y": "^6.1.1",
    "eslint-plugin-prettier": "^2.6.2",
    "eslint-plugin-react": "^7.11.1",
    "prettier": "^1.14.2",
    "stylelint": "^9.5.0",
    "stylelint-config-prettier": "^4.0.0",
    "stylelint-config-recommended": "^2.1.0",
    "stylelint-config-styled-components": "^0.1.1",
    "stylelint-processor-styled-components": "^1.3.2",
  }
}

```

###### .eslintrc.json
```json
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
```
---
### typescript

###### package.json
```json
{
  "dependencies": {
    "react-scripts-ts": "2.17.0",
    "styled-components": "^3.4.9"
  },
  "devDependencies": {
    "@types/react-router-dom": "^4.3.1",
    "@types/jest": "^23.3.2",
    "@types/node": "^10.9.4",
    "@types/react": "^16.4.14",
    "@types/react-dom": "^16.0.7",
    "prettier": "^1.4.0-beta",
    "tslint-config-airbnb": "^5.11.0",
    "tslint-config-prettier": "^1.15.0",
    "tslint-plugin-prettier": "^1.3.0",
    "tslint-react": "^3.6.0",
    "typescript": "^3.1.0-dev.20180914"
  }
}
```

###### tslint.json
```json
{
  "extends": ["tslint:latest", "tslint-react", "tslint-config-prettier"],
  "linterOptions": {
    "exclude": [
      "config/**/*.js",
      "node_modules/**/*.ts",
      "coverage/lcov-report/*.js"
    ]
  },
  "rules": {
    "ordered-imports": false,
    "object-literal-sort-keys": false,
    "interface-name": false,
    "member-ordering": false,
    "no-console": false
  }
}
```

###### tsconfig.json
```json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "~/*": ["*"]
    },
    "outDir": "build/dist",
    "module": "esnext",
    "target": "es5",
    "lib": ["es6", "dom"],
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
    "noUnusedLocals": true
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
```

### additional

###### .prettierrc
```
{
  "printWidth": 80,
  "semi": true,
  "singleQuote": true,
  "trailingComma": "es5"
}
```

###### .stylelintrc.json
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

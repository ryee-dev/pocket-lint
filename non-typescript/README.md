# non-typescript

## package.json

```json
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
```

## .eslintrc.json

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

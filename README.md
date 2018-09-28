# Pocket Lint Cheat Sheet:

*These package/linter dependency versions might not be the most recent, so remember to update your package.json!*

---

## Config Settings
### [Non-Typescript](https://github.com/ryee-dev/pocket-lint/tree/master/non-typescript)
### [Typescript](https://github.com/ryee-dev/pocket-lint/tree/master/typescript)

---

## additional linter settings

### .prettierrc

```json
{
  "printWidth": 80,
  "semi": true,
  "singleQuote": true,
  "trailingComma": "all"
}
```

### .stylelintrc.json

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

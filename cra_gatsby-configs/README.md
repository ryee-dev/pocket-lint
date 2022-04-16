# Configs for **CRA**

## **Standard**

*Install prerequisite dependencies*:
> `pnpm -D add @emotion/eslint-plugin @typescript-eslint/parser
@typescript-eslint/eslint-plugin eslint-config-xo-react eslint-plugin-react eslint-plugin-no-use-extend-native eslint-plugin-ava eslint-plugin-unicorn eslint-plugin-promise eslint-plugin-import eslint-plugin-react-hooks eslint-config-prettier stylelint stylelint-config-standard`

---

`.eslintrc`

```json
{
  "extends": [
    "eslint:recommended",
    "plugin:react/recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:@typescript-eslint/recommended-requiring-type-checking"
  ]
}
``` 

## **Using XO**

*Install the following **in addition** to **standard** deps*:

> `pnpm -D add eslint-config-xo eslint-config-xo-react eslint-config-xo-typescript`

---

`.eslintrc`

```json
{
  "extends": [
    "eslint:recommended",
    "plugin:react/recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:@typescript-eslint/recommended-requiring-type-checking",
    "xo",
    "xo-react/space",
    "xo-typescript/space"
  ]
}
```

# Configs for **Next.js**

*Install prerequisite dependencies*:
> `pnpm -D add @emotion/eslint-plugin @typescript-eslint/parser
@typescript-eslint/eslint-plugin eslint-config-next eslint-config-xo-react eslint-plugin-react eslint-plugin-no-use-extend-native eslint-plugin-ava eslint-plugin-unicorn eslint-plugin-promise eslint-plugin-import eslint-plugin-react-hooks eslint-config-prettier  stylelint stylelint-config-standard`

---

`.eslintrc`

*Include the following if using Next.js*

*(deps should already come pre-installed with next app)*

```json
{
  "extends": [
    "plugin:@next/next/recommended",
    "next",
    "next/core-web-vitals"
  ]
}
```

# ESLint

## Конфигурация

> - [Раздел документации ESLint с описанием принципов конфигурации](https://eslint.org/docs/user-guide/configuring)

### Конфигурация правил

> - [Раздел документации с описанием конфигурации правил](https://eslint.org/docs/user-guide/configuring#configuring-rules)

Изменить конфигурацию правил можно в файле конфигурации или комментариями в коде. Правилам могут соответствовать значения:

- `off` или `0` - правило не учитывается
- `warn` или `1` - срабатывание правила учитывается как warning (не влияет на exit code)
- `error` или `2` - срабатывание правила учитывается как error (завершается с exit code 1)

### Пример конфигурации

```json
/* .eslintrc.json */

{
  "env": {
    "browser": true,
    "es6": true
  },
  "extends": [
    "eslint:recommended",
    "airbnb",
    "plugin:@typescript-eslint/eslint-recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:prettier/recommended"
  ],
  "parserOptions": {
    "ecmaVersion": 2018
  },
  "rules": {
    "import/no-extraneous-dependencies": "off",
    "react/jsx-filename-extension": [
      "error",
      {
        "extensions": [".jsx", ".tsx"]
      }
    ],
    "prettier/prettier": "warn"
  }
}
```

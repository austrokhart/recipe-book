# ESLint

## Интеграция с Typescript

> - [Раздел документации `@typescript-eslint/eslint-plugin` c описанием интеграции](https://github.com/typescript-eslint/typescript-eslint/tree/master/packages/eslint-plugin#recommended-configs)

Для линтинга кода Typescript в ESLint необходимо добавить в проект пакеты `typescript`, `@typescript-eslint/eslint-plugin` и изменить конфигурацию ESLint.

Для добавления в проект необходимо выполнить:

```sh
yarn add --dev typescript @typescript-eslint/eslint-plugin
```

Пример конфигурации:

```json
/* .eslintrc.json */

{
  "extends": [
    "eslint:recommended",
    "plugin:@typescript-eslint/eslint-recommended",
    "plugin:@typescript-eslint/recommended"
  ]
}
```

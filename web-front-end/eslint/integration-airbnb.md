# ESLint

## Интеграция пресета от Airbnb

> - [Раздел документации `eslint-config-airbnb` с описанием установки](https://github.com/airbnb/javascript/tree/master/packages/eslint-config-airbnb#eslint-config-airbnb-1)

Для интеграции пресета от Airbnb необходимо установить пакет `eslint-config-airbnb`, его peer dependencies и изменить файл конфигурации ESLint.

Для добавления в проект необходимо выполнить:

```sh
npx install-peerdeps --dev eslint-config-airbnb
```

Пример конфигурации:

```json
/* .eslintrc.json */

{
  "extends": [
    "eslint:recommended",
    "airbnb"
  ]
}
```

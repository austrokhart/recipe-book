# ESLint

## Интеграция с React

> - [Раздел документации `eslint-plugin-react` с описанием установки](https://github.com/yannickcr/eslint-plugin-react#installation)
> - [Раздел документации `eslint-plugin-react-hooks` с описанием установки](https://github.com/facebook/react/tree/master/packages/eslint-plugin-react-hooks#installation)
> - [Раздел документации `eslint-plugin-jsx-a11y` с описанием установки](https://github.com/dequelabs/eslint-plugin-jsx-a11y#installation)

Для линтинга кода React в ESLint необходимо добавить в проект пакеты `eslint-plugin-react`, `eslint-plugin-react-hooks`, `eslint-plugin-jsx-a11y` и изменить файл конфигурации ESLint.

Можно сделать это двумя способами.

### Airbnb

Пакет `esling-config-airbnb` содержит конфигурацию, которая включает обращение к перечисленным пакетам и требует их в списке peer dependencies.

[Интеграция пресета от Airbnb в ESLint](integration-airbnb.md)

### Вручную

Для добавления в проект необходимо выполнить:

```sh
yarn add --dev eslint-plugin-react eslint-plugin-react-hooks eslint-plugin-jsx-a11y
```

Пример конфигурации:

```json
{
  "extends": [
    "eslint:recommended",
    "plugin:react/recommended",
    "plugin:react-hooks/recommended",
    "plugin:jsx-a11y/recommended",
  ]
}
```

## Примечания

При использовании Typescript необходимо задать правило:

```json
{
  "rules": {
    "react/jsx-filename-extension": [
      "error",
      {
        "extensions": [".js", ".jsx", ".ts", ".tsx"]
      }
    ]
  }
}
```

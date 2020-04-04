# Babel

## Транспиляция кода React

> - [Раздел документации Babel с описанием пакета `@babel/preset-react`](https://babeljs.io/docs/en/babel-preset-react)

Для транспиляции кода React необходимо добавить в проект пакет `@babel/preset-react` и изменить конфигурацию Babel.

Для добавления в проект необходимо выполнить:

```sh
yarn add --dev @babel/preset-react
```

Пример конфигурации:

```json
{
  "presets": [
    "@babel/env",
    "@babel/preset-react",
  ]
}
```

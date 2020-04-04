# Babel

## Транспиляция кода Typescript

> - [Раздел документации Babel с описанием пакета `@babel/preset-typescript`](https://babeljs.io/docs/en/babel-preset-typescript)

Для транспиляции кода Typescript необходимо добавить в проект пакет `@babel/preset-typescript` и изменить конфигурацию Babel.

Для добавления в проект необходимо выполнить:

```sh
yarn add --dev @babel/preset-typescript
```

Пример конфигурации:

```json
{
  "presets": [
    "@babel/env",
    "@babel/preset-typescript",
  ]
}
```

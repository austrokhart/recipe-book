# Webpack

## Интеграция с Babel

> - [раздел документации Webpack с описанием интеграции](https://webpack.js.org/loaders/babel-loader/)

### Порядок

1) Добавление в проект
2) Изменение файла конфигурации Webpack

### Добавление в проект

> - [раздел документации Babel с описанием @babel/core](https://babeljs.io/docs/en/next/babel-core.html)
> - [раздел документации Babel с описанием @babel/preset-env](https://babeljs.io/docs/en/next/babel-core.html)

Для интеграции с Babel потребуются несколько пакетов:

- пакет `@babel/core` содержит ядро Babel
- пакет `@babel/preset-env` содержит популярный пресет
- пакет `babel-loader` содержит лоадер для Webpack, который позволяет выполнять транспиляцию кода с помощью Babel

Для добавления в проект необходимо выполнить:

```sh
yarn add --dev babel-loader @babel/core @babel/preset-env

# если в проекте используется @babel/plugin-transform-runtime
yarn add --dev babel-loader @babel/core @babel/preset-env @babel/plugin-transform-runtime
```

### Изменение файла конфигурации Webpack

Необходимо изменить файл конфигурации Webpack и добавить `babel-loader` в список модулей.

Пример конфигурации:

```ts
/* webpack.config.ts */

{
  module: {
    rules: [
      {
        test: /(\.jsx?|\.tsx?)$/,
        exclude: /node_modules/,
        use: {
          loader: 'babel-loader',
          options: {
            presets: ['@babel/preset-env'],
            plugins: ['@babel/plugin-transform-runtime'],
          },
        },
      },
    ],
  },
}
```

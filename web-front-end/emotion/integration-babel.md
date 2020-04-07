# Emotion

## Интеграция с Babel

> - [Раздел документации Emotion с описанием особенностей плагина для Babel](https://emotion.sh/docs/babel)
> - [Раздел документации Emotion с описанием пакета `babel-plugin-emotion`](https://emotion.sh/docs/babel-plugin-emotion)
> - [Раздел документации Emotion с описанием пакета `@emotion/babel-preset-css-prop`](https://emotion.sh/docs/@emotion/babel-preset-css-prop)

Пакеты `babel-plugin-emotion`, `@emotion/babel-preset-css-prop` позволяют расширить возможности Emotion.

Краткий список расширенных возможностей:

- использование компонентов как селекторов
- минификация кода
- генерация source maps

 Пресет из `@emotion/babel-preset-css-prop` включает плагин из `babel-plugin-emotion` и вводит возможность использования css prop, поэтому его использование предпочтительнее.

Для установки необходимо добавить в проект пакет `@emotion/babel-preset-css-prop` и изменить конфигурацию Babel.

Для добавления в проект необходимо выполнить:

```sh
yarn add --dev @emotion/babel-preset-css-prop
```

Пример конфигурации:

```json
{
  "presets": [
    "@emotion/babel-preset-css-prop"
  ]
}
```

Если конфигурация Babel включает пресеты `@babel/preset-react` или `@babel/preset-typescript`, необходимо указать пресет `@emotion/babel-preset-css-prop` после них.

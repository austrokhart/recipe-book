# ESLint

## Интеграция с Prettier

> - [Раздел документации Prettier с описанием установки](https://prettier.io/docs/en/install.html)
> - [Раздел документации Prettier с описанием интеграции с ESLint](https://prettier.io/docs/en/integrating-with-linters.html#eslint)
> - [Раздел документации Prettier с описанием параметров конфигурации](https://prettier.io/docs/en/options.html)
> - [Гист со сравнением `prettier-eslint`, `eslint-plugin-prettier` и `eslint-config-prettier`](https://gist.github.com/yangshun/318102f525ec68033bf37ac4a010eb0c)

### Разница между ESLint и Prettier

> - [Вопрос в issues проекта в Github](https://github.com/prettier/prettier-eslint/issues/101)

ESLint это инструмент для анализа кода, исправления ошибок и форматирования. Prettier это инструмент для форматирования кода. Он предусматривает больше случаев форматирования, чем ESLint.

### Порядок интеграции

1) Добавление в проект
2) Создание файла конфигурации
3) Интеграция с ESLint
4) Использование

### Добавление в проект

Для добавления в проект Prettier необходимо выполнить:

```sh
yarn add --dev prettier
```

### Создание файла конфигурации

Файл конфигурации необходимо создать вручную. Поддерживается несколько форматов файла (например, `.prettierrc.json`).

Пример конфигурации (совместима с конфигурацией ESLint Airbnb):

```json
/* .prettierrc.json */

{
  "trailingComma": "es5",
  "tabWidth": 2,
  "semi": true,
  "singleQuote": true
}
```

### Интеграция с ESLint

Для интеграции Prettier с ESLint потребуется два пакета:

- пакет `eslint-plugin-prettier` содержит плагин для ESLint, который выполняет форматирование кода с использованием Prettier

- пакет `eslint-config-prettier` содержит конфигурацию для ESLint, которая отключает конфликтующие с работой Prettier правила форматирования

Необходимо добавить их в проект и расширить конфигурацию проекта конфигурацией `plugin:prettier/recommended`. Конфигурация должна быть указана последней в массиве расширений.

```sh
yarn add --dev eslint-config-prettier eslint-plugin-prettier
```

```json
/* .eslintrc.json */

{
  "extends": [
    "eslint:recommended",
    "plugin:prettier/recommended"
  ]
}
```

Что включает конфигурация `plugin:prettier/recommended`:

```json
{
  "extends": ["prettier"],
  "plugins": ["prettier"],
  "rules": {
    "prettier/prettier": "error"
  }
}
```

### Использование

Если не рассматривать обособленное использование, для проверки и форматирования кода необходимо использовать ESLint.

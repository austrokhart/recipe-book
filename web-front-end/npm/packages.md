# NPM

## Пакеты

### `package.json`

Файл, который содержит описание пакета `npm`.

#### Источники

> - [Раздел документации NPM с описанием создания файла `package.json`](https://docs.npmjs.com/creating-a-package-json-file)
> - [Раздел документации NPM с описанием структуры файла `package.json`](https://docs.npmjs.com/files/package.json)

#### Пример структуры

Пример структуры описания пакета:

```json
/* package.json */

{
  "name": "package-name",
  "version": "1.0.0",
  "main": "index.js",
  "license": "MIT"
}

```

#### Обязательные поля

Описание пакета должно включать поля `name` и `version`.

Поле `name` должно содержать имя пакета. Имя должно быть одним словом в нижнем регистре, может содержать символы `-` или `_`.

Поле `version` должно содержать номер версии пакета. Номер должен соответствовать формату `x.x.x` и рекомендации о семантическом версионировании.

#### Если пакет содержит браузерное приложение

Если пакет содержит браузерное приложение, его код может включать обращения к примитивам, которые недоступны в node (например, `window`). В таком случае вместо поля `main` необходимо указать поле `browser`:

```json
/* package.json */

{
  "browser": "index.js",
}
```

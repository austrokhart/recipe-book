# Webpack

## Файл конфигурации на Typescript

> - [раздел документации Webpack с описанием создания и использования файла конфигурации на Typescript](https://webpack.js.org/configuration/configuration-languages/#typescript)

### Порядок

1. Добавление зависимостей в проект
2. Создание файла конфигурации Webpack
3. Настройка конфигурации Typescript
4. Использование

### Добавление зависимостей в проект

Для использования файла конфигурации на Typescrit необходимо добавить в проект пакеты `typescript`, `ts-node` и соответствующие type definitions:

```sh
yarn add --dev typescript ts-node @types/node @types/webpack

# если потребуется использовать webpack-dev-server
yarn add --dev @types/webpack-dev-server
```

### Создание файла конфигурации Webpack

Файл конфигурации необходимо создать вручную.

Пример конфигурации:

```ts
/* webpack.config.ts */

import * as path from "path";
import * as webpack from "webpack";

const config: webpack.Configuration = {
  mode: "production",
  entry: "./foo.js",
  output: {
    path: path.resolve(__dirname, "dist"),
    filename: "foo.bundle.js"
  }
};

export default config;
```

### Настройка конфигурации Typescript

Пример конфигурации Webpack выше требует использования Typescript версии >= 2.7 с активными параметрами компилятора `esModuleInterop` и `allowSyntheticDefaultImports`. Если параметр компилятора `module` имеет значение, отличное от `CommonJS`, в работе Webpack будут возникать ошибки, поскольку `ts-node` поддерживает только синтаксис модулей `CommonJS`.

У этой проблемы есть два решения:

1. изменение текущей конфигурации Typescript
2. установка пакета `tsconfig-paths` и использование отдельной конфигурации Typescript для Webpack

_В первом случае_ необходимо открыть файл конфигурации Typescript, раздел `compilerOptions`, и установить значения параметра `target` в `ES5` и `module` в `CommonJS`.

_Во втором случае_ необходимо установить пакет `tsconfig-paths` и создать отдельную конфигурацию Typescript для запуска Webpack:

```sh
yarn add --dev tsconfig-paths cross-env
```

```json
/* tsconfig-for-webpack-config.json */

{
  "compilerOptions": {
    "module": "commonjs",
    "target": "es5",
    "esModuleInterop": true
  }
}
```

После установки `tsconfig-paths`, `ts-node` может определить, какую конфигурацию использовать для работы, используя переменную окружения `TS_NODE_PROJECT`.

### Использование

Для запуска Webpack необходимо выполнить:

```sh
yarn run cross-env TS_NODE_PROJECT=\"tsconfig-for-webpack-config.json\" webpack
```

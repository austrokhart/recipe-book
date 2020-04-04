# VSCode

## Форматирование при сохранении (в т.ч. автосохранении)

Чтобы выполнять форматирование при сохранении, необходимо добавить в конфигурацию редактора:

```json
/* settings.json */

/* пример с ESLint */

{
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  }
}
```

## Расширения

### ESLint

#### Как форматтер

Чтобы иметь возможность выполнять форматирование кода вручную (Ctrl+Alt+L), необходимо добавить в конфигурацию редактора:

```json
/* settings.json */

{
  "eslint.format.enable": true,
}
```

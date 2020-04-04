# Yarn

## Проблемы

### `There appears to be trouble with your network connection. Retrying...`

> - [Репорт в issues проекта в Github](https://github.com/yarnpkg/yarn/issues/4890)

Возможные решения:

1) воспользоваться VPN
2) удалить файл `yarn.lock` и выполнить `yarn install` снова
3) увеличить таймаут: `yarn add <package> --network-timeout 100000`

Если возникает после `Done`, можно проигнорировать.

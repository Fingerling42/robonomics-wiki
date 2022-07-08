---
title: Как установить ноду Робономики в режиме разработчика
cover_image: 'run-dev-node-ru.png' 
contributors: [LoSk-p, katerina510]
translated: true
---

Для тестирования Ваших приложений для Робономики Вам может понадобиться установка ноды в режиме разработчика.

https://youtu.be/04GsVkZ7aVg

## Запускаем

1. Прежде всего, Вам понадобится двоичный файл. Загрузите архив с ним из последнего [релиза](https://github.com/airalab/robonomics/releases).

2. Распакуйте его и измените разрешения:

```bash
tar xf robonomics-1.7.0-x86_64-unknown-linux-gnu.tar.gz
chmod +x robonomics
```

3. Запустите в режиме разработчика:

```bash
./robonomics --dev
```
Вы увидите следующее:

![robonomics](../images/dev-node/robonomics.png)

## Получите токены

Теперь Вы можете подключиться к Вашей локальной ноде через [Портал Полькадот](https://polkadot.js.org/apps/#/explorer).

Измените сеть на `Local Node` в верхнем левом углу и нажмите `Switch`.

![локальная нода](../images/dev-node/portal.png)

Затем перейдите в `Accounts`:

![аккаунты](../images/dev-node/accs.png)

Вы можете создать новый аккаунт, нажав `Add Account`.

![добавить аккаунт](../images/dev-node/add_acc.png)

Не забудьте сохранить сид-фразу в надежном месте.

Используйте один из существующих аккаунтов для отправки токенов на Ваш новый аккаунт. Выберите, к примеру, Alice, и нажмите `Send`. Затем выберите Ваш новый аккаунт, введите количество токенов для отправки и нажмите `Make Transfer`:

![отправить](../images/dev-node/send.png)
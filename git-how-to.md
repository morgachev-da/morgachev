# Github Guide

## SSH
1. Открыть `Git Bash` или обычный терминал на Линуксе
2. `cd ~/.ssh/`
3. `ssh-keygen -C "mail_address@company.domain"`
    + `-t ed25519` Является типом ключа по умолчанию
4. Сохранить ключ под удобным именем
5. Linux: открыть/создать файл `config` в `~/.ssh/`
6. Добавить в него следующие строки для автоматической настройки ssh при запуске терминала:
```
Host github.com
        HostName github.com
        User git
        IdentityFile ~/.ssh/your_private_key
        IdentitiesOnly yes

```
7. На Windows можно использовать WSL, либо Github Desktop (он вроде сам всё настроит), либо
```
eval "$(ssh-agent -s)"`
ssh-add ~/.ssh/your_private_key
```

## Github
Найти в настройках `SSH and GPG keys`

Добавить в SSH публичный ключ (всё содержимое файла ключа с расширением `.pub`)

При добавлении использовать предлагаемые Github параметры по умолчанию.

## Git clone

Находим нужный репозиторий: на GitHub либо путь к локальному репозиторию

Переходим в терминале в нужную папку и выполняем команду
```
git clone url_or_path_to_repo
````
Примечание: для отправления коммитов на сервер необходимо копировать ссылку SSH

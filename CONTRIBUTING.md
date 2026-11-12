# Как запустить библиотеку

## Установка

Нужны Git, PHP 8 с расширениями pdo_mysql и mbstring, MySQL 8 и редактор. На практике использовались VS Code и Apache NetBeans 25. Для проверки стиля скачайте материалы преподавателя: https://github.com/AlexandrAndreevichB/PP03. В папке tools/php находятся phpcs.phar и phpcbf.phar.

## Запуск

1. Выполните `git clone https://github.com/medvedeva26/kait-library.git` и перейдите в папку kait-library. Для проверки ветки до слияния используйте `git switch practice/m04`.
2. Создайте пустую базу MySQL, например kait_check, и дайте своему пользователю права на неё. В MySQL выберите эту базу и выполните сначала database/schema.sql, затем database/seed.sql.
3. Скопируйте .env.example в .env. Укажите имя базы, пользователя, пароль и порт MySQL. Для запуска ниже укажите APP_URL=http://127.0.0.1:8084.
4. В корне выполните `php -S 127.0.0.1:8084 -t public`. Откройте http://127.0.0.1:8084. В учебной базе можно войти как librarian@kait20.ru с паролем password.

## Редакторы

В VS Code откройте папку проекта и установите рекомендованные расширения. Настройки PHP лежат в .vscode. Профиль для переноса можно импортировать через Profiles → Import Profile. В NetBeans выберите File → Open Project и папку kait-library. Проект использует четыре пробела. Настройки редактора можно импортировать через Tools → Options → Import из practice/m04/netbeans-settings.zip.

## Проверка

В командах ниже PP03 — папка с материалами преподавателя, расположенная рядом с проектом. Запускайте из корня kait-library.

```
php ../PP03/tools/php/phpcs.phar --report=summary
php ../PP03/tools/php/phpcbf.phar
```

Если PHP сообщает «could not find driver», проверьте список модулей командой php -m и включите pdo_mysql в своём php.ini. Если терминал редактора не видит Git или PHP, добавьте папки программ в свой PATH и откройте терминал заново.

Перед коммитом проверьте git diff и повторите phpcs. Если проверка проходит, у команды код завершения 0.

## Git

Для каждого модуля создавайте отдельную ветку, например practice/m04. Для форматирования используйте отдельный коммит с префиксом style, для исправлений — fix. Пароли в .env, каталог nbproject/private и локальные пути редакторов оставляйте на компьютере.

# Symfony w/ Docker config

Темплейт приложения Symfony
1. Symfony (5.4 LTS)
2. PHP 8.0
3. PostgreSQL 14.2
4. Dockerized Nginx, FPM, CLI and a database
5. CS-Fixer и Psalm

# Quick Start

1. `composer create-project ddlzz/symfony-docker-website-skeleton local_project_path`
2. `make init` - Обязательно запустить перед началом работы над проектом. До настраивает приложение, удаляет временные файлы.
3. `make up`
4. Все контейнеры по дефолту займут рандомные поля в диапазоне (47001-47999)

Для всех контейнеров можно задать порты в ручную в /.env file (`make restart` необходимо выполнить для применения изменений).

## Configuring Xdebug settings for PhpStorm IDE

Для интеграции PHPStorm и Xdebug:
1. Создайте PHP interpreter в `Settings -> Languages & Frameworks -> PHP` для php-fpm в проекте;
2. Порт `9009` в меню `Settings -> Languages & Frameworks -> PHP -> Debug -> Xdebug -> Debug`.
3. Создайте сервер `Docker` в меню `Settings -> Languages & Frameworks -> PHP -> Servers`.
4. Настройте маппинг путей, если PHPStorm не сможет сам `Settings -> Languages & Frameworks -> PHP -> Path Mappings`,
5. Нажмите `Listen for PHP debug connections`;  

Дополнительная информация [documentation](https://www.jetbrains.com/help/phpstorm/debugging-with-phpstorm-ultimate-guide.html).

# Useful makefile commands

1. `make console` - Консоль для выполнения команд ZSH с предустановленными плагинами для работы с Symfony
2. `make test` - PHPUnit tests
3. `make cs` - PHP CS-fixer
4. `make psalm` - Psalm (default level is 1)


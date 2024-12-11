# Laravel Docker Environment

Это пример настроек Docker для проекта на Laravel. В этом репозитории настроены следующие сервисы:

- **nginx**: веб-сервер для обслуживания приложения.
- **php**: контейнер для выполнения PHP-кода.
- **mysql**: база данных MySQL.
- **composer**: контейнер для работы с Composer.
- **artisan**: контейнер для работы с командной строкой Laravel (`artisan`).
- **phpmyadmin**: веб-интерфейс для управления MySQL.

## Требования

Перед тем как запустить проект, убедитесь, что у вас установлен Docker и Docker Compose.

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/)

## Установка

1. Клонируйте репозиторий:

    ```bash
    git clone https://github.com/your-username/your-project.git
    cd your-project
    ```

2. Создайте файл `.env` для настройки конфигурации Laravel. Например, скопируйте файл `.env.example` в `.env` и настройте параметры базы данных:

    ```bash
    cp .env.example .env
    ```

3. Сборка и запуск контейнеров:

    ```bash
    docker-compose up -d
    ```

   Этот командный запуск создаст и запустит все контейнеры в фоновом режиме.

4. После запуска контейнеров, вы сможете:

    - Перейти в приложение по адресу: `http://localhost:8080`
    - Открыть phpMyAdmin по адресу: `http://localhost:8081`, используя:
        - Хост: `mysql`
        - Порт: `3306`
        - Имя пользователя: `root`
        - Пароль: `root`

## Команды

### Выполнение команд в контейнере

- Запуск команд в контейнере `php`:

    ```bash
    docker-compose exec php bash
    ```

- Выполнение команды `artisan`:

  Например, для миграции базы данных:

    ```bash
    docker-compose run artisan migrate
    ```

- Использование Composer для управления зависимостями:

    ```bash
    docker-compose run composer install
    ```

### Остановка контейнеров

Для остановки контейнеров используйте команду:

```bash
docker-compose down

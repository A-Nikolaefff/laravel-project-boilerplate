# Laravel Project Boilerplate

## Обзор
Этот шаблон для Laravel разработан с двумя основными целями:

1. **Создание базовой среды для разработки на Laravel:** Этот шаблон предоставляет базовую конфигурацию для локальной разработки
приложений Laravel. Он не является универсальным решением, подобно Laravel Sail или Laradock, и предполагает,
что разработчик может самостоятельно добавлять, удалять или настраивать сервисы по мере необходимости, 
что требует базового понимания Docker.
2. **Упрощение работы с командами:** Шаблон включает Makefile для быстрого доступа к наиболее часто используемым командам 
разработки Laravel, позволяя выполнять их без предварительного входа в PHP контейнер. Эти алиасы могут быть легко
адаптированы или расширены в соответствии с особенностями конкретного проекта.

## Системные ребтования
Шаблон предназначен для использования на системах Linux или WSL (Windows Subsystem for Linux). 
Для работы необходим установленный пакет make. Команда для установки на Ubuntu:
```
sudo apt install make
```

## Состав шаблона
- PHP: версия 8.3
- Laravel: версия 11
- MySQL: версия 8.3
- PostgreSQL: версия 16.2

## Инициализация нового проекта
* Клонируйте репозиторий в новую директорию с помощью команды:
```
git clone https://github.com/A-Nikolaefff/laravel-project-boilerplate.git YOUR_PROJECT_NAME
```
* В директории проекта выполните команду для инициализации нового Laravel проекта:
```
make init
```
* Установите в .env файле переменные для соединения с базой данной. Пример для MySQL:
```
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=laravel
DB_PASSWORD=laravel
```
* Запустите команду для начала работы контейнеров:
```
make up
```
* Запустите команду миграции базы данных
```
make migrate
```
* Проверьте доступность стандартной страницы Laravel по адресу: http://localhost:8080/

## Make комманды
Полный список команд доступен с помощью команды ```make help``` или в самом Makefile в корне проекта. Примеры команд:

* ```make init``` - инициализация нового проекта Laravel
* ```make up``` - запуск контейнеров
* ```make php``` - зайти в контейнер php (запустить терминал)
* ```make debug``` - отладка консольной команды
* ```make migrate``` - запуск миграций базы данных

## Настройка Xdebug в PHPStorm

* **Имя сервера:** localhost
* **Хост**: localhost
* **Порт**: 80
* **Path Mapping:** настроить сопоставление корневой директории проекта с путем /var/www/.

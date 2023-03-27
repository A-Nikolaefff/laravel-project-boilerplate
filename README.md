# Laravel Project Boilerplate
Сборка для быстрого развертывания локального окружения для разработки на Laravel.
Предназначена для Linux. 

### Состав:
* PHP 8.2
* Xdebug
* Composer
* PostgreSQL 15.1
* pgAdmin
* MySQL 5.7

### Создание нового проекта (Linux):
* **Обязательно** удалить файл **.geetkeep** из директории **src**, 
в момент создания нового проекта Laravel эта папка должна быть пустой.
* Выполнить команду ```make up``` 
* Выполнить команду ```make init``` 
* Проверить, что проект доступен по адресу  http://localhost:8080/

### Команды (Linux):
Для удобства управления все основные команды внесены в Makefile

* ```make build``` - сборка контейнеров
* ```make up``` - запуск контейнеров
* ```make down``` - остановка контейнеров
* ```make ps``` - список запущенных контейнеров
* ```make exec c=CONTAINER``` - зайти в контейнер, вместо CONTAINER подставить ID или имя контейнера
* ```make init``` - инициализация нового проекта Laravel

### Настройка Xdebug в PHPStorm:
* IDE key по умолчанию: docker
* Использовать path mapping для директории **src**

### Возможные проблемы

Для корректной работы volumes докер-контейнера PostgreSQL необходимо,
что бы UID/GID пользователя внутри контейнера соответствовали значению
локального пользователя Linux. По умолчанию данный контейнер запускается
с UID/GID 1000/1000. В случае если UID/GID локального пользователя отличаются
необходимо выполнить команды ```export LOCAL_UID=$(id -u)``` и ```export LOCAL_GID=$(id -g)```
перед первым запуском контейнера PostgreSQL.

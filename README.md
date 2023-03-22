# Laravel Project Boilerplate
Сборка для быстрого старта разработки на Laravel. Предназначена для локального использования.

### Состав:
* PHP 8.2
* Xdebug
* Composer
* PostgreSQL 15.1
* MySQL 5.7

### Настройка Xdebug в PHPStorm:
* IDE key по умолчанию: docker
* Использовать path mapping для папки **src**

### Команды (Linux):
Все команды выполнять в директории **bin/linux**

Перед первых использованием команд, в той же директории выполнить команду 
```chmod +x build init up down list exec```

* ```./build``` - сборка или пересборка контейнеров
* ```./init``` - создание нового Laravel проекта. Обязательное условие для корректной работы - папка src должна быть пустой
* ```./up``` - запуск контейнеров 
* ```./down``` - остановка контейнеров 
* ```./list``` - список запущенных контейнеров 
* ```./exec имя_контейнера``` - зайти в контейнер 
* ```./exec``` - при запуске без имени контейнера выводится список запущенных контейнеров с возможностью выбора контейнера по номеру

### Команды (Windows):
Все команды выполнять в директории **bin/win**

* ```.\build``` - сборка или пересборка контейнеров
* ```.\init``` - создание нового Laravel проекта. Обязательное условие для корректной работы - папка src должна быть пустой
* ```.\up``` - запуск контейнеров
* ```.\down``` - остановка контейнеров 
* ```.\list``` - список запущенных контейнеров
* ```.\exec имя_контейнера``` - зайти в контейнер
# to_do_app
REST API для создания списков задач. В нем реализован CRUD по протоколу HTTP.
## Функции
 
* регистрация новых пользователей;
* аутентификация;
* создание, редактирование, удаление, просмотр списков и задач из них
 
## Реализация
 
* для обработки HTTP-запросов используется фреймворк gin-gonic/gin;
* для хранения информации база данных postgres, для которой есть файлы миграции;
* для работы с данными библиотека jmoiron/sqlx;
* для работы с файлами конфигурации spf13/viper;
* для локального тестирования приложения был использован Postman, база данных была поднята в контейнере Docker;
* для аутентификации JWT-токены и библиотека dgrijalva/jwt-go
 
## Запуск приложения
 
 ```azure
$ docker run --name=todo_db -e POSTGRES_PASSWORD='qwerty' -p 5436:5436 -d --rm postgres
$ docker ps
$ docker exec -it <id>
$ migrate -path ./todo-app/schema -database 'postgres://postgres:qwerty@localhost:5436/postgres?sslmode=disable' up
$ go run ./cmd/main.go
```

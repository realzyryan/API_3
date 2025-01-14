
[![Build status](https://ci.appveyor.com/api/projects/status/8dfr45ys084b2dw9/branch/main?svg=true)](https://ci.appveyor.com/project/realzyryan/postmanecho/branch/main)

# Домашнее задание к занятию «1.2. Тестирование API, CI»

## Задача №3 - Postman Echo

**Важно**: эту задачу нужно выполнять в отдельном репозитории

В этой задаче мы сэмулируем ситуацию, в которой SUT уже запущен, а мы из теста просто обращаемся к нему.

Есть специальный сервис, предназначенный для тестирования HTTP-запросов. Называется он [Postman Echo](https://docs.postman-echo.com).

Мы можем отправлять туда запросы и получать ответы.

Нас будут интересовать POST-запросы, а именно отправка тела запроса:

```java
// Given - When - Then
// Предусловия
given()
  .baseUri("https://postman-echo.com")
  .body("some data") // отправляемые данные (заголовки и query можно выставлять аналогично)
// Выполняемые действия
.when()
  .post("/post")
// Проверки
.then()
  .statusCode(200)
  .body(/* --> ваша проверка здесь <-- */)
;
```

**Что нужно сделать:**
1. Создайте новый проект на базе Gradle
2. Добавьте необходимые зависимости (если вы не пишите схему, то только rest-assured)
3. Напишите тест, взяв сам запрос из кода выше
4. Изучите ответ и напишите JsonPath-выражение вместо строк `/* --> ваша проверка здесь <--*/`, которое проверит, что в нужном поле хранятся отправленные вами данные (обратите внимание, теперь у вас не массив, а объект).

Удостоверьтесь, что если вы будете использовать неверное выражение, то тесты упадут (в том числе и в CI).  

**Итого:** пришлите на проверку ссылку на ваш репозиторий (удостоверьтесь, что в истории сборки были как Success, так и Fail).  

**Результат выполнения задания:** [ссылка на текущий репозиторий](https://github.com/realzyryan/PostmanEcho)  

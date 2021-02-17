# Документация

Это приложение позволяет создать записную книжку, состоящую из записей включающих имя человека и набор его номеров. 

## Функциональность
1. Создавать новые записи
2. Добавлять новые телефоны к существующим записям
3. Удалять записи
4. Получать список записей и телефонов

## Использование
В случае если сервер работает на *localhost:8080*
1. Для создания новой записи используется POST запрос *http://localhost:8080/phoneBookREST/v1/customers/addRecord*
используемый формат JSON : 
   
   ```java
   {
   	"name":		"Your name",
   	"phones":	"Your phone"
   }
   ```
   
2. Для добавления номера к записи используется PUT запрос на *http://localhost:8080/phoneBookREST/v1/customers/updateRecordByName/PERSON_NAME?phone=PHONE_NUMBER*
  где *phone* это параметр запроса.

3. Для удаления записи используется запрос DELETE на *http://localhost:8080/phoneBookREST/v1/customers/deleteRecordByName/PERSON_NAME*
  если имя уже существует, то вызовется исключение

4. Что-бы получить все данные используется GET запрос *http://localhost:8080/phoneBookREST/v1/customers/getAllRecords*
  Что-бы получить  конкретную запись по имени используется GET запрос *http://localhost:8080/phoneBookREST/v1/customers/getRecordByName/PERSON_NAME*


## Запуск тестов
Для запуска тестов используется команда.
```mvn clean test```
# ExampleApp

## Add API
* изменил DI на Singelton
* создал CRUD операции для Users
* добавил Cors

### Документация API
### UsersController
 * Получить всех пользователей
   
   > GET http://192.168.0.100:5052/api/Users
   
  Response body 
 ```json
    [
  {
    "id": 1,
    "name": "Oleg",
    "login": "oleg",
    "password": "0000",
    "roleId": 1,
    "role": null
  },
  {
    "id": 3,
    "name": "Andrey",
    "login": "andrey",
    "password": "123",
    "roleId": 2,
    "role": null
  }
]
 ```

 * Получить пользователя по Id
   
   > GET http://192.168.0.100:5052/api/Users/1
   
   Response body 
 ```json
 {
  "id": 1,
  "name": "Oleg",
  "login": "oleg",
  "password": "0000",
  "roleId": 1,
  "role": null
}
 ```

 * Создать нового пользователя
   
   > POST https://localhost:7032/api/Users
   
  Request body 
```json
 {
  "name": "string",
  "login": "string",
  "password": "string",
  "roleId": 1
  
}
 ```  

 Server response: Пользователь успешно добавлен  

 Request body 
```json
 {
  "name": "string",
  "login": "oleg",
  "password": "string",
  "roleId": 1
  
}
 ```  
 
 Server response: Пользователь с таким логином уже существует  
 
 Request body 
```json
 {
  "name": "string",
  "login": "string1",
  "password": "",
  "roleId": 1
  
}
 ```  
 
 Server response: Не все поля были заполнены  
 

 * Обновить пользователя
   
   >  PUT https://localhost:7032/api/Users/UpdateUser
   
   Request body 
```json
 {
  "name": "string",
  "login": "string123",
  "password": "string",
  "roleId": 1
}
```  

Server response: Пользователь с таким логином не существует  

Request body 
```json
 {
  "name": "string",
  "login": "oleg",
  "password": "",
  "roleId": 1
} 
 ```  
 Server response: Не все поля были заполнены  

 Request body 
```json
 {
  "name": "string",
  "login": "oleg",
  "password": "12345",
  "roleId": 1
}
 ```  
 Server response: Пользователь успешно обновлён

 * DELETE  > http://192.168.0.100:5052/api/Users/Delete?login=string  

 Server response: Пользователь успешно удалён  

 * DELETE  > http://192.168.0.100:5052/api/Users/Delete?login=stri

 Server response: Пользователь с таким логином не существует  
 * GET > http://192.168.0.100:5052/api/Users/Login?login=oleg&password=12345
   	
Response body  
```json
 {
  "id": 1,
  "name": "string",
  "login": "oleg",
  "password": "12345",
  "roleId": 1,
  "role": null
}
 ```
 * GET > http://192.168.0.100:5052/api/Users/Login?login=oleg&password=123
   	
Response body: Такого пользователя нет  

   
### RolesController

## Android

Создал мобильное приложение с CRUD операциями

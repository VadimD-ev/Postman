![soft](https://capsule-render.vercel.app/api?type=soft&color=fe895f&text=POSTMAN&fontSize=50&animation=twinkling)

## __Задание:__

<!--start -->
1. ### _*Создать коллекцию в Postman портал администратора для системы с тортами.*_

2. ### _*Всю необходимую информацию брать из консоли разработчика.*_

3. ### _*Найдите методы, которые используются в продукте.*_

      - Получение списка тортов в портале администратора; 
      - Функционал добавления торта;       
      - Функционал удаления торта из системы.

4. ### _*Добавьте в коллекцию параметр baseUrl и сделайте все запросы параметризованными {{baseUrl}}.*_

>![Typing SVG](https://readme-typing-svg.herokuapp.com?color=F7F4F1EE&lines=My+practice+⬇️&font=Fira+Code&size=16&pause=3000)

- ### _*[Watch the video](https://youtu.be/MYfQcmzOiqI)*_

- ### _*Collection in Postman портал администратора для системы с тортами*_

```
{
 "info": {
  "_postman_id": "656af83e-16e6-4867-af19-88f3f5d3085a",
  "name": "Портал администратора для системы с тортами",
  "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json",
  "_exporter_id": "20998045"
 },
 "item": [
  {
   "name": "Получение списка тортов в портале администратора",
   "item": [
    {
     "name": "Получение списка тортов",
     "event": [
      {
       "listen": "test",
       "script": {
        "exec": [
         "pm.test(\"Status code is 200\", function () {\r",
         "    pm.response.to.have.status(200);\r",
         "});"
        ],
        "type": "text/javascript"
       }
      }
     ],
     "request": {
      "method": "GET",
      "header": [],
      "url": {
       "raw": "{{BaseUrl}}/cakes",
       "host": [
        "{{BaseUrl}}"
       ],
       "path": [
        "cakes"
       ]
      }
     },
     "response": []
    }
   ]
  },
  {
   "name": "Функционал добавления торта",
   "item": [
    {
     "name": "Добавления торта",
     "event": [
      {
       "listen": "test",
       "script": {
        "exec": [
         "var key = \"Id del\"\r",
         "var value = pm.response.json().id\r",
         "pm.collectionVariables.set(key,value)\r",
         "\r",
         "pm.test(\"Status code is 200\", function () {\r",
         "    pm.response.to.have.status(200);\r",
         "});"
        ],
        "type": "text/javascript"
       }
      }
     ],
     "request": {
      "method": "POST",
      "header": [],
      "body": {
       "mode": "raw",
       "raw": "{\r\n    \"name\":\"Чизкейк\",\r\n    \"photoFileName\":\"\",\r\n    \"description\":\"\",\r\n    \"forWhoId\":0,\r\n    \"occasionId\":0\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseUrl}}/cakes/add",
       "host": [
        "{{BaseUrl}}"
       ],
       "path": [
        "cakes",
        "add"
       ]
      }
     },
     "response": []
    }
   ]
  },
  {
   "name": "Функционал удаления торта из системы",
   "item": [
    {
     "name": "Удаления торта",
     "event": [
      {
       "listen": "test",
       "script": {
        "exec": [
         "pm.test(\"Status code is 200\", function () {\r",
         "    pm.response.to.have.status(200);\r",
         "});"
        ],
        "type": "text/javascript"
       }
      }
     ],
     "request": {
      "method": "DELETE",
      "header": [],
      "url": {
       "raw": "{{BaseUrl}}/cakes/{{Id del}}",
       "host": [
        "{{BaseUrl}}"
       ],
       "path": [
        "cakes",
        "{{Id del}}"
       ]
      }
     },
     "response": []
    }
   ]
  }
 ],
 "variable": [
  {
   "key": "BaseUrl",
   "value": "https://buy-cakes.herokuapp.com/api"
  },
  {
   "key": "BaseUrl",
   "value": ""
  },
  {
   "key": "Id del",
   "value": ""
  }
 ]
}
```
<!--end-->
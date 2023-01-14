![soft](https://capsule-render.vercel.app/api?type=soft&color=f5f5f5&text=cURL/POSTMAN&fontSize=50&animation=twinkling)

## __*Задание:*__
<!--start-->
1. ### _*Отправим cURL-запросы через терминал по описанным тест-кейсам.*_

      - Получение списка задач; 
      - Создание новой задачи;       
      - Отметка о выполнении задачи;
      - Удаление задачи.

2. ### _*Отправим запросы через Postman для проверки сайта с тортами.*_

      1. Получить список данных «Для кого?»;
      - Ответ мне пришел в формате JSON на запрос, в нем есть 5 значений:
      ```
      [
      {
      "id": 0,
      "name": "мальчик"
      },
      {
      "id": 1,
      "name": "девочка"
      },
      {
      "id": 2,
      "name": "мужчина"
      },
      {
      "id": 3,
      "name": "женщина"
      },
      {
      "id": 4,
      "name": "другой повод"
      }
      ] 
      ``` 
      - Данные во frontend совпадают с данными с backend.


      2. Отображения списка тортов;        
      3. Отображения конкретного торта, взять любой ID торта из списка тортов, которые вы получили в первом пункте.
 
>![Typing SVG](https://readme-typing-svg.herokuapp.com?color=F7F4F1EE&lines=My+practice+⬇️&font=Fira+Code&size=16&pause=3000)

## *__cURL/Postman__*

- ## _*cURL*_

```
1. Операция: «Получение списка задач»
- Команда: curl https://todo-app-sky.herokuapp.com/ 
- Результат выполнения команды в терминале: [{"id":20008,"title":"Отправить E-mail","completed":true,"order":null,"url":"/20008"},{"id":20010,"title":"Добавление задачи","completed":true,"order":null,"url":"/20010"},{"id":20014,"title":"завтрак","completed":false,"order":null,"url":"/20014"},{"id":20013,"title":"Add","completed":false,"order":null,"url":"/20013"},{"id":20007,"title":"Проверить почту","completed":false,"order":null,"url":"/20007"},{"id":20016,"title":"What to do","completed":false,"order":null,"url":"/20016"},{"id":20015,"title":"Add1","completed":true,"order":null,"url":"/20015"},{"id":20017,"title":"Ужин","completed":false,"order":null,"url":"/20017"},{"id":20018,"title":"выгулять собаку","completed":false,"order":null,"url":"/20018"}]
 
2. Операция: «Cоздание новой задачи»
- Команда: curl -x POST https://todo-app-sky.herokuapp.com/ -h "Content-Type: application/json" -d '{\"title\" : \"A NEW DAY\"}'
- Результат выполнения команды в терминале: "id": 20076,"title": "A NEW DAY","completed": false,"order": null,"url": "/20076"

3. Операция: «Отметка о выполнении задачи»
- Команда: curl -x POST https://todo-app-sky.herokuapp.com/ 20076 -h "Content-Type: application/json" -d '{\"completed\" : true}'
-Результат выполнения команды в терминале: {"id": 20080,"title": null,"completed": false,"order": null,"url": "/20080"}

4. Операция: «Удаление задачи»
- Команда: curl -x DELETE https://todo-app-sky.herokuapp.com/ 20076
- Результат выполнения команды в терминале: Удаление задачи, ответа нет.
```
<!--end-->

<!--start-->
- ## _*Postman*_

```
{
 "info": {
  "_postman_id": "525b56b3-22e5-4fe4-93aa-57d37a2e6a46",
  "name": "Портал клиентский  для системы с тортами",
  "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json",
  "_exporter_id": "20998045"
 },
 "item": [
  {
   "name": "Cписок данных",
   "item": [
    {
     "name": "Получить список данных «Для кого?»",
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
       "raw": "https://buy-cakes.herokuapp.com/api/forWho",
       "protocol": "https",
       "host": [
        "buy-cakes",
        "herokuapp",
        "com"
       ],
       "path": [
        "api",
        "forWho"
       ]
      }
     },
     "response": []
    }
   ],
   "event": [
    {
     "listen": "prerequest",
     "script": {
      "type": "text/javascript",
      "exec": [
       ""
      ]
     }
    },
    {
     "listen": "test",
     "script": {
      "type": "text/javascript",
      "exec": [
       ""
      ]
     }
    }
   ]
  },
  {
   "name": "Cписк тортов",
   "item": [
    {
     "name": "Отображения списка тортов",
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
       "raw": "https://buy-cakes.herokuapp.com/api/cakes?\"",
       "protocol": "https",
       "host": [
        "buy-cakes",
        "herokuapp",
        "com"
       ],
       "path": [
        "api",
        "cakes"
       ],
       "query": [
        {
         "key": "\"",
         "value": null
        }
       ]
      }
     },
     "response": []
    }
   ],
   "event": [
    {
     "listen": "prerequest",
     "script": {
      "type": "text/javascript",
      "exec": [
       ""
      ]
     }
    },
    {
     "listen": "test",
     "script": {
      "type": "text/javascript",
      "exec": [
       ""
      ]
     }
    }
   ]
  },
  {
   "name": "Отображения конкретного торта",
   "item": [
    {
     "name": "Отображения конкретного торта",
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
       "raw": "https://buy-cakes.herokuapp.com/api/cakes/64390",
       "protocol": "https",
       "host": [
        "buy-cakes",
        "herokuapp",
        "com"
       ],
       "path": [
        "api",
        "cakes",
        "64390"
       ]
      }
     },
     "response": []
    }
   ],
   "event": [
    {
     "listen": "prerequest",
     "script": {
      "type": "text/javascript",
      "exec": [
       ""
      ]
     }
    },
    {
     "listen": "test",
     "script": {
      "type": "text/javascript",
      "exec": [
       ""
      ]
     }
    }
   ]
  }
 ],
 "event": [
  {
   "listen": "prerequest",
   "script": {
    "type": "text/javascript",
    "exec": [
     ""
    ]
   }
  },
  {
   "listen": "test",
   "script": {
    "type": "text/javascript",
    "exec": [
     ""
    ]
   }
  }
 ],
 "variable": [
  {
   "key": "BaseUrl",
   "value": "https://buy-cakes.herokuapp.com/api",
   "type": "string"
  }
 ]
}
```
<!--end-->

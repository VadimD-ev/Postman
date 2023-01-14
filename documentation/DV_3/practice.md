
![soft](https://capsule-render.vercel.app/api?type=soft&color=fe895f&text=POSTMAN&fontSize=50&animation=twinkling)

## __*Задание:*__

<!--start -->
1. ### _*Создать коллекцию в Postman веб-приложение для учителей от Skyeng.*_
      - Протестировать кабинет учителя, продуктом сейчас пользуются более 3000 человек.
      - Наш проект — это вкладка «Расписание» и мы продолжаем работать только с личными событиями.

2.  ### _*Требования к коллекции:*_
       - Токен должен быть оформлен через переменную,
       - URL также должен быть оформлен через переменную,
       - В названии запроса должно быть указано, что происходит в запросе,
       - В коллекции должно быть не менее 10 функциональных тест-кейсов.

3. ### _*Swagger в Skyeng закрытый, используйте Chrom Devtools и вытащите запросы оттуда.*_
```
       1. Отображение списка личныx событий:  
      -Отображение личного события.

       2. Создание списка личныx событий:  
      - Создание личныx событий на латинице,
      - Создание личныx событий на кирилице,
      - Создание личныx событий с выбором цветовой гаммы,
      - Создание личныx событий время и даты в будущем,
      - Создание личныx событий с неустановленной датой и временем.

       3. Редактирование списка личныx событий:  
      - Редактирование личныx событий на латинице,
      - Редактирование личныx событий на кирилице,
      - Редактирование личныx событий времени и даты,
      - Редактирование личныx событий выбор любой цветовой гаммы.

       4. Удаление списка личныx событий:  
       - Удаление списка личныx событий на латинице,
       - Удаление списка личныx событий на кирилице,
       - Удаление списка личныx событий c ранее выбранной цветовой гаммы,
       - Удаление списка личныx событий созданного в будущем времени.  
```
4. ### _*Провести test-run.*_

>![Typing SVG](https://readme-typing-svg.herokuapp.com?color=F7F4F1EE&lines=My+practice+⬇️&font=Fira+Code&size=18&pause=3000)

- ### _*Collection in Postman веб-приложение для учителей от Skyeng*_

```
{
 "info": {
  "_postman_id": "28bff320-fbf4-4b43-a624-8cdc1aa99020",
  "name": "Веб-приложение для учителей от Skyeng",
  "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json",
  "_exporter_id": "20998045"
 },
 "item": [
  {
   "name": "Отображение списка Л/С",
   "item": [
    {
     "name": "Отображение Л/C",
     "event": [
      {
       "listen": "test",
       "script": {
        "exec": [
         "pm.test(\"Status code is 200\", function () {\r",
         "    pm.response.to.have.status(200);\r",
         "});\r",
         ""
        ],
        "type": "text/javascript"
       }
      }
     ],
     "request": {
      "method": "POST",
      "header": [
       {
        "key": "Cookie",
        "value": "{{MyToken}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n    \"from\": \"2022-07-05T00:00:00+03:00\",\r\n    \"till\": \"2022-07-05T00:00:00+03:00\",\r\n    \"onlyTypes\": [\r\n        \"slot\",\r\n        \"event\"\r\n    ],\r\n    \"statuses\": [\r\n        \"without_status\"\r\n    ]\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseUrl}}schedule/events",
       "host": [
        "{{BaseUrl}}schedule"
       ],
       "path": [
        "events"
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
   "name": "Создание списка ЛС",
   "item": [
    {
     "name": "Создание Л/C на латинице",
     "event": [
      {
       "listen": "test",
       "script": {
        "exec": [
         "var key = \"ID_Latin alphabet\" \r",
         "var value = pm.response.json().data.payload.id\r",
         "pm.collectionVariables.set(key, value);\r",
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
      "header": [
       {
        "key": "Cookie",
        "value": "{{MyToken}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n   \"startAt\": \"2022-07-08T00:00:00+03:00\",\r\n   \"endAt\": \"2022-07-08T00:30:00+03:00\",\r\n   \"title\": \"It's a great day\",\r\n   \"description\": \"\",\r\n   \"color\": \"#81888D\",\r\n   \"backgroundColor\": \"#F4F5F6\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseUrl}}schedule/createPersonal",
       "host": [
        "{{BaseUrl}}schedule"
       ],
       "path": [
        "createPersonal"
       ]
      }
     },
     "response": []
    },
    {
     "name": "Создание Л/C на кириллице",
     "event": [
      {
       "listen": "test",
       "script": {
        "exec": [
         "var key = \"ID_Cyrillic alphabet\"\r",
         "var value = pm.response.json().data.payload.id\r",
         "pm.collectionVariables.set(key, value);\r",
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
      "header": [
       {
        "key": "Cookie",
        "value": "{{MyToken}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n   \"startAt\": \"2022-07-08T00:01:00+03:00\",\r\n   \"endAt\": \"2022-07-08T00:30:00+03:00\",\r\n   \"title\": \"Отличный день\",\r\n   \"description\": \"\",\r\n   \"color\": \"#81888D\",\r\n   \"backgroundColor\": \"#F4F5F6\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseUrl}}schedule/createPersonal",
       "host": [
        "{{BaseUrl}}schedule"
       ],
       "path": [
        "createPersonal"
       ]
      }
     },
     "response": []
    },
    {
     "name": "Создание Л/C с выбором цветовой гаммы",
     "event": [
      {
       "listen": "test",
       "script": {
        "exec": [
         "var key = \"ID_Color selection\"\r",
         "var value = pm.response.json().data.payload.id\r",
         "pm.collectionVariables.set(key, value);\r",
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
      "header": [
       {
        "key": "Cookie",
        "value": "{{MyToken}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n   \"startAt\": \"2022-07-08T00:02:00+03:00\",\r\n   \"endAt\": \"2022-07-08T00:30:00+03:00\",\r\n   \"title\": \"It's a great day\",\r\n   \"description\": \"\",\r\n   \"color\": \"#81888D\",\r\n   \"backgroundColor\": \"#43B658\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseUrl}}schedule/createPersonal",
       "host": [
        "{{BaseUrl}}schedule"
       ],
       "path": [
        "createPersonal"
       ]
      }
     },
     "response": []
    },
    {
     "name": "Создание Л/C время и дата в будущем",
     "event": [
      {
       "listen": "test",
       "script": {
        "exec": [
         "var key = \"ID_date\"\r",
         "var value = pm.response.json().data.payload.id\r",
         "pm.collectionVariables.set(key, value);\r",
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
      "header": [
       {
        "key": "Cookie",
        "value": "{{MyToken}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n   \"startAt\": \"2022-07-10T00:02:00+03:00\",\r\n   \"endAt\": \"2022-07-10T00:30:00+03:00\",\r\n   \"title\": \"It's a great day\",\r\n   \"description\": \"\",\r\n   \"color\": \"#81888D\",\r\n   \"backgroundColor\": \"#F4F5F6\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseUrl}}schedule/createPersonal",
       "host": [
        "{{BaseUrl}}schedule"
       ],
       "path": [
        "createPersonal"
       ]
      }
     },
     "response": []
    },
    {
     "name": "Создание Л/C с неустановленной датой и временем",
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
      "method": "POST",
      "header": [
       {
        "key": "Cookie",
        "value": "{{MyToken}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n   \"startAt\": \"0000-00-00T00:00:00+00:00\",\r\n   \"endAt\": \"0000-00-00T00:00:00+00:00\",\r\n   \"title\": \"Revolution\",\r\n   \"description\": \"\",\r\n   \"color\": \"#81888D\",\r\n   \"backgroundColor\": \"#F4F5F6\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseUrl}}schedule/createPersonal",
       "host": [
        "{{BaseUrl}}schedule"
       ],
       "path": [
        "createPersonal"
       ]
      }
     },
     "response": []
    }
   ]
  },
  {
   "name": "Редактирование списка ЛС",
   "item": [
    {
     "name": "Редактирование Л/C на латинице",
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
      "method": "POST",
      "header": [
       {
        "key": "Cookie",
        "value": "{{MyToken}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n   \"startAt\": \"2022-07-08T00:00:00+03:00\",\r\n   \"endAt\": \"2022-07-08T00:30:00+03:00\",\r\n   \"title\": \"A great time to study\",\r\n   \"description\": \"\",\r\n   \"color\": \"#81888D\",\r\n   \"backgroundColor\": \"#F4F5F6\",\r\n   \"id\": {{ID_Latin alphabet}},\r\n   \"oldStartAt\": \"2022-07-08T00:00:00+03:00\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseUrl}}schedule/updatePersonal",
       "host": [
        "{{BaseUrl}}schedule"
       ],
       "path": [
        "updatePersonal"
       ]
      }
     },
     "response": []
    },
    {
     "name": "Редактирование Л/C на кириллице",
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
      "method": "POST",
      "header": [
       {
        "key": "Cookie",
        "value": "{{MyToken}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n   \"startAt\": \"2022-07-08T00:01:00+03:00\",\r\n   \"endAt\": \"2022-07-08T00:30:00+03:00\",\r\n   \"title\": \"Прекрасное время для учебы\",\r\n   \"description\": \"\",\r\n   \"color\": \"#81888D\",\r\n   \"backgroundColor\": \"#F4F5F6\",\r\n   \"id\": {{ID_Cyrillic alphabet}},\r\n   \"oldStartAt\": \"2022-07-08T00:01:00+03:00\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseUrl}}schedule/updatePersonal",
       "host": [
        "{{BaseUrl}}schedule"
       ],
       "path": [
        "updatePersonal"
       ]
      }
     },
     "response": []
    },
    {
     "name": "Редактирование Л/C времени и даты",
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
      "method": "POST",
      "header": [
       {
        "key": "Cookie",
        "value": "{{MyToken}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n   \"startAt\": \"2022-07-09T00:02:00+03:00\",\r\n   \"endAt\": \"2022-07-09T00:30:00+03:00\",\r\n   \"title\": \"It's a great day\",\r\n   \"description\": \"\",\r\n   \"color\": \"#81888D\",\r\n   \"backgroundColor\": \"#F4F5F6\",\r\n   \"id\": {{ID_date}},\r\n   \"oldStartAt\": \"2022-07-10T00:02:00+03:00\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseUrl}}schedule/updatePersonal",
       "host": [
        "{{BaseUrl}}schedule"
       ],
       "path": [
        "updatePersonal"
       ]
      }
     },
     "response": []
    },
    {
     "name": "Редактирование Л/C выбор любой цветовой гаммы",
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
      "method": "POST",
      "header": [
       {
        "key": "Cookie",
        "value": "{{MyToken}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n   \"startAt\": \"2022-07-08T00:02:00+03:00\",\r\n   \"endAt\": \"2022-07-08T00:30:00+03:00\",\r\n   \"title\": \"It's a great day\",\r\n   \"description\": \"\",\r\n   \"color\": \"#81888D\",\r\n   \"backgroundColor\": \"#F4F5F6\",\r\n   \"id\": {{ID_Color selection}},\r\n   \"oldStartAt\": \"2022-07-08T00:02:00+03:00\"\r\n}\r\n",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseUrl}}schedule/updatePersonal",
       "host": [
        "{{BaseUrl}}schedule"
       ],
       "path": [
        "updatePersonal"
       ]
      }
     },
     "response": []
    }
   ]
  },
  {
   "name": "Удаление списка ЛС",
   "item": [
    {
     "name": "Удаление Л/C на латинице",
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
      "method": "POST",
      "header": [
       {
        "key": "Cookie",
        "value": "{{MyToken}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n    \"id\": {{ID_Latin alphabet}},\r\n    \"startAt\": \"2022-07-08T00:00:00+03:00\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseUrl}}schedule/removePersonal",
       "host": [
        "{{BaseUrl}}schedule"
       ],
       "path": [
        "removePersonal"
       ]
      }
     },
     "response": []
    },
    {
     "name": "Удаление Л/C на кириллице",
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
      "method": "POST",
      "header": [
       {
        "key": "Cookie",
        "value": "{{MyToken}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n    \"id\": {{ID_Cyrillic alphabet}},\r\n    \"startAt\": \"2022-07-08T00:01:00+03:00\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseUrl}}schedule/removePersonal",
       "host": [
        "{{BaseUrl}}schedule"
       ],
       "path": [
        "removePersonal"
       ]
      }
     },
     "response": []
    },
    {
     "name": "Удаление Л/C с ранее выбранной цветовой гаммы",
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
      "method": "POST",
      "header": [
       {
        "key": "Cookie",
        "value": "{{MyToken}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n    \"id\": {{ID_Color selection}},\r\n    \"startAt\": \"2022-07-08T00:02:00+03:00\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseUrl}}schedule/removePersonal",
       "host": [
        "{{BaseUrl}}schedule"
       ],
       "path": [
        "removePersonal"
       ]
      }
     },
     "response": []
    },
    {
     "name": "Удаление Л/C созданного в будущем времени",
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
      "method": "POST",
      "header": [
       {
        "key": "Cookie",
        "value": "{{MyToken}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n    \"id\": {{ID_date}},\r\n    \"startAt\": \"2022-07-10T00:02:00+03:00\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseUrl}}schedule/removePersonal",
       "host": [
        "{{BaseUrl}}schedule"
       ],
       "path": [
        "removePersonal"
       ]
      }
     },
     "response": []
    }
   ]
  }
 ],
 "auth": {
  "type": "basic",
  "basic": [
   {
    "key": "password",
    "value": "vadim0106",
    "type": "string"
   },
   {
    "key": "username",
    "value": "vadim.volgograd.34rus@gmail.com",
    "type": "string"
   }
  ]
 },
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
   "value": "https://api-teachers.skyeng.ru/v2/",
   "type": "string"
  },
  {
   "key": "MyToken",
   "value": "token_global=eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJ1c2VySWQiOjEwMzM4NzM2LCJpZGVudGl0eSI6InRlc3QtbW9iaWxlMUBza3llbmcucnUiLCJpZGVudGl0eUxvZ2luIjpudWxsLCJpZGVudGl0eUVtYWlsIjoidGVzdC1tb2JpbGUxQHNreWVuZy5ydSIsImlkZW50aXR5UGhvbmUiOiIrNzkxMjI1MjUyNTIiLCJuYW1lIjoiXHUwNDFlXHUwNDNiXHUwNDM1XHUwNDMzIiwic3VybmFtZSI6Ilx1MDQxMFx1MDQzZDIiLCJlbWFpbCI6InRlc3QtbW9iaWxlMUBza3llbmcucnUiLCJ1aUxhbmd1YWdlIjoicnUiLCJsb2NhbGUiOiJydSIsInNlcnZpY2VMb2NhbGUiOm51bGwsInVhcyI6MzAsImp3dFR5cGUiOjEsImp0aSI6Im5rOW1CaEZzZHdBVmZrTThWRzZocU44MDdVUmdLaWR3IiwiYnJhbmQiOm51bGwsImV4cCI6MTY3MzEwNDQ2MiwiYXZhdGFyVXJsIjoiaHR0cHM6XC9cL2F1dGgtYXZhdGFycy1za3llbmcuaW1naXgubmV0XC8xMDMzODczNlwvNmEzZDhlOTgtYzZhMS00MWViLWI4ODgtNTBkMGYxOWYwMDA2P2F1dG89Zm9ybWF0JTJDZW5oYW5jZSZmaXQ9Y3JvcCZoPTIwMCZpeGxpYj1waHAtMi4xLjEmcT03NSZzYXQ9OCZzaGFycD0xMCZ2aWI9OCZ3PTIwMCIsImJpcnRoZGF5IjoiMTk4OC0wMy0wMSIsImFJc1N0cm9uZyI6dHJ1ZSwiYVR5cGUiOiJVU0VSTkFNRV9QQVNTV09SRCIsImFUaW1lIjoxNjczMDE4MDU5LCJyb2xlcyI6WyJST0xFX1RFQUNIRVIiLCJST0xFX0NSTTJfVEVBQ0hFUl9BQ0NFU1MiLCJST0xFX1RUQ19VU0FHRSIsIlJPTEVfVklNQk9YX1RFQUNIRVJfVVNBR0UiLCJST0xFX1ZJTUJPWF9DUkVBVEVfU0NSRUVOSU5HX1RFU1QiXX0.FaFvPzPTY5wKPiukGP34-7pMEKNCR0DCS-aFrxQdHJz1yCJ5ruUjL1cTAhDgxRtVtiqbLFpSZj2EzqpAxwDk7gb7VUZj1BQXW-2KylfpIb-B3aXzyqpRrtk3oIBDkUJxqMh9W1aFPlT_Y-slZv6wTCMrlFPGs-YpgDR6uTHzMLO8k7HfJ3ioabqqeWzOEvg2pyjZqQx_5SorAmPOCdJo8yXiqj-Tq80jcGMVrDUDH17_N4oFrPqs8Kj82z-NE6zyv77jE8tWB3bVxh_Lp8KYj5_wUYImTD1f2D6gueIwnUbpEIb9woVVZiJAOZ3EWOevq19rf4iXGRL6EyeJAAkaxTrVmHTVFshel8kG128ww-WpY4ey_NPUycZ0BDl3YqgMA9T93voDru6ayCTgUNmuUI0xgT3Mkg1AgbOmamhsaYcBOMZD3J1gpixkBTZWb9DlWDqnMbVqQoljOp0qkG4-7igbww67lymSRv7bcTmO_DQoaHfIC-F3-8IIHo24gtJQllTt-uiRI43h2hHy6xkTkNZc3SNkAs-29WWAEFoPKgMiaJddnn5tDa3aH5YZaeX2V2_rbunSarfLkgtkke4CYV5YV5_LZIoRGWGHL_Z3PxqXgioOt23LALi1wTIxGMCSvd6_Te0LWJlmzEfCznxeZoEFQmd7JXjSifOM0RgD3kY",
   "type": "string"
  },
  {
   "key": "ID_Latin alphabet",
   "value": ""
  },
  {
   "key": "ID_Cyrillic alphabet",
   "value": "",
   "type": "string"
  },
  {
   "key": "ID_Color selection",
   "value": "",
   "type": "string"
  },
  {
   "key": "ID_date",
   "value": "",
   "type": "string"
  },
  {
   "key": "ID_startAt",
   "value": ""
  },
  {
   "key": "startAt",
   "value": ""
  }
 ]
}

```
<!--end-->

<!--start-->
- ### _*Test_run. Веб-приложение для учителей от Skyeng*_

```
{
 "id": "50604e8c-b4cc-4a50-99a7-65b1795ef1ef",
 "name": "Веб-приложение для учителей  от Skyeng",
 "timestamp": "2023-01-06T15:29:47.720Z",
 "collection_id": "20998045-28bff320-fbf4-4b43-a624-8cdc1aa99020",
 "folder_id": 0,
 "environment_id": "0",
 "totalPass": 14,
 "totalFail": 0,
 "results": [
  {
   "id": "35c65f52-f949-43f7-a9e7-3277e074e8c8",
   "name": "Отображение Л/C",
   "url": "https://api-teachers.skyeng.ru/v2/schedule/events",
   "time": 657,
   "responseCode": {
    "code": 200,
    "name": "OK"
   },
   "tests": {
    "Status code is 200": true
   },
   "testPassFailCounts": {
    "Status code is 200": {
     "pass": 1,
     "fail": 0
    }
   },
   "times": [
    657
   ],
   "allTests": [
    {
     "Status code is 200": true
    }
   ]
  },
  {
   "id": "77ff8da1-c95e-407b-b51f-1b4ea8ab1364",
   "name": "Создание Л/C на латинице",
   "url": "https://api-teachers.skyeng.ru/v2/schedule/createPersonal",
   "time": 135,
   "responseCode": {
    "code": 200,
    "name": "OK"
   },
   "tests": {
    "Status code is 200": true
   },
   "testPassFailCounts": {
    "Status code is 200": {
     "pass": 1,
     "fail": 0
    }
   },
   "times": [
    135
   ],
   "allTests": [
    {
     "Status code is 200": true
    }
   ]
  },
  {
   "id": "e34349e4-eff9-45f2-89cb-5a1a07f4cc09",
   "name": "Создание Л/C на кириллице",
   "url": "https://api-teachers.skyeng.ru/v2/schedule/createPersonal",
   "time": 155,
   "responseCode": {
    "code": 200,
    "name": "OK"
   },
   "tests": {
    "Status code is 200": true
   },
   "testPassFailCounts": {
    "Status code is 200": {
     "pass": 1,
     "fail": 0
    }
   },
   "times": [
    155
   ],
   "allTests": [
    {
     "Status code is 200": true
    }
   ]
  },
  {
   "id": "50f61f63-d9cb-40c0-be1b-921da83f8884",
   "name": "Создание Л/C с выбором цветовой гаммы",
   "url": "https://api-teachers.skyeng.ru/v2/schedule/createPersonal",
   "time": 155,
   "responseCode": {
    "code": 200,
    "name": "OK"
   },
   "tests": {
    "Status code is 200": true
   },
   "testPassFailCounts": {
    "Status code is 200": {
     "pass": 1,
     "fail": 0
    }
   },
   "times": [
    155
   ],
   "allTests": [
    {
     "Status code is 200": true
    }
   ]
  },
  {
   "id": "3635e147-7eed-4b31-9471-e5be9341e3a1",
   "name": "Создание Л/C время и дата в будущем",
   "url": "https://api-teachers.skyeng.ru/v2/schedule/createPersonal",
   "time": 143,
   "responseCode": {
    "code": 200,
    "name": "OK"
   },
   "tests": {
    "Status code is 200": true
   },
   "testPassFailCounts": {
    "Status code is 200": {
     "pass": 1,
     "fail": 0
    }
   },
   "times": [
    143
   ],
   "allTests": [
    {
     "Status code is 200": true
    }
   ]
  },
  {
   "id": "07df9581-0270-4651-943a-409c065f3fb9",
   "name": "Создание Л/C с неустановленной датой и временем",
   "url": "https://api-teachers.skyeng.ru/v2/schedule/createPersonal",
   "time": 66,
   "responseCode": {
    "code": 200,
    "name": "OK"
   },
   "tests": {
    "Status code is 200": true
   },
   "testPassFailCounts": {
    "Status code is 200": {
     "pass": 1,
     "fail": 0
    }
   },
   "times": [
    66
   ],
   "allTests": [
    {
     "Status code is 200": true
    }
   ]
  },
  {
   "id": "3738c1fa-2ebc-409e-95ec-803549a54107",
   "name": "Редактирование Л/C на латинице",
   "url": "https://api-teachers.skyeng.ru/v2/schedule/updatePersonal",
   "time": 174,
   "responseCode": {
    "code": 200,
    "name": "OK"
   },
   "tests": {
    "Status code is 200": true
   },
   "testPassFailCounts": {
    "Status code is 200": {
     "pass": 1,
     "fail": 0
    }
   },
   "times": [
    174
   ],
   "allTests": [
    {
     "Status code is 200": true
    }
   ]
  },
  {
   "id": "86d0aa8e-0b18-49d1-96c2-311b4ed2b7cb",
   "name": "Редактирование Л/C на кириллице",
   "url": "https://api-teachers.skyeng.ru/v2/schedule/updatePersonal",
   "time": 178,
   "responseCode": {
    "code": 200,
    "name": "OK"
   },
   "tests": {
    "Status code is 200": true
   },
   "testPassFailCounts": {
    "Status code is 200": {
     "pass": 1,
     "fail": 0
    }
   },
   "times": [
    178
   ],
   "allTests": [
    {
     "Status code is 200": true
    }
   ]
  },
  {
   "id": "b0db1fe0-9a43-469d-a681-7ff15e18eb28",
   "name": "Редактирование Л/C времени и даты",
   "url": "https://api-teachers.skyeng.ru/v2/schedule/updatePersonal",
   "time": 201,
   "responseCode": {
    "code": 200,
    "name": "OK"
   },
   "tests": {
    "Status code is 200": true
   },
   "testPassFailCounts": {
    "Status code is 200": {
     "pass": 1,
     "fail": 0
    }
   },
   "times": [
    201
   ],
   "allTests": [
    {
     "Status code is 200": true
    }
   ]
  },
  {
   "id": "bea48724-eda5-4547-99bd-66334040c21d",
   "name": "Редактирование Л/C выбор любой цветовой гаммы",
   "url": "https://api-teachers.skyeng.ru/v2/schedule/updatePersonal",
   "time": 170,
   "responseCode": {
    "code": 200,
    "name": "OK"
   },
   "tests": {
    "Status code is 200": true
   },
   "testPassFailCounts": {
    "Status code is 200": {
     "pass": 1,
     "fail": 0
    }
   },
   "times": [
    170
   ],
   "allTests": [
    {
     "Status code is 200": true
    }
   ]
  },
  {
   "id": "1d7672a9-d850-4243-9ca7-0c83d19fb7c6",
   "name": "Удаление Л/C на латинице",
   "url": "https://api-teachers.skyeng.ru/v2/schedule/removePersonal",
   "time": 136,
   "responseCode": {
    "code": 200,
    "name": "OK"
   },
   "tests": {
    "Status code is 200": true
   },
   "testPassFailCounts": {
    "Status code is 200": {
     "pass": 1,
     "fail": 0
    }
   },
   "times": [
    136
   ],
   "allTests": [
    {
     "Status code is 200": true
    }
   ]
  },
  {
   "id": "d12d7039-64dc-4036-b42f-34056ac0f7d9",
   "name": "Удаление Л/C на кириллице",
   "url": "https://api-teachers.skyeng.ru/v2/schedule/removePersonal",
   "time": 180,
   "responseCode": {
    "code": 200,
    "name": "OK"
   },
   "tests": {
    "Status code is 200": true
   },
   "testPassFailCounts": {
    "Status code is 200": {
     "pass": 1,
     "fail": 0
    }
   },
   "times": [
    180
   ],
   "allTests": [
    {
     "Status code is 200": true
    }
   ]
  },
  {
   "id": "4d1b4f7b-f685-44a0-88c4-d42922fc031f",
   "name": "Удаление Л/C с ранее выбранной цветовой гаммы",
   "url": "https://api-teachers.skyeng.ru/v2/schedule/removePersonal",
   "time": 150,
   "responseCode": {
    "code": 200,
    "name": "OK"
   },
   "tests": {
    "Status code is 200": true
   },
   "testPassFailCounts": {
    "Status code is 200": {
     "pass": 1,
     "fail": 0
    }
   },
   "times": [
    150
   ],
   "allTests": [
    {
     "Status code is 200": true
    }
   ]
  },
  {
   "id": "946c0970-a0d4-4a4d-9576-b8f575187a2d",
   "name": "Удаление Л/C созданного в будущем времени",
   "url": "https://api-teachers.skyeng.ru/v2/schedule/removePersonal",
   "time": 86,
   "responseCode": {
    "code": 200,
    "name": "OK"
   },
   "tests": {
    "Status code is 200": true
   },
   "testPassFailCounts": {
    "Status code is 200": {
     "pass": 1,
     "fail": 0
    }
   },
   "times": [
    86
   ],
   "allTests": [
    {
     "Status code is 200": true
    }
   ]
  }
 ],
 "count": 1,
 "totalTime": 2586,
 "collection": {
  "requests": [
   {
    "id": "35c65f52-f949-43f7-a9e7-3277e074e8c8",
    "method": "POST"
   },
   {
    "id": "77ff8da1-c95e-407b-b51f-1b4ea8ab1364",
    "method": "POST"
   },
   {
    "id": "e34349e4-eff9-45f2-89cb-5a1a07f4cc09",
    "method": "POST"
   },
   {
    "id": "50f61f63-d9cb-40c0-be1b-921da83f8884",
    "method": "POST"
   },
   {
    "id": "3635e147-7eed-4b31-9471-e5be9341e3a1",
    "method": "POST"
   },
   {
    "id": "07df9581-0270-4651-943a-409c065f3fb9",
    "method": "POST"
   },
   {
    "id": "3738c1fa-2ebc-409e-95ec-803549a54107",
    "method": "POST"
   },
   {
    "id": "86d0aa8e-0b18-49d1-96c2-311b4ed2b7cb",
    "method": "POST"
   },
   {
    "id": "b0db1fe0-9a43-469d-a681-7ff15e18eb28",
    "method": "POST"
   },
   {
    "id": "bea48724-eda5-4547-99bd-66334040c21d",
    "method": "POST"
   },
   {
    "id": "1d7672a9-d850-4243-9ca7-0c83d19fb7c6",
    "method": "POST"
   },
   {
    "id": "d12d7039-64dc-4036-b42f-34056ac0f7d9",
    "method": "POST"
   },
   {
    "id": "4d1b4f7b-f685-44a0-88c4-d42922fc031f",
    "method": "POST"
   },
   {
    "id": "946c0970-a0d4-4a4d-9576-b8f575187a2d",
    "method": "POST"
   }
  ]
 }
}

```
<!--end-->

![soft](https://capsule-render.vercel.app/api?type=soft&color=fe895f&text=POSTMAN&fontSize=50&animation=twinkling)

- ## __*Задание:*__

<!--start-->
1. ### _*Создать коллекцию в Postman для Todo List, в которой будет 7 методов.*_

2. ### _*Создать новый Environment умную заглушку в Mockoon для задач:*_

    - _*GET - запрос на получение списка задач, должен возвращаться массив из 3 задач;*_

    - _*Добавить правило для GET - запроса, если в запросе был передан заголовок result, со значением empty list заглушка должна вернуть пустой массив;*_

    - _*Добавить правило для POST - запроса, если title новой задачи содержит слово «ошибка», заглушка должна вернуть HTTP 500 и тело с указанием ошибки.*_

4. ### _*Проверить работоспособность заглушки.*_

>![Typing SVG](https://readme-typing-svg.herokuapp.com?color=F7F4F1EE&lines=My+practice+⬇️&font=Fira+Code&size=18&pause=1000)

- ### __*Mockoon & Postman*__
    ### _*[Watch the video](https://youtu.be/m5Iq1JlP1zE)*_

- ### _*Collection in Postman for Todo List*_

```
{
 "info": {
  "_postman_id": "67525288-0bcf-4876-8228-4afcc657289a",
  "name": "Todo List",
  "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json",
  "_exporter_id": "20998045"
 },
 "item": [
  {
   "name": "Получения списка задач",
   "item": [
    {
     "name": "Отобразилася cписк задач",
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
       "raw": "{{Port}}",
       "host": [
        "{{Port}}"
       ]
      }
     },
     "response": []
    }
   ]
  },
  {
   "name": "Добавления задачи",
   "item": [
    {
     "name": "Добавления задачи",
     "event": [
      {
       "listen": "test",
       "script": {
        "exec": [
         "var key = \"Id_1\"\r",
         "var value = pm.response.json().id\r",
         "pm.collectionVariables.set(key,value)\r",
         "\r",
         "pm.test(\"Status code is 200\", function () {\r",
         "    pm.response.to.have.status(201);\r",
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
       "raw": "{\r\n    \"title\":\"error\",\r\n    \"completed\": false\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{Port}}",
       "host": [
        "{{Port}}"
       ]
      }
     },
     "response": []
    }
   ]
  },
  {
   "name": "В списке задач отобразилась новая задача",
   "item": [
    {
     "name": "Отобразилась новая задача",
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
       "raw": "{{BaseUrl}}",
       "host": [
        "{{BaseUrl}}"
       ]
      }
     },
     "response": []
    }
   ]
  },
  {
   "name": "Отредактировать задачу",
   "item": [
    {
     "name": "Отредактировать задачу",
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
      "method": "PATCH",
      "header": [],
      "body": {
       "mode": "raw",
       "raw": "{\r\n    \"title\":\"A new day\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseUrl}}{{Id_1}}",
       "host": [
        "{{BaseUrl}}{{Id_1}}"
       ]
      }
     },
     "response": []
    }
   ]
  },
  {
   "name": "Отметить задачу выполненой",
   "item": [
    {
     "name": "Задача выполнена",
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
      "method": "PATCH",
      "header": [],
      "body": {
       "mode": "raw",
       "raw": "{\r\n    \"completed\":true\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseUrl}}{{Id_1}}",
       "host": [
        "{{BaseUrl}}{{Id_1}}"
       ]
      }
     },
     "response": []
    }
   ]
  },
  {
   "name": "Удалить задачу",
   "item": [
    {
     "name": "Удалить задачу",
     "request": {
      "method": "DELETE",
      "header": [],
      "url": {
       "raw": "{{BaseUrl}}{{Id_1}}",
       "host": [
        "{{BaseUrl}}{{Id_1}}"
       ]
      }
     },
     "response": []
    }
   ]
  },
  {
   "name": "В обнавленном списке задачи больше нет",
   "item": [
    {
     "name": "Задачи больше нет",
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
       "raw": "https://todo-app-sky.herokuapp.com/",
       "protocol": "https",
       "host": [
        "todo-app-sky",
        "herokuapp",
        "com"
       ],
       "path": [
        ""
       ]
      }
     },
     "response": []
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
     "pm.test(\"Status code is 200\", function () {",
     "    pm.response.to.have.status(200);",
     "});"
    ]
   }
  }
 ],
 "variable": [
  {
   "key": "BaseUrl",
   "value": "https://todo-app-sky.herokuapp.com/"
  },
  {
   "key": "Id_1",
   "value": ""
  },
  {
   "key": "Port",
   "value": "http://localhost:3000",
   "type": "string"
  }
 ]
}
```
<!--end  -->

- # _*Mockoon*_

<!--start -->
```
{
  "uuid": "92dc1477-6d24-44a7-8f3a-0a16aaadb18c",
  "lastMigration": 24,
  "name": "Todo List",
  "endpointPrefix": "",
  "latency": 0,
  "port": 3000,
  "hostname": "0.0.0.0",
  "routes": [
    {
      "uuid": "b0049a3b-c7ed-47c3-bb0c-c0945a6d3481",
      "documentation": "",
      "method": "get",
      "endpoint": "",
      "responses": [
        {
          "uuid": "26aa7c8d-cb4c-4002-8061-b13f60af303f",
          "body": "\r\n    [{\r\n            \"id\": 60463,\r\n            \"title\": \"A new day, new knowledge \",\r\n            \"completed\": false,\r\n            \"order\": null,\r\n            \"url\": \"/60463\"\r\n        },\r\n        {\r\n            \"id\": 60464,\r\n            \"title\": \"Success goes with me through life\",\r\n            \"completed\": false,\r\n            \"order\": null,\r\n            \"url\": \"/60464\"\r\n        },\r\n        {\r\n            \"id\": 60465,\r\n            \"title\": \"I believe in myself and my strength \",\r\n            \"completed\": false,\r\n            \"order\": null,\r\n            \"url\": \"/60465\"\r\n        }\r\n    ]",
          "latency": 0,
          "statusCode": 200,
          "label": "Массив из 3 задач",
          "headers": [],
          "bodyType": "INLINE",
          "filePath": "",
          "databucketID": "",
          "sendFileAsBody": false,
          "rules": [],
          "rulesOperator": "OR",
          "disableTemplating": false,
          "fallbackTo404": false,
          "default": true
        },
        {
          "uuid": "e66ad093-8b15-4d12-933a-512ce0246a03",
          "body": "{}",
          "latency": 0,
          "statusCode": 200,
          "label": "Пустой массив",
          "headers": [],
          "bodyType": "INLINE",
          "filePath": "",
          "databucketID": "",
          "sendFileAsBody": false,
          "rules": [
            {
              "target": "header",
              "modifier": "result",
              "value": "empty",
              "invert": false,
              "operator": "equals"
            }
          ],
          "rulesOperator": "OR",
          "disableTemplating": false,
          "fallbackTo404": false,
          "default": false
        }
      ],
      "enabled": true,
      "responseMode": null
    },
    {
      "uuid": "f618a6d8-0174-4681-8998-4b9c684b7506",
      "documentation": "",
      "method": "post",
      "endpoint": "",
      "responses": [
        {
          "uuid": "4186e12b-7559-4b85-8e84-75f8c8089d60",
          "body": "{\n  \"title\":\"error\"\n}",
          "latency": 0,
          "statusCode": 500,
          "label": "",
          "headers": [],
          "bodyType": "INLINE",
          "filePath": "",
          "databucketID": "",
          "sendFileAsBody": false,
          "rules": [],
          "rulesOperator": "OR",
          "disableTemplating": false,
          "fallbackTo404": false,
          "default": true
        }
      ],
      "enabled": true,
      "responseMode": null
    }
  ],
  "proxyMode": false,
  "proxyHost": "",
  "proxyRemovePrefix": false,
  "tlsOptions": {
    "enabled": false,
    "type": "CERT",
    "pfxPath": "",
    "certPath": "",
    "keyPath": "",
    "caPath": "",
    "passphrase": ""
  },
  "cors": true,
  "headers": [
    {
      "key": "Content-Type",
      "value": "application/json"
    }
  ],
  "proxyReqHeaders": [
    {
      "key": "",
      "value": ""
    }
  ],
  "proxyResHeaders": [
    {
      "key": "",
      "value": ""
    }
  ],
  "data": []
}
```
<!--end -->
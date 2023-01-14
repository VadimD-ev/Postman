
![soft](https://capsule-render.vercel.app/api?type=soft&color=fe895f&text=POSTMAN&fontSize=50&animation=twinkling)

- ## __*Задание:*__

<!--start -->
1. ### _*Создать коллекцию в Postman для Trello.*_

2. ### _*Всю необходимую информацию брать из консоли разработчика.*_

> ### [*_В документации вы найдете необходимую информацию для создания сущностей._*](https://developer.atlassian.com/cloud/trello/rest/api-group-actions/)
  
      1. Board. Use the following methods:  
      -Create a Board,
      -Get a Board, 
      -Delete a Board.

      2. Lists. Use the following methods:  
      -Create a new List,
      -Get a List.
      
      3. Cards. Use the following methods:  
      -Create a new Card,
      -Delete a Card,
      -Update a Card,
      -Update a Card "list",
      -Get a Card,
      -Add a new comment to a Card.

3. ### _*Id каждой новой сущности (доска, список, карточка, комментарий) должен сохраняться как параметр в коллекции.*_

![Typing SVG](https://readme-typing-svg.herokuapp.com?color=F7F4F1EE&lines=Practice+task⮯&font=Fira+Code&size=16&pause=1000)
- ## _*Collection in Postman for Trello*_
```
{
 "info": {
  "_postman_id": "59c35df5-872c-4850-b680-a2c951527a7a",
  "name": "Trello",
  "schema": "https://schema.getpostman.com/json/collection/v2.1.0/collection.json",
  "_exporter_id": "20998045"
 },
 "item": [
  {
   "name": "Create",
   "item": [
    {
     "name": "Creat Board",
     "event": [
      {
       "listen": "test",
       "script": {
        "exec": [
         "var key = \"IdBoard\"\r",
         "var value = pm.response.json().id\r",
         "pm.collectionVariables.set(key, value)\r",
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
        "value": "{{token}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n    \"name\": \"{{$randomAdjective}}\",\r\n    \"token\": \"{{token}}\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseURL}}/boards/",
       "host": [
        "{{BaseURL}}"
       ],
       "path": [
        "boards",
        ""
       ]
      }
     },
     "response": []
    },
    {
     "name": "Creat List 1",
     "event": [
      {
       "listen": "test",
       "script": {
        "exec": [
         "var key = \"IdList 1\"\r",
         "var value = pm.response.json().id\r",
         "pm.collectionVariables.set(key, value)\r",
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
        "value": "token={{token}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n    \"name\": \"{{$randomAdjective}}\",\r\n    \"idBoard\": \"{{IdBoard}}\",\r\n    \"token\": \"{{token}}\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseURL}}/lists/",
       "host": [
        "{{BaseURL}}"
       ],
       "path": [
        "lists",
        ""
       ]
      }
     },
     "response": []
    },
    {
     "name": "Creat List 2",
     "event": [
      {
       "listen": "test",
       "script": {
        "exec": [
         "var key = \"IdList 2\"\r",
         "var value = pm.response.json().id\r",
         "pm.collectionVariables.set(key, value)\r",
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
        "value": "token={{token}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n    \"name\": \"{{$randomAbbreviation}}\",\r\n    \"idBoard\": \"{{IdBoard}}\",\r\n    \"token\": \"{{token}}\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseURL}}/lists/",
       "host": [
        "{{BaseURL}}"
       ],
       "path": [
        "lists",
        ""
       ]
      }
     },
     "response": []
    },
    {
     "name": "Creat Card",
     "event": [
      {
       "listen": "test",
       "script": {
        "exec": [
         "var key = \"idCard\"\r",
         "var value = pm.response.json().id\r",
         "pm.collectionVariables.set(key, value)\r",
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
        "value": "token={{token}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n    \"idList\": \"{{idList 1}}\",\r\n    \"name\": \"{{$randomCompanyName}}\",  \r\n    \"token\": \"{{token}}\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseURL}}/cards/",
       "host": [
        "{{BaseURL}}"
       ],
       "path": [
        "cards",
        ""
       ]
      }
     },
     "response": []
    },
    {
     "name": "Add Comment",
     "event": [
      {
       "listen": "test",
       "script": {
        "exec": [
         "var key = \"idComment\"\r",
         "var value = pm.response.json().id\r",
         "pm.collectionVariables.set(key, value)\r",
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
        "value": "token={{token}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n    \"text\": \"{{$randomCatchPhrase}}\",  \r\n    \"token\": \"{{token}}\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseURL}}/cards/{{idCard}}/actions/comments",
       "host": [
        "{{BaseURL}}"
       ],
       "path": [
        "cards",
        "{{idCard}}",
        "actions",
        "comments"
       ]
      }
     },
     "response": []
    }
   ]
  },
  {
   "name": "View",
   "item": [
    {
     "name": "Get Board",
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
      "header": [
       {
        "key": "Cookie",
        "value": "token={{token}}",
        "type": "text"
       }
      ],
      "url": {
       "raw": "{{BaseURL}}/boards/{{IdBoard}}/",
       "host": [
        "{{BaseURL}}"
       ],
       "path": [
        "boards",
        "{{IdBoard}}",
        ""
       ]
      }
     },
     "response": []
    },
    {
     "name": "Get List",
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
      "header": [
       {
        "key": "Cookie",
        "value": "token={{token}}",
        "type": "text"
       }
      ],
      "url": {
       "raw": "{{BaseURL}}/lists/{{idList 1}}/",
       "host": [
        "{{BaseURL}}"
       ],
       "path": [
        "lists",
        "{{idList 1}}",
        ""
       ]
      }
     },
     "response": []
    },
    {
     "name": "Get Card",
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
      "header": [
       {
        "key": "Cookie",
        "value": "token={{token}}",
        "type": "text"
       }
      ],
      "url": {
       "raw": "{{BaseURL}}/cards/{{idCard}}/",
       "host": [
        "{{BaseURL}}"
       ],
       "path": [
        "cards",
        "{{idCard}}",
        ""
       ]
      }
     },
     "response": []
    }
   ]
  },
  {
   "name": "Update",
   "item": [
    {
     "name": "Update Card",
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
      "method": "PUT",
      "header": [
       {
        "key": "Cookie",
        "value": "token={{token}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n    \"name\": \"{{$randomUserName}}\",\r\n    \"token\": \"{{token}}\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseURL}}/cards/{{idCard}}/",
       "host": [
        "{{BaseURL}}"
       ],
       "path": [
        "cards",
        "{{idCard}}",
        ""
       ]
      }
     },
     "response": []
    },
    {
     "name": "Update Card list",
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
      "method": "PUT",
      "header": [
       {
        "key": "Cookie",
        "value": "token={{token}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n    \"idList\": \"{{idList 2}}\",\r\n    \"token\": \"{{token}}\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseURL}}/cards/{{idCard}}",
       "host": [
        "{{BaseURL}}"
       ],
       "path": [
        "cards",
        "{{idCard}}"
       ]
      }
     },
     "response": []
    }
   ]
  },
  {
   "name": "Delete",
   "item": [
    {
     "name": "Delete Cards",
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
      "header": [
       {
        "key": "Cookie",
        "value": "token={{token}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n    \"id\": \"{{idCard}}\",\r\n    \"token\": \"{{token}}\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseURL}}/cards/{{idCard}}",
       "host": [
        "{{BaseURL}}"
       ],
       "path": [
        "cards",
        "{{idCard}}"
       ]
      }
     },
     "response": []
    },
    {
     "name": "Delete Board",
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
      "header": [
       {
        "key": "Cookie",
        "value": "token={{token}}",
        "type": "text"
       }
      ],
      "body": {
       "mode": "raw",
       "raw": "{\r\n    \"id\": \"{{IdBoard}}\",\r\n    \"token\": \"{{token}}\"\r\n}",
       "options": {
        "raw": {
         "language": "json"
        }
       }
      },
      "url": {
       "raw": "{{BaseURL}}/boards/{{IdBoard}}",
       "host": [
        "{{BaseURL}}"
       ],
       "path": [
        "boards",
        "{{IdBoard}}"
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
   "key": "BaseURL",
   "value": "https://trello.com/1/",
   "type": "string"
  },
  {
   "key": "token",
   "value": "token=\t",
   "type": "string"
  },
  {
   "key": "IdBoard",
   "value": "",
   "type": "string"
  },
  {
   "key": "idList 1",
   "value": "",
   "type": "string"
  },
  {
   "key": "idList 2",
   "value": "",
   "type": "string"
  },
  {
   "key": "idCard",
   "value": "",
   "type": "string"
  },
  {
   "key": "idComment",
   "value": "",
   "type": "string"
  },
  {
   "key": "IdList 1",
   "value": ""
  },
  {
   "key": "IdList 2",
   "value": ""
  }
 ]
}
```
<!--end-->
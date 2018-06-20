{
  "info": {
    "name": "Swagger Hub Registry Deletes the specified API",
    "_postman_id": "d951a9ee-7481-4840-8a39-242907d03deb",
    "description": "Deletes the specified api.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "APIs",
      "item": [
        {
          "id": "cfe88f31-f010-4230-ae51-a6f8db0b3cad",
          "name": "searchApis",
          "request": {
            "url": "http://api.swaggerhub.com/apis?limit=%7B%7D&order=%7B%7D&page=%7B%7D&query=%7B%7D&sort=%7B%7D&state=%7B%7D&tag=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Retrieves a list of currently defined apis in apis.json format.."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "75ec1b10-4c16-4d78-aff4-54bb74b72320"
            }
          ]
        },
        {
          "id": "18d73a10-c002-4f06-9b6e-93d13bc919b6",
          "name": "getOwnerApis",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.swaggerhub.com",
              "path": [
                "apis/:owner"
              ],
              "query": [
                {
                  "key": "limit",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "order",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "page",
                  "value": "%7B%7D",
                  "disabled": false
                },
                {
                  "key": "sort",
                  "value": "%7B%7D",
                  "disabled": false
                }
              ],
              "variable": [
                {
                  "id": "owner",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Retrieves an apis.json listing of all apis defined for this owner."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "12aaae92-9a0f-4d37-8cde-7bc58559976c"
            }
          ]
        },
        {
          "id": "81216870-3701-4140-890e-862baa261cb8",
          "name": "deleteApi",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.swaggerhub.com",
              "path": [
                "apis/:owner/:api"
              ],
              "variable": [
                {
                  "id": "api",
                  "value": "{}",
                  "type": "string"
                },
                {
                  "id": "owner",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "DELETE",
            "body": {
              "mode": "raw"
            },
            "description": "Deletes the specified api."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "da1cce3a-a0a5-416e-8c15-c5d879b4201b"
            }
          ]
        }
      ]
    }
  ]
}
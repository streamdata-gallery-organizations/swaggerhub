{
  "info": {
    "name": "Swagger Hub Registry Retrieves an APIs.json listing of all APIs defined for this owner",
    "_postman_id": "171ed00e-972c-4cab-a3ad-741524eb48ff",
    "description": "Retrieves an apis.json listing of all apis defined for this owner.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "APIs",
      "item": [
        {
          "id": "f95fab33-a407-4429-b861-30542ed37e23",
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
              "id": "7500c90c-d90d-491a-a95d-c5b0fd54a49a"
            }
          ]
        },
        {
          "id": "a5493547-e2a3-46f3-8f0b-b3507f7a81c3",
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
              "id": "0b8ee456-ba79-420e-adf9-efecd1735332"
            }
          ]
        }
      ]
    }
  ]
}
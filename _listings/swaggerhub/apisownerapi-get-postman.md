{
  "info": {
    "name": "Swagger Hub Registry Retrieves an APIs.json listing for all API versions for this owner and API",
    "_postman_id": "2f4a2676-9ad4-45fb-a681-8f52ac5273da",
    "description": "Retrieves an apis.json listing for all api versions for this owner and api.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "APIs",
      "item": [
        {
          "id": "5d066f47-326b-47ca-8277-6bdd864f1360",
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
              "id": "7e1f7ae1-8674-4dc9-96e0-84cfc6e1a4d3"
            }
          ]
        },
        {
          "id": "4ecd860e-d236-4d0e-acf1-e1741da230b0",
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
              "id": "a56e24a3-80a1-4463-b3b8-927a3c6d7560"
            }
          ]
        },
        {
          "id": "563efea0-3bfb-4ad0-848d-91bed15c4189",
          "name": "getApiVersions",
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
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Retrieves an apis.json listing for all api versions for this owner and api."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "e6b128f9-8501-430e-a369-4b500d1495e9"
            }
          ]
        },
        {
          "id": "243d2a27-1583-4a5b-a147-165493bd64e7",
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
              "id": "9760edb2-1f6a-4322-ad9f-338bc49cf351"
            }
          ]
        }
      ]
    }
  ]
}
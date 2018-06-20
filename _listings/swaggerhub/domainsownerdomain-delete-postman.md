{
  "info": {
    "name": "Swagger Hub Registry Deletes the specified domain",
    "_postman_id": "d4e99fdb-093d-427a-9892-edfb08794781",
    "description": "Deletes the specified domain.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Domains",
      "item": [
        {
          "id": "97d85871-54f3-4a7a-a4bf-cd29b4da731a",
          "name": "searchDomains",
          "request": {
            "url": "http://api.swaggerhub.com/domains?limit=%7B%7D&order=%7B%7D&page=%7B%7D&query=%7B%7D&sort=%7B%7D&state=%7B%7D&tag=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Retrieves a list of currently defined domains in apis.json format."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "f468ce96-dc20-4330-9787-26159a17ba96"
            }
          ]
        },
        {
          "id": "7a5570ea-723e-46de-9625-49dcb3d4e20b",
          "name": "getOwnerDomains",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.swaggerhub.com",
              "path": [
                "domains/:owner"
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
            "description": "Retrieves an apis.json listing of all domains defined for this owner."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "f0e28da8-ef2a-4dba-8807-ac6f75ee8647"
            }
          ]
        },
        {
          "id": "b7c0e9fa-1809-43a7-9cdb-6e2a7e73e477",
          "name": "deleteDomain",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.swaggerhub.com",
              "path": [
                "domains/:owner/:domain"
              ],
              "query": [
                {
                  "key": "force",
                  "value": "%7B%7D",
                  "disabled": false
                }
              ],
              "variable": [
                {
                  "id": "domain",
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
            "description": "Deletes the specified domain."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "f0c3241e-edd3-4fd4-95a3-45f6f2c35f12"
            }
          ]
        }
      ]
    }
  ]
}
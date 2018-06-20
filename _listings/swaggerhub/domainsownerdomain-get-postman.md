{
  "info": {
    "name": "Swagger Hub Registry Retrieves an APIs.json listing for all domain versions for this owner and domain",
    "_postman_id": "a44bce85-5a3c-452a-afd0-9fc256c7318a",
    "description": "Retrieves an apis.json listing for all domain versions for this owner and domain.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Domains",
      "item": [
        {
          "id": "e7cb9bd6-1650-4bb4-8d02-40e1b1c55eb6",
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
              "id": "acc60d04-273e-440d-8013-d81482cc473e"
            }
          ]
        },
        {
          "id": "34ddcb40-c74a-41dc-ae5b-b0701a766d2b",
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
              "id": "3ff6f364-80b0-43c5-af59-46deb686a6e8"
            }
          ]
        },
        {
          "id": "6da31a17-158c-40f9-ba27-ab9a468201d7",
          "name": "getDomainVersions",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.swaggerhub.com",
              "path": [
                "domains/:owner/:domain"
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
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Retrieves an apis.json listing for all domain versions for this owner and domain."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "5af34490-9a4c-4f08-9154-e17140f69c81"
            }
          ]
        },
        {
          "id": "6f9758a1-9a88-422c-9105-512458019388",
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
              "id": "d5c0f2dd-8c44-4d2a-950b-9b0fefab9611"
            }
          ]
        }
      ]
    }
  ]
}
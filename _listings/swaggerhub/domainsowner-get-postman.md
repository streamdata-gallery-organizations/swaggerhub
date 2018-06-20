{
  "info": {
    "name": "Swagger Hub Registry Retrieves an APIs.json listing of all domains defined for this owner",
    "_postman_id": "78026b21-140c-4f51-b1b0-38b220a90720",
    "description": "Retrieves an apis.json listing of all domains defined for this owner.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Domains",
      "item": [
        {
          "id": "ebfb6a5b-b141-4c17-adf1-4ba174e360d2",
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
              "id": "2a1e0930-c1ff-46e5-a3e9-2147fb05cf9d"
            }
          ]
        },
        {
          "id": "46740288-2ed5-4761-b851-107cc5aa57a8",
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
              "id": "9607abb1-8db6-4a28-84b1-3148d2b96a70"
            }
          ]
        }
      ]
    }
  ]
}
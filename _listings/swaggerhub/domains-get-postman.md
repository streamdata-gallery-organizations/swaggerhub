{
  "info": {
    "name": "Swagger Hub Registry Retrieves a list of currently defined domains in APIs.json format",
    "_postman_id": "30b5aed1-c709-45d5-8847-dcc697b0ef72",
    "description": "Retrieves a list of currently defined domains in apis.json format.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Domains",
      "item": [
        {
          "id": "6e691efe-7177-495a-aff7-19bddc0a48d4",
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
              "id": "2788c41d-edd6-4dc2-81c5-6f80ca0d5ca6"
            }
          ]
        }
      ]
    }
  ]
}
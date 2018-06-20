{
  "info": {
    "name": "Swagger Hub Registry Retrieves a list of currently defined APIs in APIs.json format.",
    "_postman_id": "b4bf2e54-cc1b-423a-979f-81071ba283fa",
    "description": "Retrieves a list of currently defined apis in apis.json format..",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "APIs",
      "item": [
        {
          "id": "e5327fd2-8373-4cdd-b8f1-b875b8be4508",
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
              "id": "cc7393bb-0b63-477b-b058-8b26d4a4a82e"
            }
          ]
        }
      ]
    }
  ]
}
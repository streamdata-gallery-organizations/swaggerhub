{
  "info": {
    "name": "Swagger Hub Registry Renames API",
    "_postman_id": "239b4f3e-d2f1-43b5-8f47-17aefeeb2ef6",
    "description": "Renames api.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "APIs",
      "item": [
        {
          "id": "a6841b78-5da5-42c7-8bb6-05777e7a41ab",
          "name": "renameApi",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.swaggerhub.com",
              "path": [
                "apis/:owner/:api/.newname"
              ],
              "query": [
                {
                  "key": "newName",
                  "value": "%7B%7D",
                  "disabled": false
                }
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
            "method": "POST",
            "body": {
              "mode": "raw"
            },
            "description": "Renames api."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "a8537e47-60cd-4957-aa66-7199a4e55d8f"
            }
          ]
        }
      ]
    }
  ]
}
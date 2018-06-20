{
  "info": {
    "name": "Swagger Hub Registry Returns the list of comments for the specified API",
    "_postman_id": "cf5bd046-d902-4b72-84a8-1b382b934133",
    "description": "Returns the list of comments for the specified api.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "APIs",
      "item": [
        {
          "id": "308f4672-26bd-41c9-af66-42e5eacb5939",
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
              "id": "38dd57c1-bdff-42c6-8f53-8d42d03910c8"
            }
          ]
        },
        {
          "id": "00d25a24-d790-4bc5-832e-700d89d60645",
          "name": "getApiComments",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.swaggerhub.com",
              "path": [
                "apis/:owner/:api/:version/.comment"
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
                },
                {
                  "id": "version",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Returns the list of comments for the specified api."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "ca4fcd32-0307-4f0b-9810-19e409eb6293"
            }
          ]
        }
      ]
    }
  ]
}
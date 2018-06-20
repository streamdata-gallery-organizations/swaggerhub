{
  "info": {
    "name": "Swagger Hub Registry Retrieves a list of all available plugins (ignore system plugins)",
    "_postman_id": "02b86e80-2bb8-47ba-8ba0-ea175f875710",
    "description": "Retrieves a list of all available plugins (ignore system plugins).",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Plugins",
      "item": [
        {
          "id": "443d637b-f402-4a29-903c-fa11f8a7cae5",
          "name": "getAvailablePlugins",
          "request": {
            "url": "http://api.swaggerhub.com/plugins",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Retrieves a list of all available plugins (ignore system plugins)."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "68e98c01-db07-40ca-8f3f-8757fb2fd080"
            }
          ]
        }
      ]
    }
  ]
}
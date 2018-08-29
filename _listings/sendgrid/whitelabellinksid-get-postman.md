{
  "info": {
    "name": "SendGrid Get Whitelabel Links",
    "_postman_id": "eab2795b-9491-451e-be8e-55e2a1a4d437",
    "description": "**This endpoint allows you to retrieve a specific link whitelabel.**\n\nEmail link whitelabels allow all of the click-tracked links you send in your emails to include the URL of your domain instead of sendgrid.net.\n\nFor more information, please see our [User Guide](https://sendgrid.com/docs/API_Reference/Web_API_v3/Whitelabel/links.html).",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "email",
      "item": [
        {
          "id": "93d92e1d-25fa-4b21-b530-28cb10506427",
          "name": "whitelabel.links.id.get",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.sendgrid.com",
              "path": [
                "v3",
                "whitelabel/links/:id"
              ],
              "query": [
                {
                  "key": "No Name",
                  "value": "%7B%7D",
                  "disabled": false
                }
              ],
              "variable": [
                {
                  "id": "id",
                  "value": "id",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "**This endpoint allows you to retrieve a specific link whitelabel"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "0d6de580-ee84-4049-8aac-caed6232d84c"
            }
          ]
        }
      ]
    }
  ]
}
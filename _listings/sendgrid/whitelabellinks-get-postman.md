{
  "info": {
    "name": "SendGrid Get Whitelabel Links",
    "_postman_id": "fc15bf3c-52a2-4eaa-9325-d4d1d04b88f6",
    "description": "**This endpoint allows you to retrieve all link whitelabels.**\n\nEmail link whitelabels allow all of the click-tracked links you send in your emails to include the URL of your domain instead of sendgrid.net.\n\nFor more information, please see our [User Guide](https://sendgrid.com/docs/API_Reference/Web_API_v3/Whitelabel/links.html).",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "email",
      "item": [
        {
          "id": "4109ed8e-5777-4c52-8b67-e5ebc25eac86",
          "name": "whitelabel.links.get",
          "request": {
            "url": "http://api.sendgrid.com/v3/whitelabel/links?limit=%7B%7D&No Name=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "**This endpoint allows you to retrieve all link whitelabels"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "901aac20-eb30-4629-b8e3-3b39802523ef"
            }
          ]
        }
      ]
    }
  ]
}
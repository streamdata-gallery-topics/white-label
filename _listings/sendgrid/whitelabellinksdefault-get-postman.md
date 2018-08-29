{
  "info": {
    "name": "SendGrid Get Whitelabel Links Default",
    "_postman_id": "90c13519-3356-4578-afba-9e4989955db4",
    "description": "**This endpoint allows you to retrieve the default link whitelabel.**\n\nDefault link whitelabel is the actual link whitelabel to be used when sending messages. If there are multiple link whitelabels, the default is determined by the following order:\n<ul>\n  <li>Validated link whitelabels marked as \"default\"</li>\n  <li>Legacy link whitelabels (migrated from the whitelabel wizard)</li>\n  <li>Default SendGrid link whitelabel (i.e. 100.ct.sendgrid.net)</li>\n</ul>\n\nEmail link whitelabels allow all of the click-tracked links you send in your emails to include the URL of your domain instead of sendgrid.net.\n\nFor more information, please see our [User Guide](https://sendgrid.com/docs/API_Reference/Web_API_v3/Whitelabel/links.html).",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "email",
      "item": [
        {
          "id": "e5d7a08a-ed95-447e-8889-603936828080",
          "name": "whitelabel.links.default.get",
          "request": {
            "url": "http://api.sendgrid.com/v3/whitelabel/links/default?domain=%7B%7D&No Name=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "**This endpoint allows you to retrieve the default link whitelabel"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "29fb9344-81ac-4d9a-99b9-dbe6db150af5"
            }
          ]
        }
      ]
    }
  ]
}
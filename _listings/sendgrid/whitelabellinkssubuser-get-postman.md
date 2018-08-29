{
  "info": {
    "name": "SendGrid Get Whitelabel Links Subuser",
    "_postman_id": "ac32e88a-ad95-45ca-aa45-c12583339661",
    "description": "**This endpoint allows you to retrieve the associated link whitelabel for a subuser.**\n\nLink whitelables can be associated with subusers from the parent account. This functionality allows\nsubusers to send mail using their parent's linke whitelabels. To associate a link whitelabel, the parent account\nmust first create a whitelabel and validate it. The parent may then associate that whitelabel with a subuser via the API or the Subuser Management page in the user interface.\n\nEmail link whitelabels allow all of the click-tracked links you send in your emails to include the URL of your domain instead of sendgrid.net.\n\nFor more information, please see our [User Guide](https://sendgrid.com/docs/API_Reference/Web_API_v3/Whitelabel/links.html).",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "email",
      "item": [
        {
          "id": "26d99d76-cfd8-4d20-bbc1-fe2d78eba958",
          "name": "whitelabel.links.subuser.get",
          "request": {
            "url": "http://api.sendgrid.com/v3/whitelabel/links/subuser?No Name=%7B%7D&username=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "**This endpoint allows you to retrieve the associated link whitelabel for a subuser"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "ec2d1813-0afd-4c1b-a007-946aa5c6c02b"
            }
          ]
        }
      ]
    }
  ]
}
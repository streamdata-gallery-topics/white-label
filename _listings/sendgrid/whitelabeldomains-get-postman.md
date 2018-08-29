{
  "info": {
    "name": "SendGrid Get Whitelabel Domains",
    "_postman_id": "10623b43-51ed-487b-876e-814bea6d5883",
    "description": "**This endpoint allows you to retrieve a list of all domain whitelabels you have created.**\n\nA domain whitelabel allows you to remove the ???via??? or ???sent on behalf of??? message that your recipients see when they read your emails. Whitelabeling a domain allows you to replace sendgrid.net with your personal sending domain. You will be required to create a subdomain so that SendGrid can generate the DNS records which you must give to your host provider. If you choose to use Automated Security, SendGrid will provide you with 3 CNAME records. If you turn Automated Security off, you will be given 2 TXT records and 1 MX record.\n\nFor more information on whitelabeling, please see our [User Guide](https://sendgrid.com/docs/User_Guide/Settings/Whitelabel/index.html)",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "email",
      "item": [
        {
          "id": "05b693c3-9a31-4042-8a3d-c60c0fcdcb9a",
          "name": "whitelabel.domains.get",
          "request": {
            "url": "http://api.sendgrid.com/v3/whitelabel/domains?domain=%7B%7D&exclude_subusers=%7B%7D&limit=%7B%7D&No Name=%7B%7D&offset=%7B%7D&username=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "**This endpoint allows you to retrieve a list of all domain whitelabels you have created"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "f5054a41-6309-4604-82d8-8c7a76f0ce9f"
            }
          ]
        }
      ]
    }
  ]
}
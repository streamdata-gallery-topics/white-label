{
  "info": {
    "name": "SendGrid Get Whitelabel Domains Default",
    "_postman_id": "88d44616-5507-4587-afcb-600736b99b3b",
    "description": "**This endpoint allows you to retrieve the default whitelabel for a domain.**\n\nA domain whitelabel allows you to remove the ???via??? or ???sent on behalf of??? message that your recipients see when they read your emails. Whitelabeling a domain allows you to replace sendgrid.net with your personal sending domain. You will be required to create a subdomain so that SendGrid can generate the DNS records which you must give to your host provider. If you choose to use Automated Security, SendGrid will provide you with 3 CNAME records. If you turn Automated Security off, you will be given 2 TXT records and 1 MX record.\n\nFor more information on whitelabeling, please see our [User Guide](https://sendgrid.com/docs/User_Guide/Settings/Whitelabel/index.html)\n\n## URI Parameters\n| URI Parameter   | Type   | Description  |\n|---|---|---|\n| domain | string  |The domain to find a default domain whitelabel for. |",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "email",
      "item": [
        {
          "id": "568f9d7c-7831-4235-8af5-24ab970f89cd",
          "name": "whitelabel.domains.default.get",
          "request": {
            "url": "http://api.sendgrid.com/v3/whitelabel/domains/default?No Name=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "**This endpoint allows you to retrieve the default whitelabel for a domain"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "1d17692c-7021-4c61-8be6-927d90a644c5"
            }
          ]
        }
      ]
    }
  ]
}
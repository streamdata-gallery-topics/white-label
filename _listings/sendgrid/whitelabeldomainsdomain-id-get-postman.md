{
  "info": {
    "name": "SendGrid Get Whitelabel Domains Domain",
    "_postman_id": "f36ab241-57da-41c3-bd94-9c67e6cc3dc1",
    "description": "**This endpoint allows you to retrieve a specific domain whitelabel.**\n\nA domain whitelabel allows you to remove the ???via??? or ???sent on behalf of??? message that your recipients see when they read your emails. Whitelabeling a domain allows you to replace sendgrid.net with your personal sending domain. You will be required to create a subdomain so that SendGrid can generate the DNS records which you must give to your host provider. If you choose to use Automated Security, SendGrid will provide you with 3 CNAME records. If you turn Automated Security off, you will be given 2 TXT records and 1 MX record.\n\nFor more information on whitelabeling, please see our [User Guide](https://sendgrid.com/docs/User_Guide/Settings/Whitelabel/index.html)",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "email",
      "item": [
        {
          "id": "a2def682-18c0-4afa-870e-00e4f5e0c6f9",
          "name": "whitelabel.domains.domain_id.get",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.sendgrid.com",
              "path": [
                "v3",
                "whitelabel/domains/:domain_id"
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
                  "id": "domain_id",
                  "value": "domain_id",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "**This endpoint allows you to retrieve a specific domain whitelabel"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "08e431a5-351a-4c0d-a71e-e0ebb2cce46c"
            }
          ]
        }
      ]
    }
  ]
}
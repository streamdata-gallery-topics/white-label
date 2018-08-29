{
  "info": {
    "name": "SendGrid Get Whitelabel Domains Subuser",
    "_postman_id": "b607f821-7d69-47d6-a783-2f08947eaa87",
    "description": "**This endpoint allows you to retrieve all of the whitelabels that have been assigned to a specific subuser.**\n\nA domain whitelabel allows you to remove the ???via??? or ???sent on behalf of??? message that your recipients see when they read your emails. Whitelabeling a domain allows you to replace sendgrid.net with your personal sending domain. You will be required to create a subdomain so that SendGrid can generate the DNS records which you must give to your host provider. If you choose to use Automated Security, SendGrid will provide you with 3 CNAME records. If you turn Automated Security off, you will be given 2 TXT records and 1 MX record.\n\nDomain whitelabels can be associated with (i.e. assigned to) subusers from a parent account. This functionality allows subusers to send mail using their parent's whitelabels. To associate a whitelabel with a subuser, the parent account must first create the whitelabel and validate it. The the parent may then associate the whitelabel via the subuser management tools.\n\nFor more information on whitelabeling, please see our [User Guide](https://sendgrid.com/docs/User_Guide/Settings/Whitelabel/index.html)\n\n## URI Parameters\n| URI Parameter   | Type  | Description  |\n|---|---|---|\n| username | string  | Username of the subuser to find associated whitelabels for. |",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "email",
      "item": [
        {
          "id": "850da037-a49e-466d-96b9-0f9d59b70e26",
          "name": "whitelabel.domains.subuser.get",
          "request": {
            "url": "http://api.sendgrid.com/v3/whitelabel/domains/subuser?No Name=%7B%7D",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "**This endpoint allows you to retrieve all of the whitelabels that have been assigned to a specific subuser"
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "5c3795ee-9c14-4af9-ae15-83e3d040152a"
            }
          ]
        }
      ]
    }
  ]
}
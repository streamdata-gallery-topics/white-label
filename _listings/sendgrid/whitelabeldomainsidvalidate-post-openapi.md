---
swagger: "2.0"
x-collection-name: SendGrid
x-complete: 0
info:
  title: SendGrid Add Whitelabel Domains  Valate
  description: |-
    **This endpoint allows you to validate a domain whitelabel. If it fails, it will return an error message describing why the whitelabel could not be validated.**

    A domain whitelabel allows you to remove the ???via??? or ???sent on behalf of??? message that your recipients see when they read your emails. Whitelabeling a domain allows you to replace sendgrid.net with your personal sending domain. You will be required to create a subdomain so that SendGrid can generate the DNS records which you must give to your host provider. If you choose to use Automated Security, SendGrid will provide you with 3 CNAME records. If you turn Automated Security off, you will be given 2 TXT records and 1 MX record.

    For more information on whitelabeling, please see our [User Guide](https://sendgrid.com/docs/User_Guide/Settings/Whitelabel/index.html)

    ## URI Parameters
    | URI Parameter   | Type   | Description  |
    |---|---|---|
    | id | integer  |ID of the domain whitelabel to validate. |
  version: 1.0.0
host: api.sendgrid.com
basePath: /v3
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /whitelabel/domains:
    get:
      summary: Get Whitelabel Domains
      description: |-
        **This endpoint allows you to retrieve a list of all domain whitelabels you have created.**

        A domain whitelabel allows you to remove the ???via??? or ???sent on behalf of??? message that your recipients see when they read your emails. Whitelabeling a domain allows you to replace sendgrid.net with your personal sending domain. You will be required to create a subdomain so that SendGrid can generate the DNS records which you must give to your host provider. If you choose to use Automated Security, SendGrid will provide you with 3 CNAME records. If you turn Automated Security off, you will be given 2 TXT records and 1 MX record.

        For more information on whitelabeling, please see our [User Guide](https://sendgrid.com/docs/User_Guide/Settings/Whitelabel/index.html)
      operationId: whitelabel.domains.get
      x-api-path-slug: whitelabeldomains-get
      parameters:
      - in: query
        name: domain
        description: Search for domain whitelabels that match the given domain
      - in: query
        name: exclude_subusers
        description: Exclude subuser domains from the result
      - in: query
        name: limit
        description: Number of domains to return
      - in: query
        name: No Name
      - in: query
        name: offset
        description: Paging offset
      - in: query
        name: username
        description: The username associated with a whitelabel
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Domains
    post:
      summary: Add Whitelabel Domains
      description: |-
        **This endpoint allows you to create a whitelabel for one of your domains.**

        If you are creating a domain whitelabel that you would like a subuser to use, you have two options:
        1. Use the "username" parameter. This allows you to create a whitelabel on behalf of your subuser. This means the subuser is able to see and modify the created whitelabel.
        2. Use the Association workflow (see Associate Domain section). This allows you to assign a whitelabel created by the parent to a subuser. This means the subuser will default to the assigned whitelabel, but will not be able to see or modify that whitelabel. However, if the subuser creates their own whitelabel it will overwrite the assigned whitelabel.

        A domain whitelabel allows you to remove the ???via??? or ???sent on behalf of??? message that your recipients see when they read your emails. Whitelabeling a domain allows you to replace sendgrid.net with your personal sending domain. You will be required to create a subdomain so that SendGrid can generate the DNS records which you must give to your host provider. If you choose to use Automated Security, SendGrid will provide you with 3 CNAME records. If you turn Automated Security off, you will be given 2 TXT records and 1 MX record.

        For more information on whitelabeling, please see our [User Guide](https://sendgrid.com/docs/User_Guide/Settings/Whitelabel/index.html)
      operationId: whitelabel.domains.post
      x-api-path-slug: whitelabeldomains-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Domains
  /whitelabel/domains/default:
    get:
      summary: Get Whitelabel Domains Default
      description: |-
        **This endpoint allows you to retrieve the default whitelabel for a domain.**

        A domain whitelabel allows you to remove the ???via??? or ???sent on behalf of??? message that your recipients see when they read your emails. Whitelabeling a domain allows you to replace sendgrid.net with your personal sending domain. You will be required to create a subdomain so that SendGrid can generate the DNS records which you must give to your host provider. If you choose to use Automated Security, SendGrid will provide you with 3 CNAME records. If you turn Automated Security off, you will be given 2 TXT records and 1 MX record.

        For more information on whitelabeling, please see our [User Guide](https://sendgrid.com/docs/User_Guide/Settings/Whitelabel/index.html)

        ## URI Parameters
        | URI Parameter   | Type   | Description  |
        |---|---|---|
        | domain | string  |The domain to find a default domain whitelabel for. |
      operationId: whitelabel.domains.default.get
      x-api-path-slug: whitelabeldomainsdefault-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Domains
      - Default
  /whitelabel/domains/subuser:
    delete:
      summary: Delete Whitelabel Domains Subuser
      description: |-
        **This endpoint allows you to disassociate a specific whitelabel from a subuser.**

        A domain whitelabel allows you to remove the ???via??? or ???sent on behalf of??? message that your recipients see when they read your emails. Whitelabeling a domain allows you to replace sendgrid.net with your personal sending domain. You will be required to create a subdomain so that SendGrid can generate the DNS records which you must give to your host provider. If you choose to use Automated Security, SendGrid will provide you with 3 CNAME records. If you turn Automated Security off, you will be given 2 TXT records and 1 MX record.

        Domain whitelabels can be associated with (i.e. assigned to) subusers from a parent account. This functionality allows subusers to send mail using their parent's whitelabels. To associate a whitelabel with a subuser, the parent account must first create the whitelabel and validate it. The the parent may then associate the whitelabel via the subuser management tools.

        For more information on whitelabeling, please see our [User Guide](https://sendgrid.com/docs/User_Guide/Settings/Whitelabel/index.html)

        ## URI Parameters
        | URI Parameter   | Type  | Required?  | Description  |
        |---|---|---|---|
        | username | string  | required  | Username for the subuser to find associated whitelabels for. |
      operationId: whitelabel.domains.subuser.delete
      x-api-path-slug: whitelabeldomainssubuser-delete
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Domains
      - Subuser
    get:
      summary: Get Whitelabel Domains Subuser
      description: |-
        **This endpoint allows you to retrieve all of the whitelabels that have been assigned to a specific subuser.**

        A domain whitelabel allows you to remove the ???via??? or ???sent on behalf of??? message that your recipients see when they read your emails. Whitelabeling a domain allows you to replace sendgrid.net with your personal sending domain. You will be required to create a subdomain so that SendGrid can generate the DNS records which you must give to your host provider. If you choose to use Automated Security, SendGrid will provide you with 3 CNAME records. If you turn Automated Security off, you will be given 2 TXT records and 1 MX record.

        Domain whitelabels can be associated with (i.e. assigned to) subusers from a parent account. This functionality allows subusers to send mail using their parent's whitelabels. To associate a whitelabel with a subuser, the parent account must first create the whitelabel and validate it. The the parent may then associate the whitelabel via the subuser management tools.

        For more information on whitelabeling, please see our [User Guide](https://sendgrid.com/docs/User_Guide/Settings/Whitelabel/index.html)

        ## URI Parameters
        | URI Parameter   | Type  | Description  |
        |---|---|---|
        | username | string  | Username of the subuser to find associated whitelabels for. |
      operationId: whitelabel.domains.subuser.get
      x-api-path-slug: whitelabeldomainssubuser-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Domains
      - Subuser
  /whitelabel/domains/{domain_id}:
    delete:
      summary: Delete Whitelabel Domains Domain
      description: |-
        **This endpoint allows you to delete a domain whitelabel.**

        A domain whitelabel allows you to remove the ???via??? or ???sent on behalf of??? message that your recipients see when they read your emails. Whitelabeling a domain allows you to replace sendgrid.net with your personal sending domain. You will be required to create a subdomain so that SendGrid can generate the DNS records which you must give to your host provider. If you choose to use Automated Security, SendGrid will provide you with 3 CNAME records. If you turn Automated Security off, you will be given 2 TXT records and 1 MX record.

        For more information on whitelabeling, please see our [User Guide](https://sendgrid.com/docs/User_Guide/Settings/Whitelabel/index.html)
      operationId: whitelabel.domains.domain_id.delete
      x-api-path-slug: whitelabeldomainsdomain-id-delete
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Domains
      - Domain
    get:
      summary: Get Whitelabel Domains Domain
      description: |-
        **This endpoint allows you to retrieve a specific domain whitelabel.**

        A domain whitelabel allows you to remove the ???via??? or ???sent on behalf of??? message that your recipients see when they read your emails. Whitelabeling a domain allows you to replace sendgrid.net with your personal sending domain. You will be required to create a subdomain so that SendGrid can generate the DNS records which you must give to your host provider. If you choose to use Automated Security, SendGrid will provide you with 3 CNAME records. If you turn Automated Security off, you will be given 2 TXT records and 1 MX record.

        For more information on whitelabeling, please see our [User Guide](https://sendgrid.com/docs/User_Guide/Settings/Whitelabel/index.html)
      operationId: whitelabel.domains.domain_id.get
      x-api-path-slug: whitelabeldomainsdomain-id-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Domains
      - Domain
    patch:
      summary: Patch Whitelabel Domains Domain
      description: |-
        **This endpoint allows you to update the settings for a domain whitelabel.**

        A domain whitelabel allows you to remove the ???via??? or ???sent on behalf of??? message that your recipients see when they read your emails. Whitelabeling a domain allows you to replace sendgrid.net with your personal sending domain. You will be required to create a subdomain so that SendGrid can generate the DNS records which you must give to your host provider. If you choose to use Automated Security, SendGrid will provide you with 3 CNAME records. If you turn Automated Security off, you will be given 2 TXT records and 1 MX record.

        For more information on whitelabeling, please see our [User Guide](https://sendgrid.com/docs/User_Guide/Settings/Whitelabel/index.html)
      operationId: whitelabel.domains.domain_id.patch
      x-api-path-slug: whitelabeldomainsdomain-id-patch
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Domains
      - Domain
  /whitelabel/domains/{domain_id}/subuser:
    post:
      summary: Add Whitelabel Domains Domain  Subuser
      description: |-
        **This endpoint allows you to associate a specific domain whitelabel with a subuser.**

        A domain whitelabel allows you to remove the ???via??? or ???sent on behalf of??? message that your recipients see when they read your emails. Whitelabeling a domain allows you to replace sendgrid.net with your personal sending domain. You will be required to create a subdomain so that SendGrid can generate the DNS records which you must give to your host provider. If you choose to use Automated Security, SendGrid will provide you with 3 CNAME records. If you turn Automated Security off, you will be given 2 TXT records and 1 MX record.

        Domain whitelabels can be associated with (i.e. assigned to) subusers from a parent account. This functionality allows subusers to send mail using their parent's whitelabels. To associate a whitelabel with a subuser, the parent account must first create the whitelabel and validate it. The the parent may then associate the whitelabel via the subuser management tools.

        For more information on whitelabeling, please see our [User Guide](https://sendgrid.com/docs/User_Guide/Settings/Whitelabel/index.html)

        ## URI Parameters
        | URI Parameter   | Type   | Description  |
        |---|---|---|
        | domain_id | integer   | ID of the domain whitelabel to associate with the subuser. |
      operationId: whitelabel.domains.domain_id.subuser.post
      x-api-path-slug: whitelabeldomainsdomain-idsubuser-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Domains
      - Domain
      - ""
      - Subuser
  /whitelabel/domains/{id}/ips:
    post:
      summary: Add Whitelabel Domains  Ips
      description: |-
        **This endpoint allows you to add an IP address to a domain whitelabel.**

        A domain whitelabel allows you to remove the ???via??? or ???sent on behalf of??? message that your recipients see when they read your emails. Whitelabeling a domain allows you to replace sendgrid.net with your personal sending domain. You will be required to create a subdomain so that SendGrid can generate the DNS records which you must give to your host provider. If you choose to use Automated Security, SendGrid will provide you with 3 CNAME records. If you turn Automated Security off, you will be given 2 TXT records and 1 MX record.

        For more information on whitelabeling, please see our [User Guide](https://sendgrid.com/docs/User_Guide/Settings/Whitelabel/index.html)

        ## URI Parameters
        | URI Parameter   | Type  |  Description  |
        |---|---|---|
        | id | integer  | ID of the domain to which you are adding an IP |
      operationId: whitelabel.domains.id.ips.post
      x-api-path-slug: whitelabeldomainsidips-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Domains
      - ""
      - Ips
  /whitelabel/domains/{id}/ips/{ip}:
    delete:
      summary: Delete Whitelabel Domains  Ips Ip
      description: |-
        **This endpoint allows you to remove a domain's IP address from that domain's whitelabel.**

        A domain whitelabel allows you to remove the ???via??? or ???sent on behalf of??? message that your recipients see when they read your emails. Whitelabeling a domain allows you to replace sendgrid.net with your personal sending domain. You will be required to create a subdomain so that SendGrid can generate the DNS records which you must give to your host provider. If you choose to use Automated Security, SendGrid will provide you with 3 CNAME records. If you turn Automated Security off, you will be given 2 TXT records and 1 MX record.

        For more information on whitelabeling, please see our [User Guide](https://sendgrid.com/docs/User_Guide/Settings/Whitelabel/index.html)

        ## URI Parameters
        | URI Parameter   | Type  | Description  |
        |---|---|---|
        | id | integer  | ID of the domain whitelabel to delete the IP from. |
        | ip | string | IP to remove from the domain whitelabel. |
      operationId: whitelabel.domains.id.ips.ip.delete
      x-api-path-slug: whitelabeldomainsidipsip-delete
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Domains
      - ""
      - Ips
      - Ip
  /whitelabel/domains/{id}/validate:
    post:
      summary: Add Whitelabel Domains  Valate
      description: |-
        **This endpoint allows you to validate a domain whitelabel. If it fails, it will return an error message describing why the whitelabel could not be validated.**

        A domain whitelabel allows you to remove the ???via??? or ???sent on behalf of??? message that your recipients see when they read your emails. Whitelabeling a domain allows you to replace sendgrid.net with your personal sending domain. You will be required to create a subdomain so that SendGrid can generate the DNS records which you must give to your host provider. If you choose to use Automated Security, SendGrid will provide you with 3 CNAME records. If you turn Automated Security off, you will be given 2 TXT records and 1 MX record.

        For more information on whitelabeling, please see our [User Guide](https://sendgrid.com/docs/User_Guide/Settings/Whitelabel/index.html)

        ## URI Parameters
        | URI Parameter   | Type   | Description  |
        |---|---|---|
        | id | integer  |ID of the domain whitelabel to validate. |
      operationId: whitelabel.domains.id.validate.post
      x-api-path-slug: whitelabeldomainsidvalidate-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Domains
      - ""
      - Valate
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---
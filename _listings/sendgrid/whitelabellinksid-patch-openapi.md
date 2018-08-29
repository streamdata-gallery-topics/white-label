---
swagger: "2.0"
x-collection-name: SendGrid
x-complete: 0
info:
  title: SendGrid Patch Whitelabel Links
  description: |-
    **This endpoint allows you to update a specific link whitelabel. You can use this endpoint to change a link whitelabel's default status.**

    Email link whitelabels allow all of the click-tracked links you send in your emails to include the URL of your domain instead of sendgrid.net.

    For more information, please see our [User Guide](https://sendgrid.com/docs/API_Reference/Web_API_v3/Whitelabel/links.html).
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
  /whitelabel/ips:
    get:
      summary: Get Whitelabel Ips
      description: |-
        **This endpoint allows you to retrieve all of the IP whitelabels that have been createdy by this account.**

        You may include a search key by using the "ip" parameter. This enables you to perform a prefix search for a given IP segment (e.g. "192.").

        A IP whitelabel consists of a subdomain and domain that will be used to generate a reverse DNS record for a given IP. Once SendGrid has verified that the appropriate A record for the IP has been created, the appropriate reverse DNS record for the IP is generated.

        For more information, please see our [User Guide](https://sendgrid.com/docs/API_Reference/Web_API_v3/Whitelabel/ips.html).
      operationId: whitelabel.ips.get
      x-api-path-slug: whitelabelips-get
      parameters:
      - in: query
        name: ip
        description: The IP segment that you would like to use in a prefix search
      - in: query
        name: limit
        description: The number of results to retrieve
      - in: query
        name: No Name
      - in: query
        name: offset
        description: The point in the list of results to begin retrieving IPs from
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Ips
    post:
      summary: Add Whitelabel Ips
      description: |-
        **This endpoint allows you to create an IP whitelabel.**

        When creating an IP whitelable, you should use the same subdomain that you used when you created a domain whitelabel.

        A IP whitelabel consists of a subdomain and domain that will be used to generate a reverse DNS record for a given IP. Once SendGrid has verified that the appropriate A record for the IP has been created, the appropriate reverse DNS record for the IP is generated.

        For more information, please see our [User Guide](https://sendgrid.com/docs/API_Reference/Web_API_v3/Whitelabel/ips.html).
      operationId: whitelabel.ips.post
      x-api-path-slug: whitelabelips-post
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
      - Ips
  /whitelabel/ips/{id}:
    delete:
      summary: Delete Whitelabel Ips
      description: |-
        **This endpoint allows you to delete an IP whitelabel.**

        A IP whitelabel consists of a subdomain and domain that will be used to generate a reverse DNS record for a given IP. Once SendGrid has verified that the appropriate A record for the IP has been created, the appropriate reverse DNS record for the IP is generated.

        For more information, please see our [User Guide](https://sendgrid.com/docs/API_Reference/Web_API_v3/Whitelabel/ips.html).
      operationId: whitelabel.ips.id.delete
      x-api-path-slug: whitelabelipsid-delete
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
      - Ips
    get:
      summary: Get Whitelabel Ips
      description: |-
        **This endpoint allows you to retrieve an IP whitelabel.**

        A IP whitelabel consists of a subdomain and domain that will be used to generate a reverse DNS record for a given IP. Once SendGrid has verified that the appropriate A record for the IP has been created, the appropriate reverse DNS record for the IP is generated.

        For more information, please see our [User Guide](https://sendgrid.com/docs/API_Reference/Web_API_v3/Whitelabel/ips.html).
      operationId: whitelabel.ips.id.get
      x-api-path-slug: whitelabelipsid-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Ips
  /whitelabel/ips/{id}/validate:
    post:
      summary: Add Whitelabel Ips  Valate
      description: |-
        **This endpoint allows you to validate an IP whitelabel.**

        A IP whitelabel consists of a subdomain and domain that will be used to generate a reverse DNS record for a given IP. Once SendGrid has verified that the appropriate A record for the IP has been created, the appropriate reverse DNS record for the IP is generated.

        For more information, please see our [User Guide](https://sendgrid.com/docs/API_Reference/Web_API_v3/Whitelabel/ips.html).
      operationId: whitelabel.ips.id.validate.post
      x-api-path-slug: whitelabelipsidvalidate-post
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
      - Ips
      - ""
      - Valate
  /whitelabel/links:
    get:
      summary: Get Whitelabel Links
      description: |-
        **This endpoint allows you to retrieve all link whitelabels.**

        Email link whitelabels allow all of the click-tracked links you send in your emails to include the URL of your domain instead of sendgrid.net.

        For more information, please see our [User Guide](https://sendgrid.com/docs/API_Reference/Web_API_v3/Whitelabel/links.html).
      operationId: whitelabel.links.get
      x-api-path-slug: whitelabellinks-get
      parameters:
      - in: query
        name: limit
        description: Limits the number of results returned per page
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Links
    post:
      summary: Add Whitelabel Links
      description: |-
        **This endpoint allows you to create a new link whitelabel.**

        Email link whitelabels allow all of the click-tracked links you send in your emails to include the URL of your domain instead of sendgrid.net.

        For more information, please see our [User Guide](https://sendgrid.com/docs/API_Reference/Web_API_v3/Whitelabel/links.html).
      operationId: whitelabel.links.post
      x-api-path-slug: whitelabellinks-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: limit
        description: Number of domains to return
      - in: query
        name: No Name
      - in: query
        name: offset
        description: Paging offset
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Links
  /whitelabel/links/default:
    get:
      summary: Get Whitelabel Links Default
      description: |-
        **This endpoint allows you to retrieve the default link whitelabel.**

        Default link whitelabel is the actual link whitelabel to be used when sending messages. If there are multiple link whitelabels, the default is determined by the following order:
        <ul>
          <li>Validated link whitelabels marked as "default"</li>
          <li>Legacy link whitelabels (migrated from the whitelabel wizard)</li>
          <li>Default SendGrid link whitelabel (i.e. 100.ct.sendgrid.net)</li>
        </ul>

        Email link whitelabels allow all of the click-tracked links you send in your emails to include the URL of your domain instead of sendgrid.net.

        For more information, please see our [User Guide](https://sendgrid.com/docs/API_Reference/Web_API_v3/Whitelabel/links.html).
      operationId: whitelabel.links.default.get
      x-api-path-slug: whitelabellinksdefault-get
      parameters:
      - in: query
        name: domain
        description: The domain to match against when finding a corresponding link
          whitelabel
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Links
      - Default
  /whitelabel/links/subuser:
    delete:
      summary: Delete Whitelabel Links Subuser
      description: |-
        **This endpoint allows you to disassociate a link whitelabel from a subuser.**

        Link whitelables can be associated with subusers from the parent account. This functionality allows
        subusers to send mail using their parent's linke whitelabels. To associate a link whitelabel, the parent account
        must first create a whitelabel and validate it. The parent may then associate that whitelabel with a subuser via the API or the Subuser Management page in the user interface.

        Email link whitelabels allow all of the click-tracked links you send in your emails to include the URL of your domain instead of sendgrid.net.

        For more information, please see our [User Guide](https://sendgrid.com/docs/API_Reference/Web_API_v3/Whitelabel/links.html).
      operationId: whitelabel.links.subuser.delete
      x-api-path-slug: whitelabellinkssubuser-delete
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      - in: query
        name: username
        description: The username of the subuser account that you want to disassociate
          a link whitelabel from
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Links
      - Subuser
    get:
      summary: Get Whitelabel Links Subuser
      description: |-
        **This endpoint allows you to retrieve the associated link whitelabel for a subuser.**

        Link whitelables can be associated with subusers from the parent account. This functionality allows
        subusers to send mail using their parent's linke whitelabels. To associate a link whitelabel, the parent account
        must first create a whitelabel and validate it. The parent may then associate that whitelabel with a subuser via the API or the Subuser Management page in the user interface.

        Email link whitelabels allow all of the click-tracked links you send in your emails to include the URL of your domain instead of sendgrid.net.

        For more information, please see our [User Guide](https://sendgrid.com/docs/API_Reference/Web_API_v3/Whitelabel/links.html).
      operationId: whitelabel.links.subuser.get
      x-api-path-slug: whitelabellinkssubuser-get
      parameters:
      - in: query
        name: No Name
      - in: query
        name: username
        description: The username of the subuser to retrieve associated link whitelabels
          for
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Links
      - Subuser
  /whitelabel/links/{id}:
    delete:
      summary: Delete Whitelabel Links
      description: |-
        **This endpoint allows you to delete a link whitelabel.**

        Email link whitelabels allow all of the click-tracked links you send in your emails to include the URL of your domain instead of sendgrid.net.

        For more information, please see our [User Guide](https://sendgrid.com/docs/API_Reference/Web_API_v3/Whitelabel/links.html).
      operationId: whitelabel.links.id.delete
      x-api-path-slug: whitelabellinksid-delete
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
      - Links
    get:
      summary: Get Whitelabel Links
      description: |-
        **This endpoint allows you to retrieve a specific link whitelabel.**

        Email link whitelabels allow all of the click-tracked links you send in your emails to include the URL of your domain instead of sendgrid.net.

        For more information, please see our [User Guide](https://sendgrid.com/docs/API_Reference/Web_API_v3/Whitelabel/links.html).
      operationId: whitelabel.links.id.get
      x-api-path-slug: whitelabellinksid-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Email
      - Whitelabel
      - Links
    patch:
      summary: Patch Whitelabel Links
      description: |-
        **This endpoint allows you to update a specific link whitelabel. You can use this endpoint to change a link whitelabel's default status.**

        Email link whitelabels allow all of the click-tracked links you send in your emails to include the URL of your domain instead of sendgrid.net.

        For more information, please see our [User Guide](https://sendgrid.com/docs/API_Reference/Web_API_v3/Whitelabel/links.html).
      operationId: whitelabel.links.id.patch
      x-api-path-slug: whitelabellinksid-patch
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
      - Links
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
---
swagger: "2.0"
x-collection-name: AWS Route 53
x-complete: 0
info:
  title: AWS Route 53 API Create Reusable Delegation Set
  version: 1.0.0
  description: Creates a delegation set (a group of four name servers) that can be
    reused by multiplehosted zones. If a hosted zoned ID is specified, CreateReusableDelegationSetmarks
    the delegation set associated with that zone as reusableSend a POST request to
    the /2013-04-01/delegationset resource. The request body must include a document
    with a CreateReusableDelegationSetRequest element.NoteA reusable delegation set
    can't be associated with a private hosted zone/For more information, including
    a procedure on how to create and configure a reusabledelegation set (also known
    as white label name servers), see Configuring White Label NameServers.
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /2013-04-01/delegationset:
    post:
      summary: Create Reusable Delegation Set
      description: Creates a delegation set (a group of four name servers) that can
        be reused by multiplehosted zones. If a hosted zoned ID is specified, CreateReusableDelegationSetmarks
        the delegation set associated with that zone as reusableSend a POST request
        to the /2013-04-01/delegationset resource. The request body must include a
        document with a CreateReusableDelegationSetRequest element.NoteA reusable
        delegation set can't be associated with a private hosted zone/For more information,
        including a procedure on how to create and configure a reusabledelegation
        set (also known as white label name servers), see Configuring White Label
        NameServers.
      operationId: createreusabledelegationset
      x-api-path-slug: 20130401delegationset-post
      parameters:
      - in: body
        name: CallerReference
        description: A unique string that identifies the request, and that allows
          you to retry failedCreateReusableDelegationSet requests without the risk
          of executing theoperation twice
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: CreateReusableDelegationSetRequest
        description: Root level tag for the CreateReusableDelegationSetRequest parameters
        schema:
          $ref: '#/definitions/holder'
      - in: body
        name: HostedZoneId
        description: If you want to mark the delegation set for an existing hosted
          zone as reusable, the IDfor that hosted zone
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Reusable Delegation Sets
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
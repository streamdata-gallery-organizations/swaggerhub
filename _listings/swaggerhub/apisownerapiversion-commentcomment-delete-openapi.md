---
swagger: "2.0"
x-collection-name: SwaggerHub
x-complete: 0
info:
  title: Swagger Hub Registry Deletes specified comment
  description: Deletes specified comment.
  contact:
    name: SwaggerHub
    url: http://swaggerhub.com
    email: info@swaggerhub.com
  version: 1.0.45
host: api.swaggerhub.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /apis:
    get:
      summary: Retrieves a list of currently defined APIs in APIs.json format.
      description: Retrieves a list of currently defined apis in apis.json format..
      operationId: searchApis
      x-api-path-slug: apis-get
      parameters:
      - in: query
        name: limit
        description: number of results per page
      - in: query
        name: order
        description: sort order
      - in: query
        name: page
        description: page to return
      - in: query
        name: query
        description: free text query to match
      - in: query
        name: sort
        description: sort criteria or result set* NAME -* UPATED* CREATED* OWNER
      - in: query
        name: state
        description: matches against published state of the spec* UNPUBLISHED - spec
          is a draft, a work in progress* PUBLISHED - spec is a stable version ready
          for consuming from client applications* ANY - either PUBLISHED or UNPUBLISHED
      - in: query
        name: tag
        description: matches against tags associated with an API
      responses:
        200:
          description: OK
      tags:
      - APIs
  /apis/{owner}:
    get:
      summary: Retrieves an APIs.json listing of all APIs defined for this owner
      description: Retrieves an apis.json listing of all apis defined for this owner.
      operationId: getOwnerApis
      x-api-path-slug: apisowner-get
      parameters:
      - in: query
        name: limit
        description: number of results per page
      - in: query
        name: order
        description: sort order
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: query
        name: page
        description: page to return
      - in: query
        name: sort
        description: sort criteria or result set* NAME -* UPATED* CREATED* OWNER
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
    put:
      summary: Updates owner
      description: Updates owner.
      operationId: updateOwner
      x-api-path-slug: apisowner-put
      parameters:
      - in: query
        name: newNameToken
        description: Token for updating owner name
      - in: path
        name: owner
        description: API owner identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
  /apis/{owner}/{api}:
    delete:
      summary: Deletes the specified API
      description: Deletes the specified api.
      operationId: deleteApi
      x-api-path-slug: apisownerapi-delete
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
    get:
      summary: Retrieves an APIs.json listing for all API versions for this owner
        and API
      description: Retrieves an apis.json listing for all api versions for this owner
        and api.
      operationId: getApiVersions
      x-api-path-slug: apisownerapi-get
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
    post:
      summary: Saves the provided Swagger definition
      description: Saves the provided swagger definition.
      operationId: saveDefinition
      x-api-path-slug: apisownerapi-post
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: body
        name: definition
        description: the Swagger definition of this API
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: force
        description: force update
      - in: query
        name: isPrivate
        description: Defines whether the API has to be private
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: query
        name: version
        description: api version
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
  /apis/{owner}/{api}/.collaboration:
    delete:
      summary: Deletes API's collaboration
      description: Deletes api's collaboration.
      operationId: deleteCollaboration
      x-api-path-slug: apisownerapi-collaboration-delete
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - ""
      - Collaboration
    get:
      summary: Gets API's collaboration
      description: Gets api's collaboration.
      operationId: getCollaboration
      x-api-path-slug: apisownerapi-collaboration-get
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: query
        name: expandTeams
      - in: path
        name: owner
        description: API or Domaion owner identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - ""
      - Collaboration
    put:
      summary: Updates API's collaboration
      description: Updates api's collaboration.
      operationId: updateCollaboration
      x-api-path-slug: apisownerapi-collaboration-put
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: owner
        description: API or Domaion owner identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - ""
      - Collaboration
  /apis/{owner}/{api}/{version}:
    delete:
      summary: Deletes a particular version of the specified API
      description: Deletes a particular version of the specified api.
      operationId: deleteApiVersion
      x-api-path-slug: apisownerapiversion-delete
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - Version
    get:
      summary: Retrieves the Swagger definition for the specified API and version
      description: Retrieves the swagger definition for the specified api and version.
      operationId: getDefinition
      x-api-path-slug: apisownerapiversion-get
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - Version
  /apis/{owner}/{api}/{version}/swagger.json:
    get:
      summary: Retrieves the Swagger definition for the specified API and version
        in JSON format
      description: Retrieves the swagger definition for the specified api and version
        in json format.
      operationId: getJsonDefinition
      x-api-path-slug: apisownerapiversionswagger-json-get
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - Version
      - Swagger
      - Json
  /apis/{owner}/{api}/{version}/swagger.yaml:
    get:
      summary: Retrieves the Swagger definition for the specified API and version
        in YAML format
      description: Retrieves the swagger definition for the specified api and version
        in yaml format.
      operationId: getYamlDefinition
      x-api-path-slug: apisownerapiversionswagger-yaml-get
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - Version
      - Swagger
      - Yaml
  /domains:
    get:
      summary: Retrieves a list of currently defined domains in APIs.json format
      description: Retrieves a list of currently defined domains in apis.json format.
      operationId: searchDomains
      x-api-path-slug: domains-get
      parameters:
      - in: query
        name: limit
        description: number of results per page
      - in: query
        name: order
        description: sort order
      - in: query
        name: page
        description: page to return
      - in: query
        name: query
        description: free text query to match
      - in: query
        name: sort
        description: sort criteria or result set* NAME -* UPATED* CREATED* OWNER
      - in: query
        name: state
        description: matches against published state of the spec* UNPUBLISHED - spec
          is a draft, a work in progress* PUBLISHED - spec is a stable version ready
          for consuming from client applications* ANY - either PUBLISHED or UNPUBLISHED
      - in: query
        name: tag
        description: matches against tags associated with a domain
      responses:
        200:
          description: OK
      tags:
      - Domains
  /domains/{owner}:
    get:
      summary: Retrieves an APIs.json listing of all domains defined for this owner
      description: Retrieves an apis.json listing of all domains defined for this
        owner.
      operationId: getOwnerDomains
      x-api-path-slug: domainsowner-get
      parameters:
      - in: query
        name: limit
        description: number of results per page
      - in: query
        name: order
        description: sort order
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: query
        name: page
        description: page to return
      - in: query
        name: sort
        description: sort criteria or result set* NAME -* UPATED* CREATED* OWNER
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
  /domains/{owner}/{domain}:
    delete:
      summary: Deletes the specified domain
      description: Deletes the specified domain.
      operationId: deleteDomain
      x-api-path-slug: domainsownerdomain-delete
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: query
        name: force
        description: force update
      - in: path
        name: owner
        description: API or Domaion owner identifier
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - Domain
    get:
      summary: Retrieves an APIs.json listing for all domain versions for this owner
        and domain
      description: Retrieves an apis.json listing for all domain versions for this
        owner and domain.
      operationId: getDomainVersions
      x-api-path-slug: domainsownerdomain-get
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - Domain
    post:
      summary: Saves the provided Swagger definition of a domain
      description: Saves the provided swagger definition of a domain.
      operationId: saveDomainDefinition
      x-api-path-slug: domainsownerdomain-post
      parameters:
      - in: body
        name: definition
        description: the Swagger definition of this Domain
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: domain
        description: domain identifier
      - in: query
        name: force
        description: force update
      - in: query
        name: isPrivate
        description: Defines whether the API has to be private
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: query
        name: version
        description: domain version
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - Domain
  /domains/{owner}/{domain}/{version}:
    delete:
      summary: Deletes a particular version of the specified domain
      description: Deletes a particular version of the specified domain.
      operationId: deleteDomainVersion
      x-api-path-slug: domainsownerdomainversion-delete
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: query
        name: force
        description: force update
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - Domain
      - Version
    get:
      summary: Retrieves the Swagger definition for the specified domain and version
      description: Retrieves the swagger definition for the specified domain and version.
      operationId: getDomainDefinition
      x-api-path-slug: domainsownerdomainversion-get
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - Domain
      - Version
  /domains/{owner}/{domain}/{version}/domain.json:
    get:
      summary: Retrieves the definition for the specified domain and version in JSON
        format
      description: Retrieves the definition for the specified domain and version in
        json format.
      operationId: getDomainJsonDefinition
      x-api-path-slug: domainsownerdomainversiondomain-json-get
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - Domain
      - Version
      - Domain
      - Json
  /domains/{owner}/{domain}/{version}/domain.yaml:
    get:
      summary: Retrieves the definition for the specified domain and version in YAML
        format
      description: Retrieves the definition for the specified domain and version in
        yaml format.
      operationId: getDomainYamlDefinition
      x-api-path-slug: domainsownerdomainversiondomain-yaml-get
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: path
        name: owner
        description: API or Domaion owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - Domain
      - Version
      - Domain
      - Yaml
  /specs:
    get:
      summary: Retrieves a list of currently defined APIs and Domains in APIs.json
        format
      description: Retrieves a list of currently defined apis and domains in apis.json
        format.
      operationId: searchApisAndDomains
      x-api-path-slug: specs-get
      parameters:
      - in: query
        name: limit
        description: number of results per page
      - in: query
        name: order
        description: sort order
      - in: query
        name: owner
        description: API or Domaion owner identifier
      - in: query
        name: page
        description: page to return
      - in: query
        name: query
        description: free text query to match
      - in: query
        name: sort
        description: sort criteria or result set* NAME -* UPATED* CREATED* OWNER
      - in: query
        name: specType
        description: Type of Swagger specs to search* API - APIs only* DOMAIN - Domains
          only* ANY - Both APIs and Domains
      - in: query
        name: state
        description: matches against published state of the spec* UNPUBLISHED - spec
          is a draft, a work in progress* PUBLISHED - spec is a stable version ready
          for consuming from client applications* ANY - either PUBLISHED or UNPUBLISHED
      - in: query
        name: visibility
        description: The visibility of a spec in SwaggerHub* PUBLIC - can be viewed
          by anyone* PRIVATE - can only be viewed by you or your Org and those that
          you are collaborating with or have shared it with* ANY - either PUBLIC or
          PRIVATE
      responses:
        200:
          description: OK
      tags:
      - Specs
  /apis/.template:
    get:
      summary: Retrieves list of apis templates
      description: Retrieves list of apis templates.
      operationId: getApiTemplates
      x-api-path-slug: apis-template-get
      responses:
        200:
          description: OK
      tags:
      - APIs
      - ""
      - Template
  /apis/{owner}/{api}/.newname:
    post:
      summary: Renames API
      description: Renames api.
      operationId: renameApi
      x-api-path-slug: apisownerapi-newname-post
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: query
        name: newName
        description: New name
      - in: path
        name: owner
        description: API owner identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - ""
      - Newname
  /apis/{owner}/{api}/.template:
    post:
      summary: Creates API by template
      description: Creates api by template.
      operationId: saveApiDefinitionByTemplate
      x-api-path-slug: apisownerapi-template-post
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: query
        name: isPrivate
        description: Defines whether the API has to be private
      - in: path
        name: owner
        description: API owner identifier
      - in: query
        name: template
        description: Template id
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - ""
      - Template
  /apis/{owner}/{api}/.transfer:
    post:
      summary: transfers api to another owner
      description: Transfers api to another owner.
      operationId: transferApi
      x-api-path-slug: apisownerapi-transfer-post
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: query
        name: newOwner
        description: New owner
      - in: path
        name: owner
        description: API owner identifier
      - in: query
        name: transferIntegrations
        description: Transfer integrations
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - ""
      - Transfer
  /apis/{owner}/{api}/{version}/.bump:
    post:
      summary: Adds API version
      description: Adds api version.
      operationId: bumpApi
      x-api-path-slug: apisownerapiversion-bump-post
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: query
        name: force
        description: force update
      - in: query
        name: isPrivate
        description: Defines whether the API has to be private
      - in: query
        name: newVersion
        description: New api version
      - in: path
        name: owner
        description: API owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - Version
      - ""
      - Bump
  /apis/{owner}/{api}/{version}/.comment:
    get:
      summary: Returns the list of comments for the specified API
      description: Returns the list of comments for the specified api.
      operationId: getApiComments
      x-api-path-slug: apisownerapiversion-comment-get
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: path
        name: owner
        description: API owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - Version
      - ""
      - Comment
    post:
      summary: Adds a new comment to the specified API
      description: Adds a new comment to the specified api.
      operationId: addApiComment
      x-api-path-slug: apisownerapiversion-comment-post
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: owner
        description: API owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - Version
      - ""
      - Comment
  /apis/{owner}/{api}/{version}/.comment/batch:
    post:
      summary: Updates passed batch of comments
      description: Updates passed batch of comments.
      operationId: updateApiComments
      x-api-path-slug: apisownerapiversion-commentbatch-post
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: owner
        description: API owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - Version
      - ""
      - Comment
      - Batch
  /apis/{owner}/{api}/{version}/.comment/{comment}:
    delete:
      summary: Deletes specified comment
      description: Deletes specified comment.
      operationId: deleteApiComment
      x-api-path-slug: apisownerapiversion-commentcomment-delete
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: path
        name: comment
        description: comment identifier
      - in: path
        name: owner
        description: API owner identifier
      - in: path
        name: version
        description: version identifier
      responses:
        200:
          description: OK
      tags:
      - APIs
      - Owner
      - Version
      - ""
      - Comment
      - Comment
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
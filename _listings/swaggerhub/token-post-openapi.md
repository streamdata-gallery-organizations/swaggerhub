---
swagger: "2.0"
x-collection-name: SwaggerHub
x-complete: 0
info:
  title: Swagger Hub Registry Retrieves an API token valid for the user identified
    by user object in body
  description: Retrieves an api token valid for the user identified by user object
    in body.
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
    patch:
      summary: Updates specified comment
      description: Updates specified comment.
      operationId: updateApiComment
      x-api-path-slug: apisownerapiversion-commentcomment-patch
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
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
  /apis/{owner}/{api}/{version}/.comment/{comment}/reply:
    post:
      summary: Adds a new reply to the specified comment
      description: Adds a new reply to the specified comment.
      operationId: addApiCommentReply
      x-api-path-slug: apisownerapiversion-commentcommentreply-post
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
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
      - Reply
  /apis/{owner}/{api}/{version}/.comment/{comment}/reply/{reply}:
    delete:
      summary: Deletes specified comment reply
      description: Deletes specified comment reply.
      operationId: deleteApiCommentReply
      x-api-path-slug: apisownerapiversion-commentcommentreplyreply-delete
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
        name: reply
        description: reply identifier
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
      - Reply
      - Reply
    patch:
      summary: Updates specified comment reply
      description: Updates specified comment reply.
      operationId: updateApiCommentReply
      x-api-path-slug: apisownerapiversion-commentcommentreplyreply-patch
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: comment
        description: comment identifier
      - in: path
        name: owner
        description: API owner identifier
      - in: path
        name: reply
        description: reply identifier
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
      - Reply
      - Reply
  /apis/{owner}/{api}/{version}/.comment/{comment}/status/{status}:
    put:
      summary: Updates status to the specified comment
      description: Updates status to the specified comment.
      operationId: setApiCommentStatus
      x-api-path-slug: apisownerapiversion-commentcommentstatusstatus-put
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
        name: status
        description: comment status
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
      - Status
      - Status
  /apis/{owner}/{api}/{version}/.draft:
    delete:
      summary: Deletes a particular version of the specified API
      description: Deletes a particular version of the specified api.
      operationId: deleteDraftApi
      x-api-path-slug: apisownerapiversion-draft-delete
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
      - Draft
    get:
      summary: Retrieves the draft for the specified API and version
      description: Retrieves the draft for the specified api and version.
      operationId: getDraft
      x-api-path-slug: apisownerapiversion-draft-get
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
      - Draft
    put:
      summary: Saves the provided draft for a Swagger definition
      description: Saves the provided draft for a swagger definition.
      operationId: saveDraft
      x-api-path-slug: apisownerapiversion-draft-put
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: body
        name: definition
        description: the Swagger definition of this API
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
      - Draft
  /apis/{owner}/{api}/{version}/.fork:
    post:
      summary: Forks the provided Swagger definition
      description: Forks the provided swagger definition.
      operationId: forkApi
      x-api-path-slug: apisownerapiversion-fork-post
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
      - in: body
        name: newSpec
        description: New spec id
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
      - Fork
  /apis/{owner}/{api}/{version}/compare:
    get:
      summary: Compares two APIs
      description: Compares two apis.
      operationId: compareApis
      x-api-path-slug: apisownerapiversioncompare-get
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: query
        name: method
        description: The method to use for comparing two APIs
      - in: query
        name: otherApiPath
        description: URL to external API or path to internal API
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
      - Compare
    post:
      summary: Compares two APIs
      description: Compares two apis.
      operationId: compareApisFromFile
      x-api-path-slug: apisownerapiversioncompare-post
      parameters:
      - in: path
        name: api
        description: API identifier
      - in: body
        name: definition
        description: the definition parsed from an uploaded file
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: method
        description: The method to use for comparing two APIs
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
      - Compare
  /domains/.template:
    get:
      summary: Retrieves list of domains templates
      description: Retrieves list of domains templates.
      operationId: getDomainTemplates
      x-api-path-slug: domains-template-get
      responses:
        200:
          description: OK
      tags:
      - Domains
      - ""
      - Template
  /domains/{owner}/.refs:
    get:
      summary: Retrieves an APIs.json listing of entries referensing owner domains
      description: Retrieves an apis.json listing of entries referensing owner domains.
      operationId: getOwnerReferences
      x-api-path-slug: domainsowner-refs-get
      parameters:
      - in: path
        name: owner
        description: API owner identifier
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - ""
      - Refs
  /domains/{owner}/{domain}/.newname:
    post:
      summary: Renames domain
      description: Renames domain.
      operationId: renameDomain
      x-api-path-slug: domainsownerdomain-newname-post
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: query
        name: force
        description: force update
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
      - Domains
      - Owner
      - Domain
      - ""
      - Newname
  /domains/{owner}/{domain}/.transfer:
    post:
      summary: transfers domain to another owner
      description: Transfers domain to another owner.
      operationId: transferDomain
      x-api-path-slug: domainsownerdomain-transfer-post
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: query
        name: force
        description: force update
      - in: query
        name: newOwner
        description: New owner
      - in: path
        name: owner
        description: API owner identifier
      responses:
        200:
          description: OK
      tags:
      - Domains
      - Owner
      - Domain
      - ""
      - Transfer
  /domains/{owner}/{domain}/{version}/.bump:
    post:
      summary: Adds domain version
      description: Adds domain version.
      operationId: bumpDomain
      x-api-path-slug: domainsownerdomainversion-bump-post
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: query
        name: force
        description: force update
      - in: query
        name: isPrivate
        description: Defines whether the API has to be private
      - in: query
        name: newVersion
        description: New domain version
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
      - Domains
      - Owner
      - Domain
      - Version
      - ""
      - Bump
  /domains/{owner}/{domain}/{version}/.comment:
    get:
      summary: Returns the list of comments for the specified domain
      description: Returns the list of comments for the specified domain.
      operationId: getDomainComments
      x-api-path-slug: domainsownerdomainversion-comment-get
      parameters:
      - in: path
        name: domain
        description: domain identifier
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
      - Domains
      - Owner
      - Domain
      - Version
      - ""
      - Comment
    post:
      summary: Adds a new comment to the specified domain
      description: Adds a new comment to the specified domain.
      operationId: addDomainComment
      x-api-path-slug: domainsownerdomainversion-comment-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: domain
        description: domain identifier
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
      - Domains
      - Owner
      - Domain
      - Version
      - ""
      - Comment
  /domains/{owner}/{domain}/{version}/.comment/batch:
    post:
      summary: Updates passed batch of comments
      description: Updates passed batch of comments.
      operationId: updateDomainComments
      x-api-path-slug: domainsownerdomainversion-commentbatch-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: domain
        description: domain identifier
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
      - Domains
      - Owner
      - Domain
      - Version
      - ""
      - Comment
      - Batch
  /domains/{owner}/{domain}/{version}/.comment/{comment}:
    delete:
      summary: Deletes specified comment
      description: Deletes specified comment.
      operationId: deleteDomainComment
      x-api-path-slug: domainsownerdomainversion-commentcomment-delete
      parameters:
      - in: path
        name: comment
        description: comment identifier
      - in: path
        name: domain
        description: domain identifier
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
      - Domains
      - Owner
      - Domain
      - Version
      - ""
      - Comment
      - Comment
    patch:
      summary: Updates specified comment
      description: Updates specified comment.
      operationId: updateDomainComment
      x-api-path-slug: domainsownerdomainversion-commentcomment-patch
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: comment
        description: comment identifier
      - in: path
        name: domain
        description: domain identifier
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
      - Domains
      - Owner
      - Domain
      - Version
      - ""
      - Comment
      - Comment
  /domains/{owner}/{domain}/{version}/.comment/{comment}/reply:
    post:
      summary: Adds a new reply to the specified comment
      description: Adds a new reply to the specified comment.
      operationId: addDomainCommentReply
      x-api-path-slug: domainsownerdomainversion-commentcommentreply-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: comment
        description: comment identifier
      - in: path
        name: domain
        description: domain identifier
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
      - Domains
      - Owner
      - Domain
      - Version
      - ""
      - Comment
      - Comment
      - Reply
  /domains/{owner}/{domain}/{version}/.comment/{comment}/reply/{reply}:
    delete:
      summary: Deletes specified comment reply
      description: Deletes specified comment reply.
      operationId: deleteDomainCommentReply
      x-api-path-slug: domainsownerdomainversion-commentcommentreplyreply-delete
      parameters:
      - in: path
        name: comment
        description: comment identifier
      - in: path
        name: domain
        description: domain identifier
      - in: path
        name: owner
        description: API owner identifier
      - in: path
        name: reply
        description: reply identifier
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
      - ""
      - Comment
      - Comment
      - Reply
      - Reply
    patch:
      summary: Updates specified comment reply
      description: Updates specified comment reply.
      operationId: updateDomainCommentReply
      x-api-path-slug: domainsownerdomainversion-commentcommentreplyreply-patch
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: comment
        description: comment identifier
      - in: path
        name: domain
        description: domain identifier
      - in: path
        name: owner
        description: API owner identifier
      - in: path
        name: reply
        description: reply identifier
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
      - ""
      - Comment
      - Comment
      - Reply
      - Reply
  /domains/{owner}/{domain}/{version}/.comment/{comment}/status/{status}:
    put:
      summary: Updates status to the specified comment
      description: Updates status to the specified comment.
      operationId: setDomainCommentStatus
      x-api-path-slug: domainsownerdomainversion-commentcommentstatusstatus-put
      parameters:
      - in: path
        name: comment
        description: comment identifier
      - in: path
        name: domain
        description: domain identifier
      - in: path
        name: owner
        description: API owner identifier
      - in: path
        name: status
        description: comment status
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
      - ""
      - Comment
      - Comment
      - Status
      - Status
  /domains/{owner}/{domain}/{version}/.draft:
    delete:
      summary: Deletes a particular version of the specified Domain
      description: Deletes a particular version of the specified domain.
      operationId: deleteDraftDomain
      x-api-path-slug: domainsownerdomainversion-draft-delete
      parameters:
      - in: path
        name: domain
        description: domain identifier
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
      - Domains
      - Owner
      - Domain
      - Version
      - ""
      - Draft
    get:
      summary: Retrieves the draft for the specified domain
      description: Retrieves the draft for the specified domain.
      operationId: getDraftDomain
      x-api-path-slug: domainsownerdomainversion-draft-get
      parameters:
      - in: path
        name: domain
        description: domain identifier
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
      - Domains
      - Owner
      - Domain
      - Version
      - ""
      - Draft
    put:
      summary: Saves the provided draft for a domain.
      description: Saves the provided draft for a domain..
      operationId: saveDraftDomain
      x-api-path-slug: domainsownerdomainversion-draft-put
      parameters:
      - in: body
        name: definition
        description: the Swagger definition of this Domain
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: domain
        description: domain identifier
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
      - Domains
      - Owner
      - Domain
      - Version
      - ""
      - Draft
  /domains/{owner}/{domain}/{version}/.fork:
    post:
      summary: Forks the provided domain definition
      description: Forks the provided domain definition.
      operationId: forkDomain
      x-api-path-slug: domainsownerdomainversion-fork-post
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: query
        name: force
        description: force update
      - in: query
        name: isPrivate
        description: Defines whether the API has to be private
      - in: body
        name: newSpec
        description: New spec id
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
      - Domains
      - Owner
      - Domain
      - Version
      - ""
      - Fork
  /domains/{owner}/{domain}/{version}/.template:
    post:
      summary: Creates Domain by template
      description: Creates domain by template.
      operationId: saveDomainDefinitionByTemplate
      x-api-path-slug: domainsownerdomainversion-template-post
      parameters:
      - in: path
        name: domain
        description: domain identifier
      - in: query
        name: isPrivate
        description: Defines whether the API has to be private
      - in: path
        name: owner
        description: API owner identifier
      - in: query
        name: template
        description: Template id
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
      - ""
      - Template
  /plugins:
    get:
      summary: Retrieves a list of all available plugins (ignore system plugins)
      description: Retrieves a list of all available plugins (ignore system plugins).
      operationId: getAvailablePlugins
      x-api-path-slug: plugins-get
      responses:
        200:
          description: OK
      tags:
      - Plugins
  /plugins/configurations:
    delete:
      summary: Deletes the provided Plugin configuration
      description: Deletes the provided plugin configuration.
      operationId: removePluginConfiguration
      x-api-path-slug: pluginsconfigurations-delete
      parameters:
      - in: body
        name: pluginConfiguration
        description: the Plugin configuration to be added or updated
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Plugins
      - Configurations
    get:
      summary: Retrieves a list of enabled plugin configurations
      description: Retrieves a list of enabled plugin configurations.
      operationId: getPlugins
      x-api-path-slug: pluginsconfigurations-get
      parameters:
      - in: query
        name: limit
        description: number of results per page
      - in: query
        name: objectId
        description: plugin configuration objectId
      - in: query
        name: page
        description: page to return
      responses:
        200:
          description: OK
      tags:
      - Plugins
      - Configurations
    post:
      summary: Saves the provided Plugin configuration
      description: Saves the provided plugin configuration.
      operationId: addPluginConfiguration
      x-api-path-slug: pluginsconfigurations-post
      parameters:
      - in: body
        name: pluginConfiguration
        description: the Plugin configuration to be added or updated
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: trigger
        description: if true, also execute plugin
      responses:
        200:
          description: OK
      tags:
      - Plugins
      - Configurations
    put:
      summary: Updated the provided Plugin configuration
      description: Updated the provided plugin configuration.
      operationId: updatePluginConfiguration
      x-api-path-slug: pluginsconfigurations-put
      parameters:
      - in: body
        name: pluginConfiguration
        description: the Plugin configuration to be added or updated
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: trigger
        description: if true, also execute plugin
      responses:
        200:
          description: OK
      tags:
      - Plugins
      - Configurations
  /plugins/configurations/execute/{id}:
    post:
      summary: triggers execution of plugin configuration identified by id
      description: Triggers execution of plugin configuration identified by id.
      operationId: triggerPluginConfiguration
      x-api-path-slug: pluginsconfigurationsexecuteid-post
      parameters:
      - in: path
        name: id
        description: plugin configuration id
      responses:
        200:
          description: OK
      tags:
      - Plugins
      - Configurations
      - Execute
      - Id
  /plugins/configurations/schema:
    post:
      summary: get configuration schema for the provided Plugin configuration
      description: Get configuration schema for the provided plugin configuration.
      operationId: buildConfigurationSchema
      x-api-path-slug: pluginsconfigurationsschema-post
      parameters:
      - in: body
        name: pluginConfiguration
        description: the Plugin configuration to be added or updated
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Plugins
      - Configurations
      - Schema
  /token:
    post:
      summary: Retrieves an API token valid for the user identified by user object
        in body
      description: Retrieves an api token valid for the user identified by user object
        in body.
      operationId: getApiTokenByCredentials
      x-api-path-slug: token-post
      parameters:
      - in: body
        name: user
        description: user credentials
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Token
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
---
aid: apis.json
name: Sample API
type: Index
description: |-
  This is an example APIs.json file, demonstrating what is possible with
  the API discovery specification.
image: https://kinlane-productions.s3.amazonaws.com/apis-json/apis-json-logo.jpg
tags:
  - Application Programming Interface
  - API
created: 2024-5-24
modified: 2024-5-24
url: http://example.com/apis.json
specificationVersion: '0.17'
apis:
  - aid: apis.json:example-api
    name: Example API
    description: This provides details about a specific API, telling what is possible.
    image: https://kinlane-productions.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: http://example.com
    baseURL: http://api.example.com
    tags:
      - API
      - Application Programming Interface
    properties:
      - type: Documentation
        url: https://example.com/documentation
      - type: OpenAPI
        url: http://example.com/openapi.yml
      - type: Swagger
        url: http://example.com/swagger.yml
      - type: JSONSchema
        url: http://example.com/json-schema.json
      - type: GraphQLSchema
        url: http://example.com/graphqlql.schema
      - type: PostmanCollection
        url: http://example.com/postman-collection.json
      - type: AsyncAPI
        url: http://example.com/asyncapi.json
      - type: RAML
        url: http://example.com/raml.yml
      - type: Blueprint
        url: http://example.com/blueprint.apib
      - type: WADL
        url: http://example.com/wadl.xml
      - type: WSDL
        url: http://example.com/api.wsdl
      - type: OpenAIPluginManifest
        url: https://example.com/openaiplugin.yml
    overlays:
      - type: APIs.io Search
        url: https://example.com/apis-io-search
      - type: API Evangelist Rating
        url: http://example.com/api-evangelist-ratings
    contact:
      - FN: APIs.json
        email: info@apisjson.org
        X-twitter: apisjson
common:
  - type: Signup
    url: https://example.com/signup
  - type: Login
    url: https://example.com/login
  - type: Authentication
    url: http://example.com/authentication
  - type: Blog
    url: http://example.com/blog
  - type: BlogFeed
    url: http://example.com/blog-feed
  - type: Pricing
    url: http://example.com/pricing
  - type: GettingStarted
    url: http://example.com/getting-started
  - type: Versioning
    url: http://example.com/versioning
  - type: TermsOfService
    url: http://example.com/terms-of-service
  - type: InterfaceLicense
    url: http://example.com/interfacce-license
  - type: PrivacyPolicy
    url: http://example.com/privacy-policy
  - type: DeprecationPolicy
    url: http://example.com/deprecation-policy
  - type: ServiceLevelAgreement
    url: http://example.com/service-level-agreement
  - type: Security
    url: http://example.com/security
  - type: SDKs
    url: http://example.com/sdks
  - type: StatusPage
    url: http://example.com/status-page
  - type: RateLimits
    url: http://example.com/rate-limits
  - type: Forums
    url: http://example.com/forums
  - type: Support
    url: http://example.com/support
  - type: ChangeLog
    url: http://example.com/change-log
  - type: RoadMap
    url: http://example.com/road-map
  - type: Contact
    url: http://example.com/contact
  - type: ErrorCodes
    url: http://example.com/error-codes
  - type: GitHubOrg
    url: http://example.com/github-org
  - type: GitHubRepo
    url: http://example.com/github-repo
  - type: Twitter
    url: http://example.com/twitter
  - type: AlertsTwitterHandle
    url: http://example.com/alerts-twitter-handle
  - type: Webhooks
    url: http://example.com/webhooks
  - type: Integrations
    url: http://example.com/integrations
overlays:
  - type: APIs.io Search
    url: https://example.com/apis-io-search
  - type: API Evangelist Ratings
    url: http://example.com/api-evangelist-ratings
include:
  - name: Another Example API
    url: http://example.com/apis.json
maintainers:
  - FN: Kin Lane
    X-twitter: apievangelist
    email: info@apievangelist.com
---
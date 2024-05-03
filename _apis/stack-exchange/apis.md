---
name: Stack Exchange
description: >-
  Stack Exchange is a network of question-and-answer websites on topics in
  diverse fields, each site covering a specific topic, where questions, answers,
  and users are subject to a reputation award process. The reputation system
  allows the sites to be self-moderating
image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
url: >-
  https://raw.githubusercontent.com/apis-json/artisanal/main/apis/stack-exchange.yml
created: 2023/11/15
modified: 2023/11/15
specificationVersion: '0.16'
tags: []
apis:
  - name: Stack Exchange API
    description: >-
      This is the documentation for the v2.3 Stack Exchange API (with both
      authentication and write support). If you have additional questions, or
      believe you have encountered a bug, don't hesitate to post a question on
      Stack Apps.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://api.stackexchange.com/
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: https://api.stackexchange.com/docs
      - type: OpenAPI
        url: >-
          https://raw.githubusercontent.com/openapis/api-specs/master/stackexchange/stackexchange-api-v2.2_swagger-v2.0.yaml
    contact:
      - FN: Stack Exchange
        url: http://stackapps.com/
        email: team+api@stackexchange.com
    overlays:
      - type: APIs.io Search
        url: >-
          overlays/https://raw.githubusercontent.com/openapis/api-specs/master/stackexchange/stackexchange-api-v2.2_swagger-v2.0.yaml-openapi-search.yml
    aid: stack-exchange:stack-exchange-api
common:
  - type: Authentication
    url: https://api.stackexchange.com/docs/authentication
  - type: Blog
    url: https://stackoverflow.blog/
  - type: Terms of Service
    url: https://stackexchange.com/legal/api-terms-of-use
  - type: Rate Limits
    url: https://api.stackexchange.com/docs/throttle
  - type: Sign UP
    url: http://stackapps.com/apps/oauth/register
  - type: Applications
    url: http://stackapps.com/apps/oauth
maintainers:
  - FN: Name
    url: http://example.com
    email: info@example.com
overlays:
  - type: APIs.io Search
    url: overlays/apis-io-search.yml
  - type: API Evangelist Ratings
    url: overlays/apis-io-search.yml
aid: stack-exchange
---
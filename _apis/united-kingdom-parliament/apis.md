---
name: United Kingdom Parliament
description: This is the description.
image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
url: https://raw.githubusercontent.com/apis-json/artisanal/main/apis/template.yml
created: 2024/01/01
modified: 2024/01/01
specificationVersion: '0.16'
tags: []
apis:
  - name: United Kingdom Parliament API
    description: This is the description.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://developer.parliament.uk/
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: https://developer.parliament.uk/
    overlays: []
    aid: united-kingdom-parliament:united-kingdom-parliament-api
common:
  - type: Portal
    url: https://developer.parliament.uk/
maintainers:
  - FN: API Evangelist
    url: http://apievangelist.com
    email: info@apievangelist.com
overlays:
  - type: APIs.io Search
    url: overlays/apis-io-search.yml
  - type: API Evangelist Ratings
    url: overlays/apis-io-search.yml
aid: united-kingdom-parliament
---
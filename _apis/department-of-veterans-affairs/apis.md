---
name: Department of Veterans Affairs (VA)
description: This is the description.
image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
url: https://raw.githubusercontent.com/apis-json/artisanal/main/apis/template.yml
created: 2024/01/01
modified: 2024/01/01
specificationVersion: '0.16'
tags: []
apis:
  - name: Department of Veterans Affairs (VA) API
    description: This is the description.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://developer.va.gov/
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: https://developer.va.gov/
    overlays: []
    aid: department-of-veterans-affairs-va:department-of-veterans-affairs-va-api
common:
  - type: Portal
    url: https://developer.va.gov/
maintainers:
  - FN: API Evangelist
    url: http://apievangelist.com
    email: info@apievangelist.com
overlays:
  - type: APIs.io Search
    url: overlays/apis-io-search.yml
  - type: API Evangelist Ratings
    url: overlays/apis-io-search.yml
aid: department-of-veterans-affairs-va
---
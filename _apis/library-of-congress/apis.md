---
name: Library of Congress
description: This is the description.
image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
url: https://raw.githubusercontent.com/apis-json/artisanal/main/apis/template.yml
created: 2024/01/01
modified: 2024/01/01
specificationVersion: '0.16'
tags: []
apis:
  - name: Library of Congress API
    description: This is the description.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://www.loc.gov/apis/
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: https://www.loc.gov/apis/
    overlays: []
    aid: library-of-congress:library-of-congress-api
common:
  - type: Portal
    url: https://www.loc.gov/apis/
maintainers:
  - FN: API Evangelist
    url: http://apievangelist.com
    email: info@apievangelist.com
overlays:
  - type: APIs.io Search
    url: overlays/apis-io-search.yml
  - type: API Evangelist Ratings
    url: overlays/apis-io-search.yml
aid: library-of-congress
---
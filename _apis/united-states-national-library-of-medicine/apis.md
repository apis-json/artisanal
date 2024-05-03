---
name: United States National Library of Medicine
description: This is the description.
image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
url: https://raw.githubusercontent.com/apis-json/artisanal/main/apis/template.yml
created: 2024/01/01
modified: 2024/01/01
specificationVersion: '0.16'
tags: []
apis:
  - name: United States National Library of Medicine Blast URL API
    description: >-
      The BLAST API allows developers to submit BLAST searches for processing at
      NCBI or cloud service provider(s) using HTTPS. The API can then check the
      status of submitted searches and retrieve results when ready in several
      formats.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: >-
      https://blast.ncbi.nlm.nih.gov/doc/blast-help/developerinfo.html#developerinfo
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: https://www.ncbi.nlm.nih.gov/home/develop/api/
    overlays: []
    aid: >-
      united-states-national-library-of-medicine:united-states-national-library-of-medicine-blast-url-api
common:
  - type: Portal
    url: https://www.ncbi.nlm.nih.gov/home/develop/api/
maintainers:
  - FN: API Evangelist
    url: http://apievangelist.com
    email: info@apievangelist.com
overlays:
  - type: APIs.io Search
    url: overlays/apis-io-search.yml
  - type: API Evangelist Ratings
    url: overlays/apis-io-search.yml
aid: united-states-national-library-of-medicine
---
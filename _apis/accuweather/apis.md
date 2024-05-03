---
name: AccuWeather
description: >-
  AccuWeather provides the world's most sophisticated weather intelligence to
  make lives simpler, safer, and better. Our mission is to save lives and
  protect property.
image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
url: >-
  https://raw.githubusercontent.com/apis-json/artisanal/main/apis/accuweather.yml
created: 2023/11/22
modified: 2023/11/22
specificationVersion: '0.16'
tags: []
apis:
  - name: AccuWeather Locations API
    description: >-
      Get a location key for your desired location. Use the location key to
      retrieve weather data from the Forecast or Current Conditions API.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://developer.accuweather.com/accuweather-locations-api/apis
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: https://developer.accuweather.com/accuweather-locations-api/apis
    overlays: []
    aid: accuweather:accuweather-locations-api
  - name: AccuWeather Forecast API
    description: Get forecast information for a specific location.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://developer.accuweather.com/accuweather-forecast-api/apis
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: https://developer.accuweather.com/accuweather-forecast-api/apis
    overlays: []
    aid: accuweather:accuweather-forecast-api
  - name: AccuWeather Current Conditions API
    description: Get Current Conditions data for a specific location.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://developer.accuweather.com/accuweather-current-conditions-api/apis
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: >-
          https://developer.accuweather.com/accuweather-current-conditions-api/apis
    overlays: []
    aid: accuweather:accuweather-current-conditions-api
  - name: AccuWeather Indices API
    description: >-
      Get daily index values for a specific location. Index availability varies
      by location.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://developer.accuweather.com/accuweather-indices-api/apis
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: https://developer.accuweather.com/accuweather-indices-api/apis
    overlays: []
    aid: accuweather:accuweather-indices-api
  - name: AccuWeather Weather Alarms API
    description: >-
      Get Weather Alarms for a specific location. AccuWeather Weather Alarms are
      determined using the daily forecasts for a location. An alarm exists for a
      location if the forecast weather meets or exceeds specific thresholds.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://developer.accuweather.com/accuweather-weather-alarms-api/apis
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: https://developer.accuweather.com/accuweather-weather-alarms-api/apis
    overlays: []
    aid: accuweather:accuweather-weather-alarms-api
  - name: AccuWeather Alerts API
    description: >-
      Get severe weather alerts from official Government Meteorological Agencies
      and leading global weather alert providers.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://developer.accuweather.com/accuweather-alerts-api/apis
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: https://developer.accuweather.com/accuweather-alerts-api/apis
    overlays: []
    aid: accuweather:accuweather-alerts-api
  - name: AccuWeather Imagery API
    description: Get radar and satellite images.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://developer.accuweather.com/accuweather-imagery-api/apis
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: https://developer.accuweather.com/accuweather-imagery-api/apis
    overlays: []
    aid: accuweather:accuweather-imagery-api
  - name: AccuWeather Tropical API
    description: >-
      Get current position, past positions, and forecasts for tropical cyclones
      worldwide.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://developer.accuweather.com/accuweather-tropical-api/apis
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: https://developer.accuweather.com/accuweather-tropical-api/apis
    overlays: []
    aid: accuweather:accuweather-tropical-api
  - name: AccuWeather Translations API
    description: >-
      Get a list of available languages. Get translations for specific groups of
      phrases.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://developer.accuweather.com/accuweather-translations-api/apis
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: https://developer.accuweather.com/accuweather-translations-api/apis
    overlays: []
    aid: accuweather:accuweather-translations-api
  - name: AccuWeather MinuteCast® API
    description: Get a 120-minute precipitation forecast by latitude and longitude.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://developer.accuweather.com/minutecast-api/apis
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: https://developer.accuweather.com/minutecast-api/apis
    overlays: []
    aid: accuweather:accuweather-minutecast-api
common:
  - type: Best Practices
    url: https://developer.accuweather.com/best-practices
  - type: Status
    url: https://status.accuweather.com/
  - type: Terms of Service
    url: https://developer.accuweather.com/legal
  - type: FAQ
    url: https://developer.accuweather.com/faq-page
  - type: Plans
    url: https://developer.accuweather.com/packages
  - type: Privacy
    url: http://www.accuweather.com/en/privacy
  - type: Press
    url: http://www.accuweather.com/en/press
maintainers:
  - FN: API Evangelist
    url: http://apievangelist.com
    email: info@apievangelist.com
overlays:
  - type: APIs.io Search
    url: overlays/apis-io-search.yml
  - type: API Evangelist Ratings
    url: overlays/apis-io-search.yml
aid: accuweather
---
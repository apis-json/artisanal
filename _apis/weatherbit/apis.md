---
name: Weatherbit
description: >-
  Our mission at Weatherbit.io is pretty simple. It is to provide the highest
  quality weather forecasts, observations, and historical weather data
  possibl-e.
image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
url: https://raw.githubusercontent.com/apis-json/artisanal/main/apis/weatherbit.yml
created: 2023/11/20
modified: 2023/11/20
specificationVersion: '0.16'
tags: []
apis:
  - name: Weatherbit Current Weather API
    description: >-
      This API returns current conditions from our network of sub-hourly
      reporting weather stations, as well as relevant atmospheric meso-analyses
      (For example, the RTMA). Every API request will return the nearest, and
      most recent observation.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://www.weatherbit.io/api/weather-current
    baseURL: http://api.weatherbit.io
    tags: []
    properties:
      - type: Documentation
        url: https://www.weatherbit.io/api/weather-current
    overlays: []
    aid: weatherbit:weatherbit-current-weather-api
  - name: Weatherbit Severe Weather Alerts API
    description: >+
      This API returns severe weather alerts issued by local meteorological
      agencies. Current supported countries include: The USA via NOAA. European
      Union member nations, the United Kingdom, and Israel via Meteoalarm. As
      well as weather alerts for Canada via Environment Canada, and China via
      the China Meteorological Administration.

    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://www.weatherbit.io/api/alerts
    baseURL: https://api.weatherbit.io
    tags: []
    properties:
      - type: Documentation
        url: https://www.weatherbit.io/api/alerts
    overlays: []
    aid: weatherbit:weatherbit-severe-weather-alerts-api
  - name: Weatherbit Weather Forecast API
    description: >-
      Improve your business applications with accurate forecasts derived from
      the world's best high resolution global, and regional weather models.
      These forecasts incorporate corrections for model biases using state of
      the art machine learning methods. Our temperature forecasts consistently
      outperform those of all competitors, including the US National Weather
      Service! View our live forecast verification page to see how our API has
      performed against the competition over the past 30 days.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://www.weatherbit.io/api/weather-forecast-api
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: https://www.weatherbit.io/api/weather-forecast-api
    overlays: []
    aid: weatherbit:weatherbit-weather-forecast-api
  - name: Weatherbit Historical Weather API
    description: >-
      The Historical Weather API allows you to quickly retrieve accurate, high
      resolution historical weather data for any location in the world. Our
      curated weather data is backed by over 120,000 weather stations as well as
      high resolution gridded weather datasets such as the ERA-5 re-analysis,
      and global satellite / doppler radar. Data retrieved from our API is
      gap-free (minimal missing data) due to its application of advanced machine
      learning, and statistical backfilling techniques.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://www.weatherbit.io/api/historical-weather-api
    baseURL: https://api.weatherbit.io
    tags: []
    properties:
      - type: Documentation
        url: https://www.weatherbit.io/api/historical-weather-api
    overlays: []
    aid: weatherbit:weatherbit-historical-weather-api
  - name: Weatherbit Ag-Weather API
    description: >-
      Use our service to retrieve derived data specific to the agriculture
      industry. This API utilizes the state of the art GLDAS re-analysis to
      provide global coverage at a spatial resolution of 0.25 degrees.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://www.weatherbit.io/api/agweather-api
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: https://www.weatherbit.io/api/agweather-api
    overlays: []
    aid: weatherbit:weatherbit-ag-weather-api
  - name: Weatherbit Air Quality API
    description: >
      Enrich your business applications with high quality air quality data
      derived from the world's most advanced global, and regional air quality
      models. As well as thousands of air quality monitoring stations around the
      world.
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://www.weatherbit.io/api/air-quality-api
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: https://www.weatherbit.io/api/air-quality-api
    overlays: []
    aid: weatherbit:weatherbit-air-quality-api
common:
  - type: Plans
    url: https://www.weatherbit.io/pricing
  - type: Features
    url: https://www.weatherbit.io/features
  - type: FAQs
    url: https://help.weatherbit.io/faq/
  - type: Status
    url: https://status.weatherbit.io/
  - type: Blog
    url: https://blog.weatherbit.io/
  - type: Knowledge
    url: https://help.weatherbit.io/
  - type: Sign Up
    url: https://www.weatherbit.io/account/create
  - type: Login
    url: https://www.weatherbit.io/account/login
  - type: Terms of Service
    url: https://www.weatherbit.io/terms
  - type: Privacy Policy
    url: https://www.weatherbit.io/privacy
  - type: Contact
    url: https://www.weatherbit.io/contact
maintainers:
  - FN: API Evangelist
    url: http://apievangelist.com
    email: info@apievangelist.com
overlays:
  - type: APIs.io Search
    url: overlays/apis-io-search.yml
  - type: API Evangelist Ratings
    url: overlays/apis-io-search.yml
aid: weatherbit
---
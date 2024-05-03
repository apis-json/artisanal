---
name: Abandoned Carts
description: Needs a description.
image: >-
  https://kinlane-productions2.s3.amazonaws.com/apis-json-icons/abandoned-carts.png
url: https://example.com/apis/abandoned-carts.yml
created: 2024/4/8
modified: 2024/4/8
specificationVersion: '0.16'
tags:
  - Abandoned Carts
apis:
  - aid: bigcommerce:abandoned-carts
    name: Abandoned Carts
    description: Needs a description
    image: https://kinlane-productions2.s3.amazonaws.com/apis-json/apis-json-logo.jpg
    humanURL: https://developer.bigcommerce.com/
    baseURL: https://api.example.com
    tags: []
    properties:
      - type: Documentation
        url: https://developer.bigcommerce.com/
      - type: OpenAPI
        data:
          openapi: 3.0.0
          info:
            version: ''
            title: Abandoned Carts
          tags:
            - name: Abandoned Carts
            - name: Abandoned Cart Settings
            - name: Abandoned Carts Settings
          paths:
            /abandoned-carts/settings:
              get:
                summary: Get Global Abandoned Cart Settings
                description: Returns the global abandoned cart settings of a store.
                tags:
                  - Get
                  - Global
                  - Abandoned
                  - Cart
                  - Settings
                  - Abandoned
                  - Carts
                  - Settings
              put:
                summary: Update Global Abandoned Cart Settings
                description: Updates the global abandoned cart settings of a store.
                tags:
                  - Update
                  - Global
                  - Abandoned
                  - Cart
                  - Settings
                  - Abandoned
                  - Carts
                  - Settings
              parameters:
                - null
            /abandoned-carts/settings/channels/{channel_id}:
              get:
                summary: Get Channel Abandoned Cart Settings
                description: >-
                  Returns the per-channel overrides for the abandoned cart
                  settings of a store.
                tags:
                  - Get
                  - Channel
                  - Abandoned
                  - Cart
                  - Settings
                  - Abandoned
                  - Carts
                  - Settings
                  - Channels
                  - Channel_id
              put:
                summary: Update Channel Abandoned Cart Settings
                description: >-
                  Updates the per-channel overrides for the abandoned cart
                  settings of a store.


                  #### OAuth Scopes

                  | UI Name                                      | Permission |
                  Parameter                                     |

                  |-||--|     

                  | Information & Settings                       | modify     |
                  `store_v2_information`                        |
                tags:
                  - Update
                  - Channel
                  - Abandoned
                  - Cart
                  - Settings
                  - Abandoned
                  - Carts
                  - Settings
                  - Channels
                  - Channel_id
              parameters:
                - null
                - null
            /abandoned-carts/{token}:
              get:
                summary: Get an Abandoned Cart
                description: >-
                  Returns the `cart_id` corresponding to the abandoned cart
                  `{token}` passed in.


                  **Usage Notes**:

                  * `{token}` is the token in the query string of the abandoned
                  cart link found in abandoned cart email notifications to
                  shoppers
                tags:
                  - Get
                  - An
                  - Abandoned
                  - Cart
                  - Abandoned
                  - Carts
                  - Settings
                  - Channels
                  - Channel_id
                  - Token
              parameters:
                - null
                - null
    overlays:
      - type: APIs.io Search
        url: overlays/abandoned-carts-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/abandoned-carts-openapi-api-evangelist-ratings.yml
maintainers:
  - FN: API Evangelist
    email: info@apievangelist.com
---
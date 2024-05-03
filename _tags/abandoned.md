---
name: Abandoned
description: Needs a description.
image: https://kinlane-productions2.s3.amazonaws.com/apis-json-icons/abandoned.png
url: https://example.com/apis/abandoned.yml
created: 2024/4/8
modified: 2024/4/8
specificationVersion: '0.16'
tags:
  - Abandoned
apis:
  - aid: bigcommerce:abandoned-cart-emails
    name: Abandoned Cart Emails
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
            title: Abandoned Cart Emails
          tags:
            - name: Abandoned Cart Emails
            - name: Template settings
          paths:
            /marketing/abandoned-cart-emails:
              get:
                description: An array of abandoned cart emails pertaining to a store.
                tags:
                  - Get
                  - All
                  - Abandoned
                  - Cart
                  - Email
                  - Templates
                  - Marketing
                  - Abandoned
                  - Cart
                  - Emails
                summary: Get all abandoned cart email templates
              post:
                summary: Create abandoned cart email template
                tags:
                  - Create
                  - Abandoned
                  - Cart
                  - Email
                  - Template
                  - Marketing
                  - Abandoned
                  - Cart
                  - Emails
                description: Create an Abandoned Cart Email template.
              parameters:
                - null
            /marketing/abandoned-cart-emails/{id}:
              get:
                summary: Get an email template
                description: Get a single Abandoned Cart Email template.
                tags:
                  - Get
                  - An
                  - Email
                  - Template
                  - Marketing
                  - Abandoned
                  - Cart
                  - Emails
                  - Id
              put:
                summary: Update an email template
                description: Update an email template.
                tags:
                  - Update
                  - An
                  - Email
                  - Template
                  - Marketing
                  - Abandoned
                  - Cart
                  - Emails
                  - Id
              delete:
                tags:
                  - Delete
                  - Email
                  - Template
                  - Marketing
                  - Abandoned
                  - Cart
                  - Emails
                  - Id
                description: Delete Abandoned Cart Email template.
                summary: Delete email template
              parameters:
                - null
                - null
            /marketing/abandoned-cart-emails/default:
              get:
                summary: Get default email template
                description: Return default Abandoned Cart Email template.
                tags:
                  - Get
                  - Default
                  - Email
                  - Template
                  - Marketing
                  - Abandoned
                  - Cart
                  - Emails
                  - Id
                  - Default
              parameters:
                - null
            /marketing/abandoned-cart-emails/settings:
              get:
                summary: Get email template settings
                tags:
                  - Get
                  - Email
                  - Template
                  - Settings
                  - Marketing
                  - Abandoned
                  - Cart
                  - Emails
                  - Id
                  - Default
                  - Settings
                description: Read Abandoned Cart Email Template settings.
              put:
                summary: Update email template settings
                tags:
                  - Update
                  - Email
                  - Template
                  - Settings
                  - Marketing
                  - Abandoned
                  - Cart
                  - Emails
                  - Id
                  - Default
                  - Settings
                description: Update Abandoned Cart Email template settings.
              parameters:
                - null
    overlays:
      - type: APIs.io Search
        url: overlays/abandoned-cart-emails-openapi-search.yml
      - type: API Evangelist Ratings
        url: overlays/abandoned-cart-emails-openapi-api-evangelist-ratings.yml
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
---
openapi: 3.0.0
info:
  title: Stripe Exchange Rates API
  description: Needs description.
  contact:
    email: dev-platform@stripe.com
    name: Stripe Dev Platform Team
    url: 'https://stripe.com'
  termsOfService: 'https://stripe.com/us/terms/'
  version: '2023-10-16'
  x-stripeSpecFilename: spec3
security:
  - basicAuth: []
  - bearerAuth: []
servers:
  - url: 'https://api.stripe.com/'
paths:
  /v1/exchange_rates:
    get:
      description: >-
        <p>Returns a list of objects that contain the rates at which foreign
        currencies are converted to one another. Only shows the currencies for
        which Stripe supports.</p>
      operationId: GetExchangeRates
      parameters:
        - description: >-
            A cursor for use in pagination. `ending_before` is the currency that
            defines your place in the list. For instance, if you make a list
            request and receive 100 objects, starting with the exchange rate for
            currency X your subsequent call can include `ending_before=obj_bar`
            in order to fetch the previous page of the list.
          in: query
          name: ending_before
          required: false
          schema:
            maxLength: 5000
            type: string
          style: form
        - description: Specifies which fields in the response should be expanded.
          explode: true
          in: query
          name: expand
          required: false
          schema:
            items:
              maxLength: 5000
              type: string
            type: array
          style: deepObject
        - description: >-
            A limit on the number of objects to be returned. Limit can range
            between 1 and total number of supported payout currencies, and the
            default is the max.
          in: query
          name: limit
          required: false
          schema:
            type: integer
          style: form
        - description: >-
            A cursor for use in pagination. `starting_after` is the currency
            that defines your place in the list. For instance, if you make a
            list request and receive 100 objects, ending with the exchange rate
            for currency X, your subsequent call can include `starting_after=X`
            in order to fetch the next page of the list.
          in: query
          name: starting_after
          required: false
          schema:
            maxLength: 5000
            type: string
          style: form
      requestBody:
        content:
          application/x-www-form-urlencoded:
            encoding: {}
            schema:
              additionalProperties: false
              properties: {}
              type: object
        required: false
      responses:
        '200':
          content:
            application/json:
              schema:
                description: ''
                properties:
                  data:
                    items:
                      $ref: '#/components/schemas/exchange_rate'
                    type: array
                  has_more:
                    description: >-
                      True if this list has another page of items after this one
                      that can be fetched.
                    type: boolean
                  object:
                    description: >-
                      String representing the object's type. Objects of the same
                      type share the same value. Always has the value `list`.
                    enum:
                      - list
                    type: string
                  url:
                    description: The URL where this list can be accessed.
                    maxLength: 5000
                    pattern: ^/v1/exchange_rates
                    type: string
                required:
                  - data
                  - has_more
                  - object
                  - url
                title: ExchangeRateList
                type: object
                x-expandableFields:
                  - data
          description: Successful response.
        default:
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/error'
          description: Error response.
      summary: Retrieve Exchange Rates
      tags:
        - Exchanges
        - Rates
  '/v1/exchange_rates/{rate_id}':
    get:
      description: >-
        <p>Retrieves the exchange rates from the given currency to every
        supported currency.</p>
      operationId: GetExchangeRatesRateId
      parameters:
        - description: Specifies which fields in the response should be expanded.
          explode: true
          in: query
          name: expand
          required: false
          schema:
            items:
              maxLength: 5000
              type: string
            type: array
          style: deepObject
        - in: path
          name: rate_id
          required: true
          schema:
            maxLength: 5000
            type: string
          style: simple
      requestBody:
        content:
          application/x-www-form-urlencoded:
            encoding: {}
            schema:
              additionalProperties: false
              properties: {}
              type: object
        required: false
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/exchange_rate'
          description: Successful response.
        default:
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/error'
          description: Error response.
      summary: Retrieve Exchange Rate
      tags:
        - Exchanges
        - Rates
components:
  schemas:
    error:
      description: An error response from the Stripe API
      properties:
        error:
          $ref: '#/components/schemas/api_errors'
      required:
        - error
      type: object
    exchange_rate:
      description: >-
        `ExchangeRate` objects allow you to determine the rates that Stripe is
        currently

        using to convert from one currency to another. Since this number is
        variable

        throughout the day, there are various reasons why you might want to know
        the current

        rate (for example, to dynamically price an item for a user with a
        default

        payment in a foreign currency).


        Please refer to our [Exchange Rates
        API](https://stripe.com/docs/fx-rates) guide for more details.


        *[Note: this integration path is supported but no longer recommended]*
        Additionally,

        you can guarantee that a charge is made with an exchange rate that you
        expect is

        current. To do so, you must pass in the exchange_rate to charges
        endpoints. If the

        value is no longer up to date, the charge won't go through. Please refer
        to our

        [Using with charges](https://stripe.com/docs/exchange-rates) guide for
        more details.


        --

         

        *This Exchange Rates API is a Beta Service and is subject to Stripe's
        terms of service. You may use the API solely for the purpose of
        transacting on Stripe. For example, the API may be queried in order to:*


        - *localize prices for processing payments on Stripe*

        - *reconcile Stripe transactions*

        - *determine how much money to send to a connected account*

        - *determine app fees to charge a connected account*


        *Using this Exchange Rates API beta for any purpose other than to
        transact on Stripe is strictly prohibited and constitutes a violation of
        Stripe's terms of service.*
      properties:
        id:
          description: >-
            Unique identifier for the object. Represented as the three-letter
            [ISO currency
            code](https://www.iso.org/iso-4217-currency-codes.html) in
            lowercase.
          maxLength: 5000
          type: string
        object:
          description: >-
            String representing the object's type. Objects of the same type
            share the same value.
          enum:
            - exchange_rate
          type: string
        rates:
          additionalProperties:
            type: number
          description: >-
            Hash where the keys are supported currencies and the values are the
            exchange rate at which the base id currency converts to the key
            currency.
          type: object
      required:
        - id
        - object
        - rates
      title: ExchangeRate
      type: object
      x-expandableFields: []
      x-resourceId: exchange_rate
  securitySchemes:
    basicAuth:
      description: >-
        Basic HTTP authentication. Allowed headers-- Authorization: Basic
        <api_key> | Authorization: Basic <base64 hash of `api_key:`>
      scheme: basic
      type: http
    bearerAuth:
      bearerFormat: auth-scheme
      description: >-
        Bearer HTTP authentication. Allowed headers-- Authorization: Bearer
        <api_key>
      scheme: bearer
      type: http
tags:
  - name: Exchanges
    description: Needs a description.
  - name: Rates
    description: Needs a description.
---
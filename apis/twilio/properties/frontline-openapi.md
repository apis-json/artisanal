---
components:
  schemas:
    frontline.v1.user:
      type: object
      properties:
        sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^US[0-9a-fA-F]{32}$'
          nullable: true
          description: The unique string that we created to identify the User resource.
        identity:
          type: string
          nullable: true
          description: >-
            The application-defined string that uniquely identifies the
            resource's User. This value is often a username or an email address,
            and is case-sensitive.
          x-twilio:
            pii:
              handling: standard
              deleteSla: 30
        friendly_name:
          type: string
          nullable: true
          description: The string that you assigned to describe the User.
          x-twilio:
            pii:
              handling: standard
              deleteSla: 30
        avatar:
          type: string
          nullable: true
          description: The avatar URL which will be shown in Frontline application.
        state:
          type: string
          $ref: '#/components/schemas/user_enum_state_type'
          nullable: true
          description: >-
            Current state of this user. Can be either `active` or `deactivated`
            and defaults to `active`
        is_available:
          type: boolean
          nullable: true
          description: >-
            Whether the User is available for new conversations. Defaults to
            `false` for new users.
        url:
          type: string
          format: uri
          nullable: true
          description: An absolute API resource URL for this user.
    user_enum_state_type:
      type: string
      enum:
        - active
        - deactivated
  securitySchemes:
    accountSid_authToken:
      type: http
      scheme: basic
info:
  title: Twilio Frontline API
  description: Twilio Frontline is limited to existing Frontline accounts only. New and existing Twilio customers without previous access to Frontline will not be able to get Frontline through Twilio’s Console nor access developer documentation.
  termsOfService: 'https://www.twilio.com/legal/tos'
  contact:
    name: Twilio Support
    url: 'https://support.twilio.com'
    email: support@twilio.com
  license:
    name: Apache 2.0
    url: 'https://www.apache.org/licenses/LICENSE-2.0.html'
  version: 1.52.0
openapi: 3.0.1
paths:
  '/v1/Users/{Sid}':
    servers:
      - url: 'https://frontline-api.twilio.com'
    description: A User resource represents a frontline user.
    x-twilio:
      defaultOutputProperties:
        - sid
        - identity
      pathType: instance
    get:
      description: Fetch a frontline user
      tags:
        - Sales
        - ' Relationships'
        - ' Users'
      parameters:
        - name: Sid
          in: path
          description: >-
            The SID of the User resource to fetch. This value can be either the
            `sid` or the `identity` of the User resource to fetch.
          schema:
            type: string
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/frontline.v1.user'
          description: OK
      security:
        - accountSid_authToken: []
      operationId: FetchUser
      x-maturity:
        - Beta
      summary: Retrieve User
    post:
      description: Update an existing frontline user
      tags:
        - Sales
        - ' Relationships'
        - ' Users'
      parameters:
        - name: Sid
          in: path
          description: >-
            The SID of the User resource to update. This value can be either the
            `sid` or the `identity` of the User resource to update.
          schema:
            type: string
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/frontline.v1.user'
          description: OK
      security:
        - accountSid_authToken: []
      operationId: UpdateUser
      x-maturity:
        - Beta
      requestBody:
        content:
          application/x-www-form-urlencoded:
            schema:
              type: object
              title: UpdateUserRequest
              properties:
                FriendlyName:
                  type: string
                  description: The string that you assigned to describe the User.
                Avatar:
                  type: string
                  description: The avatar URL which will be shown in Frontline application.
                State:
                  type: string
                  $ref: '#/components/schemas/user_enum_state_type'
                  description: >-
                    Current state of this user. Can be either `active` or
                    `deactivated`.
                IsAvailable:
                  type: boolean
                  description: >-
                    Whether the User is available for new conversations. Set to
                    `false` to prevent User from receiving new inbound
                    conversations if you are using [Pool
                    Routing](https://www.twilio.com/docs/frontline/handle-incoming-conversations#3-pool-routing).
      summary: Update User
servers:
  - url: 'https://frontline-api.twilio.com'
tags:
  - name: Frontline
    description: Needs a description.
  - name: Sales
    description: Needs a description.
  - name: ' Relationships'
    description: Needs a description.
  - name: ' Users'
    description: Needs a description.
x-maturity:
  - name: Beta
    description: >-
      PLEASE NOTE that this is a Beta product that is subject to change. Use it
      with caution.
---
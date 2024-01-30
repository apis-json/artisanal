---
components:
  schemas:
    trusthub.v1.compliance_inquiry:
      type: object
      properties:
        inquiry_id:
          type: string
          nullable: true
          description: >-
            The unique ID used to start an embedded compliance registration
            session.
        inquiry_session_token:
          type: string
          nullable: true
          description: >-
            The session token used to start an embedded compliance registration
            session.
        customer_id:
          type: string
          nullable: true
          description: >-
            The CustomerID matching the Customer Profile that should be resumed
            or resubmitted for editing.
        url:
          type: string
          format: uri
          nullable: true
          description: The URL of this resource.
    trusthub.v1.compliance_tollfree_inquiry:
      type: object
      properties:
        inquiry_id:
          type: string
          nullable: true
          description: >-
            The unique ID used to start an embedded compliance registration
            session.
        inquiry_session_token:
          type: string
          nullable: true
          description: >-
            The session token used to start an embedded compliance registration
            session.
        registration_id:
          type: string
          nullable: true
          description: >-
            The TolfreeId matching the Tollfree Profile that should be resumed
            or resubmitted for editing.
        url:
          type: string
          format: uri
          nullable: true
          description: The URL of this resource.
    compliance_tollfree_inquiry_enum_status:
      type: string
      enum:
        - PENDING_REVIEW
        - IN_REVIEW
        - TWILIO_APPROVED
        - TWILIO_REJECTED
    compliance_tollfree_inquiry_enum_opt_in_type:
      type: string
      enum:
        - VERBAL
        - WEB_FORM
        - PAPER_FORM
        - VIA_TEXT
        - MOBILE_QR_CODE
    trusthub.v1.customer_profile:
      type: object
      properties:
        sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^BU[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string that we created to identify the Customer-Profile
            resource.
        account_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^AC[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The SID of the
            [Account](https://www.twilio.com/docs/iam/api/account) that created
            the Customer-Profile resource.
        policy_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^RN[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string of a policy that is associated to the
            Customer-Profile resource.
        friendly_name:
          type: string
          nullable: true
          description: The string that you assigned to describe the resource.
        status:
          type: string
          $ref: '#/components/schemas/customer_profile_enum_status'
          nullable: true
          description: The verification status of the Customer-Profile resource.
        valid_until:
          type: string
          format: date-time
          nullable: true
          description: >-
            The date and time in GMT in [ISO
            8601](https://en.wikipedia.org/wiki/ISO_8601) format when the
            resource will be valid until.
        email:
          type: string
          nullable: true
          description: >-
            The email address that will receive updates when the
            Customer-Profile resource changes status.
        status_callback:
          type: string
          format: uri
          nullable: true
          description: The URL we call to inform your application of status changes.
        date_created:
          type: string
          format: date-time
          nullable: true
          description: >-
            The date and time in GMT when the resource was created specified in
            [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format.
        date_updated:
          type: string
          format: date-time
          nullable: true
          description: >-
            The date and time in GMT when the resource was last updated
            specified in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)
            format.
        url:
          type: string
          format: uri
          nullable: true
          description: The absolute URL of the Customer-Profile resource.
        links:
          type: object
          format: uri-map
          nullable: true
          description: The URLs of the Assigned Items of the Customer-Profile resource.
    customer_profile_enum_status:
      type: string
      enum:
        - draft
        - pending-review
        - in-review
        - twilio-rejected
        - twilio-approved
    customer_profile_enum_end_user_type:
      type: string
      enum:
        - individual
        - business
    trusthub.v1.customer_profile.customer_profile_channel_endpoint_assignment:
      type: object
      properties:
        sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^RA[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string that we created to identify the Item Assignment
            resource.
        customer_profile_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^BU[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string that we created to identify the CustomerProfile
            resource.
        account_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^AC[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The SID of the
            [Account](https://www.twilio.com/docs/iam/api/account) that created
            the Item Assignment resource.
        channel_endpoint_type:
          type: string
          nullable: true
          description: 'The type of channel endpoint. eg: phone-number'
        channel_endpoint_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^[a-zA-Z]{2}[0-9a-fA-F]{32}$'
          nullable: true
          description: The SID of an channel endpoint
        date_created:
          type: string
          format: date-time
          nullable: true
          description: >-
            The date and time in GMT when the resource was created specified in
            [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format.
        url:
          type: string
          format: uri
          nullable: true
          description: The absolute URL of the Identity resource.
    trusthub.v1.customer_profile.customer_profile_entity_assignment:
      type: object
      properties:
        sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^BV[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string that we created to identify the Item Assignment
            resource.
        customer_profile_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^BU[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string that we created to identify the CustomerProfile
            resource.
        account_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^AC[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The SID of the
            [Account](https://www.twilio.com/docs/iam/api/account) that created
            the Item Assignment resource.
        object_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^[a-zA-Z]{2}[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The SID of an object bag that holds information of the different
            items.
        date_created:
          type: string
          format: date-time
          nullable: true
          description: >-
            The date and time in GMT when the resource was created specified in
            [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format.
        url:
          type: string
          format: uri
          nullable: true
          description: The absolute URL of the Identity resource.
    trusthub.v1.customer_profile.customer_profile_evaluation:
      type: object
      properties:
        sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^EL[0-9a-fA-F]{32}$'
          nullable: true
          description: The unique string that identifies the Evaluation resource.
        account_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^AC[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The SID of the
            [Account](https://www.twilio.com/docs/iam/api/account) that created
            the customer_profile resource.
        policy_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^RN[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string of a policy that is associated to the
            customer_profile resource.
        customer_profile_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^BU[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string that we created to identify the customer_profile
            resource.
        status:
          type: string
          $ref: '#/components/schemas/customer_profile_evaluation_enum_status'
          nullable: true
          description: The compliance status of the Evaluation resource.
        results:
          type: array
          items: {}
          nullable: true
          description: >-
            The results of the Evaluation which includes the valid and invalid
            attributes.
        date_created:
          type: string
          format: date-time
          nullable: true
        url:
          type: string
          format: uri
          nullable: true
    customer_profile_evaluation_enum_status:
      type: string
      enum:
        - compliant
        - noncompliant
    trusthub.v1.end_user:
      type: object
      properties:
        sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^IT[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string created by Twilio to identify the End User
            resource.
        account_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^AC[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The SID of the
            [Account](https://www.twilio.com/docs/iam/api/account) that created
            the End User resource.
        friendly_name:
          type: string
          nullable: true
          description: The string that you assigned to describe the resource.
        type:
          type: string
          nullable: true
          description: >-
            The type of end user of the Bundle resource - can be `individual` or
            `business`.
        attributes:
          nullable: true
          description: >-
            The set of parameters that are the attributes of the End Users
            resource which are listed in the End User Types.
          x-twilio:
            pii:
              handling: standard
              deleteSla: 30
        date_created:
          type: string
          format: date-time
          nullable: true
          description: >-
            The date and time in GMT when the resource was created specified in
            [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format.
        date_updated:
          type: string
          format: date-time
          nullable: true
          description: >-
            The date and time in GMT when the resource was last updated
            specified in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)
            format.
        url:
          type: string
          format: uri
          nullable: true
          description: The absolute URL of the End User resource.
    trusthub.v1.end_user_type:
      type: object
      properties:
        sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^OY[0-9a-fA-F]{32}$'
          nullable: true
          description: The unique string that identifies the End-User Type resource.
        friendly_name:
          type: string
          nullable: true
          description: >-
            A human-readable description that is assigned to describe the
            End-User Type resource. Examples can include first name, last name,
            email, business name, etc
        machine_name:
          type: string
          nullable: true
          description: >-
            A machine-readable description of the End-User Type resource.
            Examples can include first_name, last_name, email, business_name,
            etc.
        fields:
          type: array
          items: {}
          nullable: true
          description: >-
            The required information for creating an End-User. The required
            fields will change as regulatory needs change and will differ for
            businesses and individuals.
        url:
          type: string
          format: uri
          nullable: true
          description: The absolute URL of the End-User Type resource.
    trusthub.v1.policies:
      type: object
      properties:
        sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^RN[0-9a-fA-F]{32}$'
          nullable: true
          description: The unique string that identifies the Policy resource.
        friendly_name:
          type: string
          nullable: true
          description: >-
            A human-readable description that is assigned to describe the Policy
            resource. Examples can include Primary Customer profile policy
        requirements:
          nullable: true
          description: The SID of an object that holds the policy information
        url:
          type: string
          format: uri
          nullable: true
          description: The absolute URL of the Policy resource.
    policies_enum_end_user_type:
      type: string
      enum:
        - individual
        - business
    trusthub.v1.supporting_document:
      type: object
      properties:
        sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^RD[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string created by Twilio to identify the Supporting
            Document resource.
        account_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^AC[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The SID of the
            [Account](https://www.twilio.com/docs/iam/api/account) that created
            the Document resource.
        friendly_name:
          type: string
          nullable: true
          description: The string that you assigned to describe the resource.
        mime_type:
          type: string
          nullable: true
          description: The image type uploaded in the Supporting Document container.
        status:
          type: string
          $ref: '#/components/schemas/supporting_document_enum_status'
          nullable: true
          description: The verification status of the Supporting Document resource.
        type:
          type: string
          nullable: true
          description: The type of the Supporting Document.
        attributes:
          nullable: true
          description: >-
            The set of parameters that are the attributes of the Supporting
            Documents resource which are listed in the Supporting Document
            Types.
          x-twilio:
            pii:
              handling: standard
              deleteSla: 30
        date_created:
          type: string
          format: date-time
          nullable: true
          description: >-
            The date and time in GMT when the resource was created specified in
            [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format.
        date_updated:
          type: string
          format: date-time
          nullable: true
          description: >-
            The date and time in GMT when the resource was last updated
            specified in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)
            format.
        url:
          type: string
          format: uri
          nullable: true
          description: The absolute URL of the Supporting Document resource.
    supporting_document_enum_status:
      type: string
      enum:
        - draft
        - pending-review
        - rejected
        - approved
        - expired
        - provisionally-approved
    trusthub.v1.supporting_document_type:
      type: object
      properties:
        sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^OY[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string that identifies the Supporting Document Type
            resource.
        friendly_name:
          type: string
          nullable: true
          description: >-
            A human-readable description of the Supporting Document Type
            resource.
        machine_name:
          type: string
          nullable: true
          description: >-
            The machine-readable description of the Supporting Document Type
            resource.
        fields:
          type: array
          items: {}
          nullable: true
          description: >-
            The required information for creating a Supporting Document. The
            required fields will change as regulatory needs change and will
            differ for businesses and individuals.
        url:
          type: string
          format: uri
          nullable: true
          description: The absolute URL of the Supporting Document Type resource.
    trusthub.v1.trust_product:
      type: object
      properties:
        sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^BU[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string that we created to identify the Customer-Profile
            resource.
        account_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^AC[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The SID of the
            [Account](https://www.twilio.com/docs/iam/api/account) that created
            the Customer-Profile resource.
        policy_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^RN[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string of a policy that is associated to the
            Customer-Profile resource.
        friendly_name:
          type: string
          nullable: true
          description: The string that you assigned to describe the resource.
        status:
          type: string
          $ref: '#/components/schemas/trust_product_enum_status'
          nullable: true
          description: The verification status of the Customer-Profile resource.
        valid_until:
          type: string
          format: date-time
          nullable: true
          description: >-
            The date and time in GMT in [ISO
            8601](https://en.wikipedia.org/wiki/ISO_8601) format when the
            resource will be valid until.
        email:
          type: string
          nullable: true
          description: >-
            The email address that will receive updates when the
            Customer-Profile resource changes status.
        status_callback:
          type: string
          format: uri
          nullable: true
          description: The URL we call to inform your application of status changes.
        date_created:
          type: string
          format: date-time
          nullable: true
          description: >-
            The date and time in GMT when the resource was created specified in
            [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format.
        date_updated:
          type: string
          format: date-time
          nullable: true
          description: >-
            The date and time in GMT when the resource was last updated
            specified in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)
            format.
        url:
          type: string
          format: uri
          nullable: true
          description: The absolute URL of the Customer-Profile resource.
        links:
          type: object
          format: uri-map
          nullable: true
          description: The URLs of the Assigned Items of the Customer-Profile resource.
    trust_product_enum_status:
      type: string
      enum:
        - draft
        - pending-review
        - in-review
        - twilio-rejected
        - twilio-approved
    trust_product_enum_end_user_type:
      type: string
      enum:
        - individual
        - business
    trusthub.v1.trust_product.trust_product_channel_endpoint_assignment:
      type: object
      properties:
        sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^RA[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string that we created to identify the Item Assignment
            resource.
        trust_product_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^BU[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string that we created to identify the CustomerProfile
            resource.
        account_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^AC[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The SID of the
            [Account](https://www.twilio.com/docs/iam/api/account) that created
            the Item Assignment resource.
        channel_endpoint_type:
          type: string
          nullable: true
          description: 'The type of channel endpoint. eg: phone-number'
        channel_endpoint_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^[a-zA-Z]{2}[0-9a-fA-F]{32}$'
          nullable: true
          description: The SID of an channel endpoint
        date_created:
          type: string
          format: date-time
          nullable: true
          description: >-
            The date and time in GMT when the resource was created specified in
            [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format.
        url:
          type: string
          format: uri
          nullable: true
          description: The absolute URL of the Identity resource.
    trusthub.v1.trust_product.trust_product_entity_assignment:
      type: object
      properties:
        sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^BV[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string that we created to identify the Item Assignment
            resource.
        trust_product_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^BU[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string that we created to identify the TrustProduct
            resource.
        account_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^AC[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The SID of the
            [Account](https://www.twilio.com/docs/iam/api/account) that created
            the Item Assignment resource.
        object_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^[a-zA-Z]{2}[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The SID of an object bag that holds information of the different
            items.
        date_created:
          type: string
          format: date-time
          nullable: true
          description: >-
            The date and time in GMT when the resource was created specified in
            [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format.
        url:
          type: string
          format: uri
          nullable: true
          description: The absolute URL of the Identity resource.
    trusthub.v1.trust_product.trust_product_evaluation:
      type: object
      properties:
        sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^EL[0-9a-fA-F]{32}$'
          nullable: true
          description: The unique string that identifies the Evaluation resource.
        account_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^AC[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The SID of the
            [Account](https://www.twilio.com/docs/iam/api/account) that created
            the trust_product resource.
        policy_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^RN[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string of a policy that is associated to the
            trust_product resource.
        trust_product_sid:
          type: string
          minLength: 34
          maxLength: 34
          pattern: '^BU[0-9a-fA-F]{32}$'
          nullable: true
          description: >-
            The unique string that we created to identify the trust_product
            resource.
        status:
          type: string
          $ref: '#/components/schemas/trust_product_evaluation_enum_status'
          nullable: true
          description: The compliance status of the Evaluation resource.
        results:
          type: array
          items: {}
          nullable: true
          description: >-
            The results of the Evaluation which includes the valid and invalid
            attributes.
        date_created:
          type: string
          format: date-time
          nullable: true
        url:
          type: string
          format: uri
          nullable: true
    trust_product_evaluation_enum_status:
      type: string
      enum:
        - compliant
        - noncompliant
  securitySchemes:
    accountSid_authToken:
      type: http
      scheme: basic
info:
  title: Twilio Trust Hub API
  description: This is the public Twilio REST API.
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
  /v1/ComplianceInquiries/Customers/Initialize:
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - inquiry_id
        - session_token
        - customer_id
      pathType: list
      mountName: compliance_inquiries
      className: compliance_inquiries
    post:
      description: >-
        Create a new Compliance Inquiry for the authenticated account. This is
        necessary to start a new embedded session.
      tags:
        - Trust Hubs
        - Compliance
        - Inquiries
        - Customers
        - Initialize
      responses:
        '201':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/trusthub.v1.compliance_inquiry'
          description: Created
      security:
        - accountSid_authToken: []
      operationId: CreateComplianceInquiry
      x-maturity:
        - GA
      requestBody:
        content:
          application/x-www-form-urlencoded:
            schema:
              type: object
              title: CreateComplianceInquiryRequest
              properties:
                PrimaryProfileSid:
                  type: string
                  minLength: 34
                  maxLength: 34
                  pattern: '^BU[0-9a-fA-F]{32}$'
                  description: >-
                    The unique SID identifier of the Primary Customer Profile
                    that should be used as a parent. Only necessary when
                    creating a secondary Customer Profile.
              required:
                - PrimaryProfileSid
      summary: Create Compliance Inquiry Customers Initialize
  '/v1/ComplianceInquiries/Customers/{CustomerId}/Initialize':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - inquiry_id
        - session_token
        - customer_id
      pathType: instance
      mountName: compliance_inquiries
      className: compliance_inquiries
    post:
      description: >-
        Resume a specific Compliance Inquiry that has expired, or re-open a
        rejected Compliance Inquiry for editing.
      tags:
        - Trust Hubs
        - Compliance
        - Inquiries
        - Customers
        - Initialize
      parameters:
        - name: CustomerId
          in: path
          description: >-
            The unique CustomerId matching the Customer Profile/Compliance
            Inquiry that should be resumed or resubmitted. This value will have
            been returned by the initial Compliance Inquiry creation call.
          schema:
            type: string
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/trusthub.v1.compliance_inquiry'
          description: OK
      security:
        - accountSid_authToken: []
      operationId: UpdateComplianceInquiry
      x-maturity:
        - GA
      requestBody:
        content:
          application/x-www-form-urlencoded:
            schema:
              type: object
              title: UpdateComplianceInquiryRequest
              properties:
                PrimaryProfileSid:
                  type: string
                  minLength: 34
                  maxLength: 34
                  pattern: '^BU[0-9a-fA-F]{32}$'
                  description: >-
                    The unique SID identifier of the Primary Customer Profile
                    that should be used as a parent. Only necessary when
                    creating a secondary Customer Profile.
              required:
                - PrimaryProfileSid
      summary: Create Compliance Inquiry Customer Initialize
  /v1/ComplianceInquiries/Tollfree/Initialize:
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - inquiry_id
        - session_token
        - registration_id
      pathType: list
      mountName: compliance_tollfree_inquiries
      className: compliance_tollfree_inquiries
    post:
      description: >-
        Create a new Compliance Tollfree Verification Inquiry for the
        authenticated account. This is necessary to start a new embedded
        session.
      tags:
        - Trust Hubs
        - Compliance
        - Inquiries
        - Toll
        - Free
        - Initialize
      responses:
        '201':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/trusthub.v1.compliance_tollfree_inquiry'
          description: Created
      security:
        - accountSid_authToken: []
      operationId: CreateComplianceTollfreeInquiry
      x-maturity:
        - GA
      requestBody:
        content:
          application/x-www-form-urlencoded:
            schema:
              type: object
              title: CreateComplianceTollfreeInquiryRequest
              properties:
                TollfreePhoneNumber:
                  type: string
                  format: phone-number
                  description: The Tollfree phone number to be verified
                NotificationEmail:
                  type: string
                  description: >-
                    The email address to receive the notification about the
                    verification result.
                BusinessName:
                  type: string
                  description: >-
                    The name of the business or organization using the Tollfree
                    number.
                BusinessWebsite:
                  type: string
                  description: >-
                    The website of the business or organization using the
                    Tollfree number.
                UseCaseCategories:
                  type: array
                  items:
                    type: string
                  description: >-
                    The category of the use case for the Tollfree Number. List
                    as many are applicable..
                UseCaseSummary:
                  type: string
                  description: >-
                    Use this to further explain how messaging is used by the
                    business or organization.
                ProductionMessageSample:
                  type: string
                  description: 'An example of message content, i.e. a sample message.'
                OptInImageUrls:
                  type: array
                  items:
                    type: string
                  description: >-
                    Link to an image that shows the opt-in workflow. Multiple
                    images allowed and must be a publicly hosted URL.
                OptInType:
                  type: string
                  $ref: >-
                    #/components/schemas/compliance_tollfree_inquiry_enum_opt_in_type
                  description: Describe how a user opts-in to text messages.
                MessageVolume:
                  type: string
                  description: >-
                    Estimate monthly volume of messages from the Tollfree
                    Number.
                BusinessStreetAddress:
                  type: string
                  description: >-
                    The address of the business or organization using the
                    Tollfree number.
                BusinessStreetAddress2:
                  type: string
                  description: >-
                    The address of the business or organization using the
                    Tollfree number.
                BusinessCity:
                  type: string
                  description: >-
                    The city of the business or organization using the Tollfree
                    number.
                BusinessStateProvinceRegion:
                  type: string
                  description: >-
                    The state/province/region of the business or organization
                    using the Tollfree number.
                BusinessPostalCode:
                  type: string
                  description: >-
                    The postal code of the business or organization using the
                    Tollfree number.
                BusinessCountry:
                  type: string
                  description: >-
                    The country of the business or organization using the
                    Tollfree number.
                AdditionalInformation:
                  type: string
                  description: Additional information to be provided for verification.
                BusinessContactFirstName:
                  type: string
                  description: >-
                    The first name of the contact for the business or
                    organization using the Tollfree number.
                BusinessContactLastName:
                  type: string
                  description: >-
                    The last name of the contact for the business or
                    organization using the Tollfree number.
                BusinessContactEmail:
                  type: string
                  description: >-
                    The email address of the contact for the business or
                    organization using the Tollfree number.
                BusinessContactPhone:
                  type: string
                  format: phone-number
                  description: >-
                    The phone number of the contact for the business or
                    organization using the Tollfree number.
              required:
                - TollfreePhoneNumber
                - NotificationEmail
      summary: Create Compliance Inquiry Toll Free Initialize
  /v1/CustomerProfiles:
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
        - policy_sid
        - friendly_name
      pathType: list
      dependentProperties:
        customer_profiles_entity_assignments:
          mapping:
            customer_profile_sid: sid
          resource_url: '/v1/CustomerProfiles/{customer_profile_sid}/EntityAssignments'
        customer_profiles_evaluations:
          mapping:
            customer_profile_sid: sid
          resource_url: '/v1/CustomerProfiles/{customer_profile_sid}/Evaluations'
        customer_profiles_channel_endpoint_assignment:
          mapping:
            customer_profile_sid: sid
          resource_url: >-
            /v1/CustomerProfiles/{customer_profile_sid}/ChannelEndpointAssignments
      className: customer_profiles
    post:
      description: Create a new Customer-Profile.
      tags:
        - Trust Hubs
        - Customer Profiles
        - Profiles
      responses:
        '201':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/trusthub.v1.customer_profile'
          description: Created
      security:
        - accountSid_authToken: []
      operationId: CreateCustomerProfile
      x-maturity:
        - GA
      requestBody:
        content:
          application/x-www-form-urlencoded:
            schema:
              type: object
              title: CreateCustomerProfileRequest
              properties:
                FriendlyName:
                  type: string
                  description: The string that you assigned to describe the resource.
                Email:
                  type: string
                  description: >-
                    The email address that will receive updates when the
                    Customer-Profile resource changes status.
                PolicySid:
                  type: string
                  minLength: 34
                  maxLength: 34
                  pattern: '^RN[0-9a-fA-F]{32}$'
                  description: >-
                    The unique string of a policy that is associated to the
                    Customer-Profile resource.
                StatusCallback:
                  type: string
                  format: uri
                  description: >-
                    The URL we call to inform your application of status
                    changes.
              required:
                - FriendlyName
                - Email
                - PolicySid
      summary: Create Customer Profile
    get:
      description: Retrieve a list of all Customer-Profiles for an account.
      tags:
        - Trust Hubs
        - Customer Profiles
        - Profiles
      parameters:
        - name: Status
          in: query
          description: The verification status of the Customer-Profile resource.
          schema:
            type: string
            $ref: '#/components/schemas/customer_profile_enum_status'
        - name: FriendlyName
          in: query
          description: The string that you assigned to describe the resource.
          schema:
            type: string
        - name: PolicySid
          in: query
          description: >-
            The unique string of a policy that is associated to the
            Customer-Profile resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^RN[0-9a-fA-F]{32}$'
        - name: PageSize
          in: query
          description: >-
            How many resources to return in each list page. The default is 50,
            and the maximum is 1000.
          schema:
            type: integer
            minimum: 1
            maximum: 1000
        - name: Page
          in: query
          description: The page index. This value is simply for client state.
          schema:
            type: integer
            minimum: 0
        - name: PageToken
          in: query
          description: The page token. This is provided by the API.
          schema:
            type: string
      responses:
        '200':
          content:
            application/json:
              schema:
                type: object
                title: ListCustomerProfileResponse
                properties:
                  results:
                    type: array
                    items:
                      $ref: '#/components/schemas/trusthub.v1.customer_profile'
                  meta:
                    type: object
                    properties:
                      first_page_url:
                        type: string
                        format: uri
                      next_page_url:
                        type: string
                        format: uri
                        nullable: true
                      page:
                        type: integer
                      page_size:
                        type: integer
                      previous_page_url:
                        type: string
                        format: uri
                        nullable: true
                      url:
                        type: string
                        format: uri
                      key:
                        type: string
          description: OK
      security:
        - accountSid_authToken: []
      operationId: ListCustomerProfile
      x-maturity:
        - GA
      summary: Retrieve Customer Profiles
  '/v1/CustomerProfiles/{Sid}':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
        - policy_sid
        - friendly_name
      pathType: instance
      dependentProperties:
        customer_profiles_entity_assignments:
          mapping:
            customer_profile_sid: sid
          resource_url: '/v1/CustomerProfiles/{customer_profile_sid}/EntityAssignments'
        customer_profiles_evaluations:
          mapping:
            customer_profile_sid: sid
          resource_url: '/v1/CustomerProfiles/{customer_profile_sid}/Evaluations'
        customer_profiles_channel_endpoint_assignment:
          mapping:
            customer_profile_sid: sid
          resource_url: >-
            /v1/CustomerProfiles/{customer_profile_sid}/ChannelEndpointAssignments
      className: customer_profiles
    get:
      description: Fetch a specific Customer-Profile instance.
      tags:
        - Trust Hubs
        - Customer Profiles
        - Profiles
      parameters:
        - name: Sid
          in: path
          description: >-
            The unique string that we created to identify the Customer-Profile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/trusthub.v1.customer_profile'
          description: OK
      security:
        - accountSid_authToken: []
      operationId: FetchCustomerProfile
      x-maturity:
        - GA
      summary: Retrieve Customer Profile
    post:
      description: Updates a Customer-Profile in an account.
      tags:
        - Trust Hubs
        - Customer Profiles
        - Profiles
      parameters:
        - name: Sid
          in: path
          description: >-
            The unique string that we created to identify the Customer-Profile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/trusthub.v1.customer_profile'
          description: OK
      security:
        - accountSid_authToken: []
      operationId: UpdateCustomerProfile
      x-maturity:
        - GA
      requestBody:
        content:
          application/x-www-form-urlencoded:
            schema:
              type: object
              title: UpdateCustomerProfileRequest
              properties:
                Status:
                  type: string
                  $ref: '#/components/schemas/customer_profile_enum_status'
                  description: The verification status of the Customer-Profile resource.
                StatusCallback:
                  type: string
                  format: uri
                  description: >-
                    The URL we call to inform your application of status
                    changes.
                FriendlyName:
                  type: string
                  description: The string that you assigned to describe the resource.
                Email:
                  type: string
                  description: >-
                    The email address that will receive updates when the
                    Customer-Profile resource changes status.
      summary: Update Customer Profile
    delete:
      description: Delete a specific Customer-Profile.
      tags:
        - Trust Hubs
        - Customer Profiles
        - Profiles
      parameters:
        - name: Sid
          in: path
          description: >-
            The unique string that we created to identify the Customer-Profile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
      responses:
        '204':
          description: The resource was deleted successfully.
      security:
        - accountSid_authToken: []
      operationId: DeleteCustomerProfile
      x-maturity:
        - GA
      summary: Delete Customer Profile
  '/v1/CustomerProfiles/{CustomerProfileSid}/ChannelEndpointAssignments':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
      pathType: list
      parent: '/CustomerProfiles/{Sid}'
      mountName: customer_profiles_channel_endpoint_assignment
    post:
      description: Create a new Assigned Item.
      tags:
        - Trust Hubs
        - Customer Profiles
        - Profiles
        - Channels
        - Endpoints
        - Assignments
      parameters:
        - name: CustomerProfileSid
          in: path
          description: >-
            The unique string that we created to identify the CustomerProfile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
      responses:
        '201':
          content:
            application/json:
              schema:
                $ref: >-
                  #/components/schemas/trusthub.v1.customer_profile.customer_profile_channel_endpoint_assignment
          description: Created
      security:
        - accountSid_authToken: []
      operationId: CreateCustomerProfileChannelEndpointAssignment
      x-maturity:
        - GA
      requestBody:
        content:
          application/x-www-form-urlencoded:
            schema:
              type: object
              title: CreateCustomerProfileChannelEndpointAssignmentRequest
              properties:
                ChannelEndpointType:
                  type: string
                  description: 'The type of channel endpoint. eg: phone-number'
                ChannelEndpointSid:
                  type: string
                  minLength: 34
                  maxLength: 34
                  pattern: '^[a-zA-Z]{2}[0-9a-fA-F]{32}$'
                  description: The SID of an channel endpoint
              required:
                - ChannelEndpointType
                - ChannelEndpointSid
      summary: Create Customer Profile Channel Endpoint Assignment
    get:
      description: Retrieve a list of all Assigned Items for an account.
      tags:
        - Trust Hubs
        - Customer Profiles
        - Profiles
        - Channels
        - Endpoints
        - Assignments
      parameters:
        - name: CustomerProfileSid
          in: path
          description: >-
            The unique string that we created to identify the CustomerProfile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
        - name: ChannelEndpointSid
          in: query
          description: The SID of an channel endpoint
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^[a-zA-Z]{2}[0-9a-fA-F]{32}$'
        - name: ChannelEndpointSids
          in: query
          description: comma separated list of channel endpoint sids
          schema:
            type: string
        - name: PageSize
          in: query
          description: >-
            How many resources to return in each list page. The default is 50,
            and the maximum is 1000.
          schema:
            type: integer
            minimum: 1
            maximum: 1000
        - name: Page
          in: query
          description: The page index. This value is simply for client state.
          schema:
            type: integer
            minimum: 0
        - name: PageToken
          in: query
          description: The page token. This is provided by the API.
          schema:
            type: string
      responses:
        '200':
          content:
            application/json:
              schema:
                type: object
                title: ListCustomerProfileChannelEndpointAssignmentResponse
                properties:
                  results:
                    type: array
                    items:
                      $ref: >-
                        #/components/schemas/trusthub.v1.customer_profile.customer_profile_channel_endpoint_assignment
                  meta:
                    type: object
                    properties:
                      first_page_url:
                        type: string
                        format: uri
                      next_page_url:
                        type: string
                        format: uri
                        nullable: true
                      page:
                        type: integer
                      page_size:
                        type: integer
                      previous_page_url:
                        type: string
                        format: uri
                        nullable: true
                      url:
                        type: string
                        format: uri
                      key:
                        type: string
          description: OK
      security:
        - accountSid_authToken: []
      operationId: ListCustomerProfileChannelEndpointAssignment
      x-maturity:
        - GA
      summary: Retrieve Customer Profile Channel Endpoint Assignments
  '/v1/CustomerProfiles/{CustomerProfileSid}/ChannelEndpointAssignments/{Sid}':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
      pathType: instance
      parent: '/CustomerProfiles/{Sid}'
      mountName: customer_profiles_channel_endpoint_assignment
    get:
      description: Fetch specific Assigned Item Instance.
      tags:
        - Trust Hubs
        - Customer Profiles
        - Profiles
        - Channels
        - Endpoints
        - Assignments
      parameters:
        - name: CustomerProfileSid
          in: path
          description: >-
            The unique string that we created to identify the CustomerProfile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
        - name: Sid
          in: path
          description: The unique string that we created to identify the resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^RA[0-9a-fA-F]{32}$'
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: >-
                  #/components/schemas/trusthub.v1.customer_profile.customer_profile_channel_endpoint_assignment
          description: OK
      security:
        - accountSid_authToken: []
      operationId: FetchCustomerProfileChannelEndpointAssignment
      x-maturity:
        - GA
      summary: Retrieve Customer Profile Channel Endpoint Assignment
    delete:
      description: Remove an Assignment Item Instance.
      tags:
        - Trust Hubs
        - Customer Profiles
        - Profiles
        - Channels
        - Endpoints
        - Assignments
      parameters:
        - name: CustomerProfileSid
          in: path
          description: >-
            The unique string that we created to identify the CustomerProfile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
        - name: Sid
          in: path
          description: The unique string that we created to identify the resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^RA[0-9a-fA-F]{32}$'
          required: true
      responses:
        '204':
          description: The resource was deleted successfully.
      security:
        - accountSid_authToken: []
      operationId: DeleteCustomerProfileChannelEndpointAssignment
      x-maturity:
        - GA
      summary: Delete Customer Profile Channel Endpoint Assignment
  '/v1/CustomerProfiles/{CustomerProfileSid}/EntityAssignments':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
      pathType: list
      parent: '/CustomerProfiles/{Sid}'
      mountName: customer_profiles_entity_assignments
      className: customer_profiles_entity_assignments
    post:
      description: Create a new Assigned Item.
      tags:
        - Trust Hubs
        - Customer Profiles
        - Profiles
        - Entities
        - Assignments
      parameters:
        - name: CustomerProfileSid
          in: path
          description: >-
            The unique string that we created to identify the CustomerProfile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
      responses:
        '201':
          content:
            application/json:
              schema:
                $ref: >-
                  #/components/schemas/trusthub.v1.customer_profile.customer_profile_entity_assignment
          description: Created
      security:
        - accountSid_authToken: []
      operationId: CreateCustomerProfileEntityAssignment
      x-maturity:
        - GA
      requestBody:
        content:
          application/x-www-form-urlencoded:
            schema:
              type: object
              title: CreateCustomerProfileEntityAssignmentRequest
              properties:
                ObjectSid:
                  type: string
                  minLength: 34
                  maxLength: 34
                  pattern: '^[a-zA-Z]{2}[0-9a-fA-F]{32}$'
                  description: >-
                    The SID of an object bag that holds information of the
                    different items.
              required:
                - ObjectSid
      summary: Create Customer Profile Entity Assignment
    get:
      description: Retrieve a list of all Assigned Items for an account.
      tags:
        - Trust Hubs
        - Customer Profiles
        - Profiles
        - Entities
        - Assignments
      parameters:
        - name: CustomerProfileSid
          in: path
          description: >-
            The unique string that we created to identify the CustomerProfile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
        - name: PageSize
          in: query
          description: >-
            How many resources to return in each list page. The default is 50,
            and the maximum is 1000.
          schema:
            type: integer
            minimum: 1
            maximum: 1000
        - name: Page
          in: query
          description: The page index. This value is simply for client state.
          schema:
            type: integer
            minimum: 0
        - name: PageToken
          in: query
          description: The page token. This is provided by the API.
          schema:
            type: string
      responses:
        '200':
          content:
            application/json:
              schema:
                type: object
                title: ListCustomerProfileEntityAssignmentResponse
                properties:
                  results:
                    type: array
                    items:
                      $ref: >-
                        #/components/schemas/trusthub.v1.customer_profile.customer_profile_entity_assignment
                  meta:
                    type: object
                    properties:
                      first_page_url:
                        type: string
                        format: uri
                      next_page_url:
                        type: string
                        format: uri
                        nullable: true
                      page:
                        type: integer
                      page_size:
                        type: integer
                      previous_page_url:
                        type: string
                        format: uri
                        nullable: true
                      url:
                        type: string
                        format: uri
                      key:
                        type: string
          description: OK
      security:
        - accountSid_authToken: []
      operationId: ListCustomerProfileEntityAssignment
      x-maturity:
        - GA
      summary: Retrieve Customer Profile Entity Assignments
  '/v1/CustomerProfiles/{CustomerProfileSid}/EntityAssignments/{Sid}':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
      pathType: instance
      parent: '/CustomerProfiles/{Sid}'
      mountName: customer_profiles_entity_assignments
      className: customer_profiles_entity_assignments
    get:
      description: Fetch specific Assigned Item Instance.
      tags:
        - Trust Hubs
        - Customer Profiles
        - Profiles
        - Entities
        - Assignments
      parameters:
        - name: CustomerProfileSid
          in: path
          description: >-
            The unique string that we created to identify the CustomerProfile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
        - name: Sid
          in: path
          description: The unique string that we created to identify the Identity resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BV[0-9a-fA-F]{32}$'
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: >-
                  #/components/schemas/trusthub.v1.customer_profile.customer_profile_entity_assignment
          description: OK
      security:
        - accountSid_authToken: []
      operationId: FetchCustomerProfileEntityAssignment
      x-maturity:
        - GA
      summary: Retrieve Customer Profile Entity Assignment
    delete:
      description: Remove an Assignment Item Instance.
      tags:
        - Trust Hubs
        - Customer Profiles
        - Profiles
        - Entities
        - Assignments
      parameters:
        - name: CustomerProfileSid
          in: path
          description: >-
            The unique string that we created to identify the CustomerProfile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
        - name: Sid
          in: path
          description: The unique string that we created to identify the Identity resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BV[0-9a-fA-F]{32}$'
          required: true
      responses:
        '204':
          description: The resource was deleted successfully.
      security:
        - accountSid_authToken: []
      operationId: DeleteCustomerProfileEntityAssignment
      x-maturity:
        - GA
      summary: Delete Customer Profile Entity Assignment
  '/v1/CustomerProfiles/{CustomerProfileSid}/Evaluations':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
      pathType: list
      parent: '/CustomerProfiles/{Sid}'
      mountName: customer_profiles_evaluations
      className: customer_profiles_evaluations
    post:
      description: Create a new Evaluation
      tags:
        - Trust Hubs
        - Customer Profiles
        - Profiles
        - Evaluations
      parameters:
        - name: CustomerProfileSid
          in: path
          description: >-
            The unique string that we created to identify the CustomerProfile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
      responses:
        '201':
          content:
            application/json:
              schema:
                $ref: >-
                  #/components/schemas/trusthub.v1.customer_profile.customer_profile_evaluation
          description: Created
      security:
        - accountSid_authToken: []
      operationId: CreateCustomerProfileEvaluation
      x-maturity:
        - GA
      requestBody:
        content:
          application/x-www-form-urlencoded:
            schema:
              type: object
              title: CreateCustomerProfileEvaluationRequest
              properties:
                PolicySid:
                  type: string
                  minLength: 34
                  maxLength: 34
                  pattern: '^RN[0-9a-fA-F]{32}$'
                  description: >-
                    The unique string of a policy that is associated to the
                    customer_profile resource.
              required:
                - PolicySid
      summary: Create Customer Profile Evaluation
    get:
      description: >-
        Retrieve a list of Evaluations associated to the customer_profile
        resource.
      tags:
        - Trust Hubs
        - Customer Profiles
        - Profiles
        - Evaluations
      parameters:
        - name: CustomerProfileSid
          in: path
          description: >-
            The unique string that we created to identify the CustomerProfile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
        - name: PageSize
          in: query
          description: >-
            How many resources to return in each list page. The default is 50,
            and the maximum is 1000.
          schema:
            type: integer
            minimum: 1
            maximum: 1000
        - name: Page
          in: query
          description: The page index. This value is simply for client state.
          schema:
            type: integer
            minimum: 0
        - name: PageToken
          in: query
          description: The page token. This is provided by the API.
          schema:
            type: string
      responses:
        '200':
          content:
            application/json:
              schema:
                type: object
                title: ListCustomerProfileEvaluationResponse
                properties:
                  results:
                    type: array
                    items:
                      $ref: >-
                        #/components/schemas/trusthub.v1.customer_profile.customer_profile_evaluation
                  meta:
                    type: object
                    properties:
                      first_page_url:
                        type: string
                        format: uri
                      next_page_url:
                        type: string
                        format: uri
                        nullable: true
                      page:
                        type: integer
                      page_size:
                        type: integer
                      previous_page_url:
                        type: string
                        format: uri
                        nullable: true
                      url:
                        type: string
                        format: uri
                      key:
                        type: string
          description: OK
      security:
        - accountSid_authToken: []
      operationId: ListCustomerProfileEvaluation
      x-maturity:
        - GA
      summary: Retrieve Customer Profile Evaluations
  '/v1/CustomerProfiles/{CustomerProfileSid}/Evaluations/{Sid}':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
      pathType: instance
      parent: '/CustomerProfiles/{Sid}'
      mountName: customer_profiles_evaluations
      className: customer_profiles_evaluations
    get:
      description: Fetch specific Evaluation Instance.
      tags:
        - Trust Hubs
        - Customer Profiles
        - Profiles
        - Evaluations
      parameters:
        - name: CustomerProfileSid
          in: path
          description: >-
            The unique string that we created to identify the customer_profile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
        - name: Sid
          in: path
          description: The unique string that identifies the Evaluation resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^EL[0-9a-fA-F]{32}$'
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: >-
                  #/components/schemas/trusthub.v1.customer_profile.customer_profile_evaluation
          description: OK
      security:
        - accountSid_authToken: []
      operationId: FetchCustomerProfileEvaluation
      x-maturity:
        - GA
      summary: Retrieve Customer Profile Evaluation
  /v1/EndUsers:
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
        - friendly_name
      pathType: list
    post:
      description: Create a new End User.
      tags:
        - Trust Hubs
        - Users
      responses:
        '201':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/trusthub.v1.end_user'
          description: Created
      security:
        - accountSid_authToken: []
      operationId: CreateEndUser
      x-maturity:
        - GA
      requestBody:
        content:
          application/x-www-form-urlencoded:
            schema:
              type: object
              title: CreateEndUserRequest
              properties:
                FriendlyName:
                  type: string
                  description: The string that you assigned to describe the resource.
                Type:
                  type: string
                  description: >-
                    The type of end user of the Bundle resource - can be
                    `individual` or `business`.
                Attributes:
                  description: >-
                    The set of parameters that are the attributes of the End
                    User resource which are derived End User Types.
              required:
                - FriendlyName
                - Type
      summary: Create End User
    get:
      description: Retrieve a list of all End User for an account.
      tags:
        - Trust Hubs
        - Users
      parameters:
        - name: PageSize
          in: query
          description: >-
            How many resources to return in each list page. The default is 50,
            and the maximum is 1000.
          schema:
            type: integer
            minimum: 1
            maximum: 1000
        - name: Page
          in: query
          description: The page index. This value is simply for client state.
          schema:
            type: integer
            minimum: 0
        - name: PageToken
          in: query
          description: The page token. This is provided by the API.
          schema:
            type: string
      responses:
        '200':
          content:
            application/json:
              schema:
                type: object
                title: ListEndUserResponse
                properties:
                  results:
                    type: array
                    items:
                      $ref: '#/components/schemas/trusthub.v1.end_user'
                  meta:
                    type: object
                    properties:
                      first_page_url:
                        type: string
                        format: uri
                      next_page_url:
                        type: string
                        format: uri
                        nullable: true
                      page:
                        type: integer
                      page_size:
                        type: integer
                      previous_page_url:
                        type: string
                        format: uri
                        nullable: true
                      url:
                        type: string
                        format: uri
                      key:
                        type: string
          description: OK
      security:
        - accountSid_authToken: []
      operationId: ListEndUser
      x-maturity:
        - GA
      summary: Retrieve End Users
  '/v1/EndUsers/{Sid}':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
        - friendly_name
      pathType: instance
    get:
      description: Fetch specific End User Instance.
      tags:
        - Trust Hubs
        - Users
      parameters:
        - name: Sid
          in: path
          description: >-
            The unique string created by Twilio to identify the End User
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^IT[0-9a-fA-F]{32}$'
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/trusthub.v1.end_user'
          description: OK
      security:
        - accountSid_authToken: []
      operationId: FetchEndUser
      x-maturity:
        - GA
      summary: Retrieve End User
    post:
      description: Update an existing End User.
      tags:
        - Trust Hubs
        - Users
      parameters:
        - name: Sid
          in: path
          description: >-
            The unique string created by Twilio to identify the End User
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^IT[0-9a-fA-F]{32}$'
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/trusthub.v1.end_user'
          description: OK
      security:
        - accountSid_authToken: []
      operationId: UpdateEndUser
      x-maturity:
        - GA
      requestBody:
        content:
          application/x-www-form-urlencoded:
            schema:
              type: object
              title: UpdateEndUserRequest
              properties:
                FriendlyName:
                  type: string
                  description: The string that you assigned to describe the resource.
                Attributes:
                  description: >-
                    The set of parameters that are the attributes of the End
                    User resource which are derived End User Types.
      summary: Update End User
    delete:
      description: Delete a specific End User.
      tags:
        - Trust Hubs
        - Users
      parameters:
        - name: Sid
          in: path
          description: >-
            The unique string created by Twilio to identify the End User
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^IT[0-9a-fA-F]{32}$'
          required: true
      responses:
        '204':
          description: The resource was deleted successfully.
      security:
        - accountSid_authToken: []
      operationId: DeleteEndUser
      x-maturity:
        - GA
      summary: Delete End User
  /v1/EndUserTypes:
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
        - friendly_name
      pathType: list
    get:
      description: Retrieve a list of all End-User Types.
      tags:
        - Trust Hubs
        - Users
        - User Types
        - Types
      parameters:
        - name: PageSize
          in: query
          description: >-
            How many resources to return in each list page. The default is 50,
            and the maximum is 1000.
          schema:
            type: integer
            minimum: 1
            maximum: 1000
        - name: Page
          in: query
          description: The page index. This value is simply for client state.
          schema:
            type: integer
            minimum: 0
        - name: PageToken
          in: query
          description: The page token. This is provided by the API.
          schema:
            type: string
      responses:
        '200':
          content:
            application/json:
              schema:
                type: object
                title: ListEndUserTypeResponse
                properties:
                  end_user_types:
                    type: array
                    items:
                      $ref: '#/components/schemas/trusthub.v1.end_user_type'
                  meta:
                    type: object
                    properties:
                      first_page_url:
                        type: string
                        format: uri
                      next_page_url:
                        type: string
                        format: uri
                        nullable: true
                      page:
                        type: integer
                      page_size:
                        type: integer
                      previous_page_url:
                        type: string
                        format: uri
                        nullable: true
                      url:
                        type: string
                        format: uri
                      key:
                        type: string
          description: OK
      security:
        - accountSid_authToken: []
      operationId: ListEndUserType
      x-maturity:
        - GA
      summary: Retrieve End User Types
  '/v1/EndUserTypes/{Sid}':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
        - friendly_name
      pathType: instance
    get:
      description: Fetch a specific End-User Type Instance.
      tags:
        - Trust Hubs
        - Users
        - User Types
        - Types
      parameters:
        - name: Sid
          in: path
          description: The unique string that identifies the End-User Type resource.
          schema:
            type: string
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/trusthub.v1.end_user_type'
          description: OK
      security:
        - accountSid_authToken: []
      operationId: FetchEndUserType
      x-maturity:
        - GA
      summary: Retrieve End User Type
  /v1/Policies:
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
        - friendly_name
      pathType: list
      className: policies
    get:
      description: Retrieve a list of all Policys.
      tags:
        - Trust Hubs
        - Policies
      parameters:
        - name: PageSize
          in: query
          description: >-
            How many resources to return in each list page. The default is 50,
            and the maximum is 1000.
          schema:
            type: integer
            minimum: 1
            maximum: 1000
        - name: Page
          in: query
          description: The page index. This value is simply for client state.
          schema:
            type: integer
            minimum: 0
        - name: PageToken
          in: query
          description: The page token. This is provided by the API.
          schema:
            type: string
      responses:
        '200':
          content:
            application/json:
              schema:
                type: object
                title: ListPoliciesResponse
                properties:
                  results:
                    type: array
                    items:
                      $ref: '#/components/schemas/trusthub.v1.policies'
                  meta:
                    type: object
                    properties:
                      first_page_url:
                        type: string
                        format: uri
                      next_page_url:
                        type: string
                        format: uri
                        nullable: true
                      page:
                        type: integer
                      page_size:
                        type: integer
                      previous_page_url:
                        type: string
                        format: uri
                        nullable: true
                      url:
                        type: string
                        format: uri
                      key:
                        type: string
          description: OK
      security:
        - accountSid_authToken: []
      operationId: ListPolicies
      x-maturity:
        - GA
      summary: Retrieve Policies
  '/v1/Policies/{Sid}':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
        - friendly_name
      pathType: instance
      className: policies
    get:
      description: Fetch specific Policy Instance.
      tags:
        - Trust Hubs
        - Policies
      parameters:
        - name: Sid
          in: path
          description: The unique string that identifies the Policy resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^RN[0-9a-fA-F]{32}$'
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/trusthub.v1.policies'
          description: OK
      security:
        - accountSid_authToken: []
      operationId: FetchPolicies
      x-maturity:
        - GA
      summary: Retrieve Policy
  /v1/SupportingDocuments:
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
        - friendly_name
      pathType: list
    post:
      description: Create a new Supporting Document.
      tags:
        - Trust Hubs
        - Supporting Documents
        - Documents
      responses:
        '201':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/trusthub.v1.supporting_document'
          description: Created
      security:
        - accountSid_authToken: []
      operationId: CreateSupportingDocument
      x-maturity:
        - GA
      requestBody:
        content:
          application/x-www-form-urlencoded:
            schema:
              type: object
              title: CreateSupportingDocumentRequest
              properties:
                FriendlyName:
                  type: string
                  description: The string that you assigned to describe the resource.
                Type:
                  type: string
                  description: The type of the Supporting Document.
                Attributes:
                  description: >-
                    The set of parameters that are the attributes of the
                    Supporting Documents resource which are derived Supporting
                    Document Types.
              required:
                - FriendlyName
                - Type
      summary: Create Supporting Document
    get:
      description: Retrieve a list of all Supporting Document for an account.
      tags:
        - Trust Hubs
        - Supporting Documents
        - Documents
      parameters:
        - name: PageSize
          in: query
          description: >-
            How many resources to return in each list page. The default is 50,
            and the maximum is 1000.
          schema:
            type: integer
            minimum: 1
            maximum: 1000
        - name: Page
          in: query
          description: The page index. This value is simply for client state.
          schema:
            type: integer
            minimum: 0
        - name: PageToken
          in: query
          description: The page token. This is provided by the API.
          schema:
            type: string
      responses:
        '200':
          content:
            application/json:
              schema:
                type: object
                title: ListSupportingDocumentResponse
                properties:
                  results:
                    type: array
                    items:
                      $ref: '#/components/schemas/trusthub.v1.supporting_document'
                  meta:
                    type: object
                    properties:
                      first_page_url:
                        type: string
                        format: uri
                      next_page_url:
                        type: string
                        format: uri
                        nullable: true
                      page:
                        type: integer
                      page_size:
                        type: integer
                      previous_page_url:
                        type: string
                        format: uri
                        nullable: true
                      url:
                        type: string
                        format: uri
                      key:
                        type: string
          description: OK
      security:
        - accountSid_authToken: []
      operationId: ListSupportingDocument
      x-maturity:
        - GA
      summary: Retrieve Supporting Documents
  '/v1/SupportingDocuments/{Sid}':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
        - friendly_name
      pathType: instance
    get:
      description: Fetch specific Supporting Document Instance.
      tags:
        - Trust Hubs
        - Supporting Documents
        - Documents
      parameters:
        - name: Sid
          in: path
          description: >-
            The unique string created by Twilio to identify the Supporting
            Document resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^RD[0-9a-fA-F]{32}$'
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/trusthub.v1.supporting_document'
          description: OK
      security:
        - accountSid_authToken: []
      operationId: FetchSupportingDocument
      x-maturity:
        - GA
      summary: Retrieve Supporting Document
    post:
      description: Update an existing Supporting Document.
      tags:
        - Trust Hubs
        - Supporting Documents
        - Documents
      parameters:
        - name: Sid
          in: path
          description: >-
            The unique string created by Twilio to identify the Supporting
            Document resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^RD[0-9a-fA-F]{32}$'
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/trusthub.v1.supporting_document'
          description: OK
      security:
        - accountSid_authToken: []
      operationId: UpdateSupportingDocument
      x-maturity:
        - GA
      requestBody:
        content:
          application/x-www-form-urlencoded:
            schema:
              type: object
              title: UpdateSupportingDocumentRequest
              properties:
                FriendlyName:
                  type: string
                  description: The string that you assigned to describe the resource.
                Attributes:
                  description: >-
                    The set of parameters that are the attributes of the
                    Supporting Document resource which are derived Supporting
                    Document Types.
      summary: Update Supporting Document
    delete:
      description: Delete a specific Supporting Document.
      tags:
        - Trust Hubs
        - Supporting Documents
        - Documents
      parameters:
        - name: Sid
          in: path
          description: >-
            The unique string created by Twilio to identify the Supporting
            Document resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^RD[0-9a-fA-F]{32}$'
          required: true
      responses:
        '204':
          description: The resource was deleted successfully.
      security:
        - accountSid_authToken: []
      operationId: DeleteSupportingDocument
      x-maturity:
        - GA
      summary: Delete Supporting Document
  /v1/SupportingDocumentTypes:
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
        - friendly_name
      pathType: list
    get:
      description: Retrieve a list of all Supporting Document Types.
      tags:
        - Trust Hubs
        - Supporting Documents
        - Documents
        - Document Types
        - Types
      parameters:
        - name: PageSize
          in: query
          description: >-
            How many resources to return in each list page. The default is 50,
            and the maximum is 1000.
          schema:
            type: integer
            minimum: 1
            maximum: 1000
        - name: Page
          in: query
          description: The page index. This value is simply for client state.
          schema:
            type: integer
            minimum: 0
        - name: PageToken
          in: query
          description: The page token. This is provided by the API.
          schema:
            type: string
      responses:
        '200':
          content:
            application/json:
              schema:
                type: object
                title: ListSupportingDocumentTypeResponse
                properties:
                  supporting_document_types:
                    type: array
                    items:
                      $ref: >-
                        #/components/schemas/trusthub.v1.supporting_document_type
                  meta:
                    type: object
                    properties:
                      first_page_url:
                        type: string
                        format: uri
                      next_page_url:
                        type: string
                        format: uri
                        nullable: true
                      page:
                        type: integer
                      page_size:
                        type: integer
                      previous_page_url:
                        type: string
                        format: uri
                        nullable: true
                      url:
                        type: string
                        format: uri
                      key:
                        type: string
          description: OK
      security:
        - accountSid_authToken: []
      operationId: ListSupportingDocumentType
      x-maturity:
        - GA
      summary: Retrieve Supporting Document Types
  '/v1/SupportingDocumentTypes/{Sid}':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
        - friendly_name
      pathType: instance
    get:
      description: Fetch a specific Supporting Document Type Instance.
      tags:
        - Trust Hubs
        - Supporting Documents
        - Documents
        - Document Types
        - Types
      parameters:
        - name: Sid
          in: path
          description: >-
            The unique string that identifies the Supporting Document Type
            resource.
          schema:
            type: string
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/trusthub.v1.supporting_document_type'
          description: OK
      security:
        - accountSid_authToken: []
      operationId: FetchSupportingDocumentType
      x-maturity:
        - GA
      summary: Retrieve Supporting Document Type
  /v1/TrustProducts:
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
        - policy_sid
        - friendly_name
      pathType: list
      dependentProperties:
        trust_products_entity_assignments:
          mapping:
            trust_product_sid: sid
          resource_url: '/v1/TrustProducts/{trust_product_sid}/EntityAssignments'
        trust_products_evaluations:
          mapping:
            trust_product_sid: sid
          resource_url: '/v1/TrustProducts/{trust_product_sid}/Evaluations'
        trust_products_channel_endpoint_assignment:
          mapping:
            trust_product_sid: sid
          resource_url: '/v1/TrustProducts/{trust_product_sid}/ChannelEndpointAssignments'
      className: trust_products
    post:
      description: Create a new Customer-Profile.
      tags:
        - Trust Hubs
        - Trust
        - Products
      responses:
        '201':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/trusthub.v1.trust_product'
          description: Created
      security:
        - accountSid_authToken: []
      operationId: CreateTrustProduct
      x-maturity:
        - GA
      requestBody:
        content:
          application/x-www-form-urlencoded:
            schema:
              type: object
              title: CreateTrustProductRequest
              properties:
                FriendlyName:
                  type: string
                  description: The string that you assigned to describe the resource.
                Email:
                  type: string
                  description: >-
                    The email address that will receive updates when the
                    Customer-Profile resource changes status.
                PolicySid:
                  type: string
                  minLength: 34
                  maxLength: 34
                  pattern: '^RN[0-9a-fA-F]{32}$'
                  description: >-
                    The unique string of a policy that is associated to the
                    Customer-Profile resource.
                StatusCallback:
                  type: string
                  format: uri
                  description: >-
                    The URL we call to inform your application of status
                    changes.
              required:
                - FriendlyName
                - Email
                - PolicySid
      summary: Create Trust Product
    get:
      description: Retrieve a list of all Customer-Profiles for an account.
      tags:
        - Trust Hubs
        - Trust
        - Products
      parameters:
        - name: Status
          in: query
          description: The verification status of the Customer-Profile resource.
          schema:
            type: string
            $ref: '#/components/schemas/trust_product_enum_status'
        - name: FriendlyName
          in: query
          description: The string that you assigned to describe the resource.
          schema:
            type: string
        - name: PolicySid
          in: query
          description: >-
            The unique string of a policy that is associated to the
            Customer-Profile resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^RN[0-9a-fA-F]{32}$'
        - name: PageSize
          in: query
          description: >-
            How many resources to return in each list page. The default is 50,
            and the maximum is 1000.
          schema:
            type: integer
            minimum: 1
            maximum: 1000
        - name: Page
          in: query
          description: The page index. This value is simply for client state.
          schema:
            type: integer
            minimum: 0
        - name: PageToken
          in: query
          description: The page token. This is provided by the API.
          schema:
            type: string
      responses:
        '200':
          content:
            application/json:
              schema:
                type: object
                title: ListTrustProductResponse
                properties:
                  results:
                    type: array
                    items:
                      $ref: '#/components/schemas/trusthub.v1.trust_product'
                  meta:
                    type: object
                    properties:
                      first_page_url:
                        type: string
                        format: uri
                      next_page_url:
                        type: string
                        format: uri
                        nullable: true
                      page:
                        type: integer
                      page_size:
                        type: integer
                      previous_page_url:
                        type: string
                        format: uri
                        nullable: true
                      url:
                        type: string
                        format: uri
                      key:
                        type: string
          description: OK
      security:
        - accountSid_authToken: []
      operationId: ListTrustProduct
      x-maturity:
        - GA
      summary: Retrieve Trust Products
  '/v1/TrustProducts/{Sid}':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
        - policy_sid
        - friendly_name
      pathType: instance
      dependentProperties:
        trust_products_entity_assignments:
          mapping:
            trust_product_sid: sid
          resource_url: '/v1/TrustProducts/{trust_product_sid}/EntityAssignments'
        trust_products_evaluations:
          mapping:
            trust_product_sid: sid
          resource_url: '/v1/TrustProducts/{trust_product_sid}/Evaluations'
        trust_products_channel_endpoint_assignment:
          mapping:
            trust_product_sid: sid
          resource_url: '/v1/TrustProducts/{trust_product_sid}/ChannelEndpointAssignments'
      className: trust_products
    get:
      description: Fetch a specific Customer-Profile instance.
      tags:
        - Trust Hubs
        - Trust
        - Products
      parameters:
        - name: Sid
          in: path
          description: >-
            The unique string that we created to identify the Customer-Profile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/trusthub.v1.trust_product'
          description: OK
      security:
        - accountSid_authToken: []
      operationId: FetchTrustProduct
      x-maturity:
        - GA
      summary: Retrieve Trust Product
    post:
      description: Updates a Customer-Profile in an account.
      tags:
        - Trust Hubs
        - Trust
        - Products
      parameters:
        - name: Sid
          in: path
          description: >-
            The unique string that we created to identify the Customer-Profile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/trusthub.v1.trust_product'
          description: OK
      security:
        - accountSid_authToken: []
      operationId: UpdateTrustProduct
      x-maturity:
        - GA
      requestBody:
        content:
          application/x-www-form-urlencoded:
            schema:
              type: object
              title: UpdateTrustProductRequest
              properties:
                Status:
                  type: string
                  $ref: '#/components/schemas/trust_product_enum_status'
                  description: The verification status of the Customer-Profile resource.
                StatusCallback:
                  type: string
                  format: uri
                  description: >-
                    The URL we call to inform your application of status
                    changes.
                FriendlyName:
                  type: string
                  description: The string that you assigned to describe the resource.
                Email:
                  type: string
                  description: >-
                    The email address that will receive updates when the
                    Customer-Profile resource changes status.
      summary: Update Trust Product
    delete:
      description: Delete a specific Customer-Profile.
      tags:
        - Trust Hubs
        - Trust
        - Products
      parameters:
        - name: Sid
          in: path
          description: >-
            The unique string that we created to identify the Customer-Profile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
      responses:
        '204':
          description: The resource was deleted successfully.
      security:
        - accountSid_authToken: []
      operationId: DeleteTrustProduct
      x-maturity:
        - GA
      summary: Delete Trust Product
  '/v1/TrustProducts/{TrustProductSid}/ChannelEndpointAssignments':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
      pathType: list
      parent: '/TrustProducts/{Sid}'
      mountName: trust_products_channel_endpoint_assignment
    post:
      description: Create a new Assigned Item.
      tags:
        - Trust Hubs
        - Trust
        - Products
        - Channels
        - Endpoints
        - Assignments
      parameters:
        - name: TrustProductSid
          in: path
          description: >-
            The unique string that we created to identify the CustomerProfile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
      responses:
        '201':
          content:
            application/json:
              schema:
                $ref: >-
                  #/components/schemas/trusthub.v1.trust_product.trust_product_channel_endpoint_assignment
          description: Created
      security:
        - accountSid_authToken: []
      operationId: CreateTrustProductChannelEndpointAssignment
      x-maturity:
        - GA
      requestBody:
        content:
          application/x-www-form-urlencoded:
            schema:
              type: object
              title: CreateTrustProductChannelEndpointAssignmentRequest
              properties:
                ChannelEndpointType:
                  type: string
                  description: 'The type of channel endpoint. eg: phone-number'
                ChannelEndpointSid:
                  type: string
                  minLength: 34
                  maxLength: 34
                  pattern: '^[a-zA-Z]{2}[0-9a-fA-F]{32}$'
                  description: The SID of an channel endpoint
              required:
                - ChannelEndpointType
                - ChannelEndpointSid
      summary: Create Trust Product Channel Endpoint Assignment
    get:
      description: Retrieve a list of all Assigned Items for an account.
      tags:
        - Trust Hubs
        - Trust
        - Products
        - Channels
        - Endpoints
        - Assignments
      parameters:
        - name: TrustProductSid
          in: path
          description: >-
            The unique string that we created to identify the CustomerProfile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
        - name: ChannelEndpointSid
          in: query
          description: The SID of an channel endpoint
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^[a-zA-Z]{2}[0-9a-fA-F]{32}$'
        - name: ChannelEndpointSids
          in: query
          description: comma separated list of channel endpoint sids
          schema:
            type: string
        - name: PageSize
          in: query
          description: >-
            How many resources to return in each list page. The default is 50,
            and the maximum is 1000.
          schema:
            type: integer
            minimum: 1
            maximum: 1000
        - name: Page
          in: query
          description: The page index. This value is simply for client state.
          schema:
            type: integer
            minimum: 0
        - name: PageToken
          in: query
          description: The page token. This is provided by the API.
          schema:
            type: string
      responses:
        '200':
          content:
            application/json:
              schema:
                type: object
                title: ListTrustProductChannelEndpointAssignmentResponse
                properties:
                  results:
                    type: array
                    items:
                      $ref: >-
                        #/components/schemas/trusthub.v1.trust_product.trust_product_channel_endpoint_assignment
                  meta:
                    type: object
                    properties:
                      first_page_url:
                        type: string
                        format: uri
                      next_page_url:
                        type: string
                        format: uri
                        nullable: true
                      page:
                        type: integer
                      page_size:
                        type: integer
                      previous_page_url:
                        type: string
                        format: uri
                        nullable: true
                      url:
                        type: string
                        format: uri
                      key:
                        type: string
          description: OK
      security:
        - accountSid_authToken: []
      operationId: ListTrustProductChannelEndpointAssignment
      x-maturity:
        - GA
      summary: Retrieve Trust Product Channel Endpoint Assignments
  '/v1/TrustProducts/{TrustProductSid}/ChannelEndpointAssignments/{Sid}':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
      pathType: instance
      parent: '/TrustProducts/{Sid}'
      mountName: trust_products_channel_endpoint_assignment
    get:
      description: Fetch specific Assigned Item Instance.
      tags:
        - Trust Hubs
        - Trust
        - Products
        - Channels
        - Endpoints
        - Assignments
      parameters:
        - name: TrustProductSid
          in: path
          description: >-
            The unique string that we created to identify the CustomerProfile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
        - name: Sid
          in: path
          description: The unique string that we created to identify the resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^RA[0-9a-fA-F]{32}$'
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: >-
                  #/components/schemas/trusthub.v1.trust_product.trust_product_channel_endpoint_assignment
          description: OK
      security:
        - accountSid_authToken: []
      operationId: FetchTrustProductChannelEndpointAssignment
      x-maturity:
        - GA
      summary: Retrieve Trust Product Channel Endpoint Assignment
    delete:
      description: Remove an Assignment Item Instance.
      tags:
        - Trust Hubs
        - Trust
        - Products
        - Channels
        - Endpoints
        - Assignments
      parameters:
        - name: TrustProductSid
          in: path
          description: >-
            The unique string that we created to identify the CustomerProfile
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
        - name: Sid
          in: path
          description: The unique string that we created to identify the resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^RA[0-9a-fA-F]{32}$'
          required: true
      responses:
        '204':
          description: The resource was deleted successfully.
      security:
        - accountSid_authToken: []
      operationId: DeleteTrustProductChannelEndpointAssignment
      x-maturity:
        - GA
      summary: Delete Trust Product Channel Endpoint Assignment
  '/v1/TrustProducts/{TrustProductSid}/EntityAssignments':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
      pathType: list
      parent: '/TrustProducts/{Sid}'
      mountName: trust_products_entity_assignments
      className: trust_products_entity_assignments
    post:
      description: Create a new Assigned Item.
      tags:
        - Trust Hubs
        - Trust
        - Products
        - Entities
        - Assignments
      parameters:
        - name: TrustProductSid
          in: path
          description: >-
            The unique string that we created to identify the TrustProduct
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
      responses:
        '201':
          content:
            application/json:
              schema:
                $ref: >-
                  #/components/schemas/trusthub.v1.trust_product.trust_product_entity_assignment
          description: Created
      security:
        - accountSid_authToken: []
      operationId: CreateTrustProductEntityAssignment
      x-maturity:
        - GA
      requestBody:
        content:
          application/x-www-form-urlencoded:
            schema:
              type: object
              title: CreateTrustProductEntityAssignmentRequest
              properties:
                ObjectSid:
                  type: string
                  minLength: 34
                  maxLength: 34
                  pattern: '^[a-zA-Z]{2}[0-9a-fA-F]{32}$'
                  description: >-
                    The SID of an object bag that holds information of the
                    different items.
              required:
                - ObjectSid
      summary: Create Trust Product Entity Assignment
    get:
      description: Retrieve a list of all Assigned Items for an account.
      tags:
        - Trust Hubs
        - Trust
        - Products
        - Entities
        - Assignments
      parameters:
        - name: TrustProductSid
          in: path
          description: >-
            The unique string that we created to identify the TrustProduct
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
        - name: PageSize
          in: query
          description: >-
            How many resources to return in each list page. The default is 50,
            and the maximum is 1000.
          schema:
            type: integer
            minimum: 1
            maximum: 1000
        - name: Page
          in: query
          description: The page index. This value is simply for client state.
          schema:
            type: integer
            minimum: 0
        - name: PageToken
          in: query
          description: The page token. This is provided by the API.
          schema:
            type: string
      responses:
        '200':
          content:
            application/json:
              schema:
                type: object
                title: ListTrustProductEntityAssignmentResponse
                properties:
                  results:
                    type: array
                    items:
                      $ref: >-
                        #/components/schemas/trusthub.v1.trust_product.trust_product_entity_assignment
                  meta:
                    type: object
                    properties:
                      first_page_url:
                        type: string
                        format: uri
                      next_page_url:
                        type: string
                        format: uri
                        nullable: true
                      page:
                        type: integer
                      page_size:
                        type: integer
                      previous_page_url:
                        type: string
                        format: uri
                        nullable: true
                      url:
                        type: string
                        format: uri
                      key:
                        type: string
          description: OK
      security:
        - accountSid_authToken: []
      operationId: ListTrustProductEntityAssignment
      x-maturity:
        - GA
      summary: Retrieve Trust Product Entity Assignments
  '/v1/TrustProducts/{TrustProductSid}/EntityAssignments/{Sid}':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
      pathType: instance
      parent: '/TrustProducts/{Sid}'
      mountName: trust_products_entity_assignments
      className: trust_products_entity_assignments
    get:
      description: Fetch specific Assigned Item Instance.
      tags:
        - Trust Hubs
        - Trust
        - Products
        - Entities
        - Assignments
      parameters:
        - name: TrustProductSid
          in: path
          description: >-
            The unique string that we created to identify the TrustProduct
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
        - name: Sid
          in: path
          description: The unique string that we created to identify the Identity resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BV[0-9a-fA-F]{32}$'
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: >-
                  #/components/schemas/trusthub.v1.trust_product.trust_product_entity_assignment
          description: OK
      security:
        - accountSid_authToken: []
      operationId: FetchTrustProductEntityAssignment
      x-maturity:
        - GA
      summary: Retrieve Trust Product Entity Assignment
    delete:
      description: Remove an Assignment Item Instance.
      tags:
        - Trust Hubs
        - Trust
        - Products
        - Entities
        - Assignments
      parameters:
        - name: TrustProductSid
          in: path
          description: >-
            The unique string that we created to identify the TrustProduct
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
        - name: Sid
          in: path
          description: The unique string that we created to identify the Identity resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BV[0-9a-fA-F]{32}$'
          required: true
      responses:
        '204':
          description: The resource was deleted successfully.
      security:
        - accountSid_authToken: []
      operationId: DeleteTrustProductEntityAssignment
      x-maturity:
        - GA
      summary: Delete Trust Product Entity Assignment
  '/v1/TrustProducts/{TrustProductSid}/Evaluations':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
      pathType: list
      parent: '/TrustProducts/{Sid}'
      mountName: trust_products_evaluations
      className: trust_products_evaluations
    post:
      description: Create a new Evaluation
      tags:
        - Trust Hubs
        - Trust
        - Products
        - Evaluations
      parameters:
        - name: TrustProductSid
          in: path
          description: >-
            The unique string that we created to identify the trust_product
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
      responses:
        '201':
          content:
            application/json:
              schema:
                $ref: >-
                  #/components/schemas/trusthub.v1.trust_product.trust_product_evaluation
          description: Created
      security:
        - accountSid_authToken: []
      operationId: CreateTrustProductEvaluation
      x-maturity:
        - GA
      requestBody:
        content:
          application/x-www-form-urlencoded:
            schema:
              type: object
              title: CreateTrustProductEvaluationRequest
              properties:
                PolicySid:
                  type: string
                  minLength: 34
                  maxLength: 34
                  pattern: '^RN[0-9a-fA-F]{32}$'
                  description: >-
                    The unique string of a policy that is associated to the
                    customer_profile resource.
              required:
                - PolicySid
      summary: Create Trust Product Evaluation
    get:
      description: Retrieve a list of Evaluations associated to the trust_product resource.
      tags:
        - Trust Hubs
        - Trust
        - Products
        - Evaluations
      parameters:
        - name: TrustProductSid
          in: path
          description: >-
            The unique string that we created to identify the trust_product
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
        - name: PageSize
          in: query
          description: >-
            How many resources to return in each list page. The default is 50,
            and the maximum is 1000.
          schema:
            type: integer
            minimum: 1
            maximum: 1000
        - name: Page
          in: query
          description: The page index. This value is simply for client state.
          schema:
            type: integer
            minimum: 0
        - name: PageToken
          in: query
          description: The page token. This is provided by the API.
          schema:
            type: string
      responses:
        '200':
          content:
            application/json:
              schema:
                type: object
                title: ListTrustProductEvaluationResponse
                properties:
                  results:
                    type: array
                    items:
                      $ref: >-
                        #/components/schemas/trusthub.v1.trust_product.trust_product_evaluation
                  meta:
                    type: object
                    properties:
                      first_page_url:
                        type: string
                        format: uri
                      next_page_url:
                        type: string
                        format: uri
                        nullable: true
                      page:
                        type: integer
                      page_size:
                        type: integer
                      previous_page_url:
                        type: string
                        format: uri
                        nullable: true
                      url:
                        type: string
                        format: uri
                      key:
                        type: string
          description: OK
      security:
        - accountSid_authToken: []
      operationId: ListTrustProductEvaluation
      x-maturity:
        - GA
      summary: Retrieve Trust Product Evaluations
  '/v1/TrustProducts/{TrustProductSid}/Evaluations/{Sid}':
    servers:
      - url: 'https://trusthub.twilio.com'
    description: 'TODO: Resource-level docs'
    x-twilio:
      defaultOutputProperties:
        - sid
      pathType: instance
      parent: '/TrustProducts/{Sid}'
      mountName: trust_products_evaluations
      className: trust_products_evaluations
    get:
      description: Fetch specific Evaluation Instance.
      tags:
        - Trust Hubs
        - Trust
        - Products
        - Evaluations
      parameters:
        - name: TrustProductSid
          in: path
          description: >-
            The unique string that we created to identify the trust_product
            resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^BU[0-9a-fA-F]{32}$'
          required: true
        - name: Sid
          in: path
          description: The unique string that identifies the Evaluation resource.
          schema:
            type: string
            minLength: 34
            maxLength: 34
            pattern: '^EL[0-9a-fA-F]{32}$'
          required: true
      responses:
        '200':
          content:
            application/json:
              schema:
                $ref: >-
                  #/components/schemas/trusthub.v1.trust_product.trust_product_evaluation
          description: OK
      security:
        - accountSid_authToken: []
      operationId: FetchTrustProductEvaluation
      x-maturity:
        - GA
      summary: Retrieve Trust Product Evaluation
servers:
  - url: 'https://trusthub.twilio.com'
tags:
  - name: Tag
  - name: Trust Hubs
    description: Needs a description.
  - name: Compliance
    description: Needs a description.
  - name: Inquiries
    description: Needs a description.
  - name: Customers
    description: Needs a description.
  - name: Initialize
    description: Needs a description.
  - name: Toll
    description: Needs a description.
  - name: Free
    description: Needs a description.
  - name: Customer Profiles
    description: Needs a description.
  - name: Profiles
    description: Needs a description.
  - name: Channels
    description: Needs a description.
  - name: Endpoints
    description: Needs a description.
  - name: Assignments
    description: Needs a description.
  - name: Entities
    description: Needs a description.
  - name: Evaluations
    description: Needs a description.
  - name: Users
    description: Needs a description.
  - name: User Types
    description: Needs a description.
  - name: Types
    description: Needs a description.
  - name: Policies
    description: Needs a description.
  - name: Supporting Documents
    description: Needs a description.
  - name: Documents
    description: Needs a description.
  - name: Document Types
    description: Needs a description.
  - name: Trust
    description: Needs a description.
  - name: Products
    description: Needs a description.
x-maturity:
  - name: GA
    description: This product is Generally Available.
---
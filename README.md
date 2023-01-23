openapi: 3.0.3
info:
  title: My API
  version: 1.0.0
security:
- oauth2:
    - read
    - write
paths:
  /users:
    post:
      summary: Creates a new user
      requestBody:
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/User'
      responses:
        '201':
          description: User created
components:
  schemas:
    User:
      type: object
      required:
        - name
        - email
      properties:
        name:
          type: string
        email:
          type: string

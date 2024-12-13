---
sidebar_label: Auth Clients
---

# Auth Clients

<!-- todo -->
<!-- ## Manage Auth Clients -->

## Credential Exchange

### Overview

The OAuth 2.0 Client Credentials Grant is used to allow an application to authenticate and obtain an access token for accessing resources under its control, rather than on behalf of a user. This grant type is commonly used for machine-to-machine communication, where the application needs to authenticate itself without a user context.

### Request Initial Credentials

1) Client Authentication
    - The client authenticates itself to the Authorization Server using the *client_id* and *client_secret*.
    - The credentials should be kept secure and only accessible to the application.

1) Token Request
    - The client sends a POST request to the token endpoint of the Authorization Server.
    - The request must include the following parameters:
        - `grant_type`: Must be set to **client_credentials**.
        - `client_id`: The client’s unique identifier.
        - `client_secret`: The client’s secret key.
        - `scope` (optional): Specifies the level of access the client is requesting.

      Example Request:
      ```
      curl --location 'https://oauth.tuinly.com/token' \
      --header 'Content-Type: application/x-www-form-urlencoded' \
      --data-urlencode 'grant_type=client_credentials' \
      --data-urlencode 'client_id=CLIENT_ID' \
      --data-urlencode 'client_secret=CLIENT_SECRET'
      ```

1) Token Response
    - If the request is valid and the credentials are authenticated, the Authorization Server responds with a JSON object containing the access token, refresh token and token type.
    - The response also includes an *expires_in* field indicating the access token's lifetime.

      Example Response:
      ```
      {
        "access_token": "ACCESS_TOKEN",
        "refresh_token": "REFRESH_TOKEN",
        "token_type": "Bearer",
        "expires_in": 3600
      }
      ```

1) Resource Access
    - The client includes the access token in the Authorization header of subsequent requests to the Tuinly API.
    - The token is sent using the Bearer authentication scheme.

      Example Request:
      ```
      curl --location 'https://graphql.tuinly.com/graphql' \
      --header 'Content-Type: application/json' \
      --header 'Authorization: Bearer ACCESS_TOKEN' \
      --data '{"query":"query MyQuery(...
      ...
      ```

### Refresh Credentials

1) Token Request
    - The client sends a POST request to the token endpoint of the Authorization Server.
    - The request must include the following parameters:
        - `grant_type`: Must be set to **refresh_token**.
        - `refresh_token`: The refresh token obtained during the initial token request.

      Example Request:
      ```
      curl --location 'https://oauth.tuinly.com/token' \
      --header 'Content-Type: application/x-www-form-urlencoded' \
      --data-urlencode 'grant_type=refresh_token' \
      --data-urlencode 'refresh_token=REFRESH_TOKEN'
      ```

1) Token Response
    - If the request is valid and the credentials are authenticated, the Authorization Server responds with a JSON object containing the refreshed access token and token type.
    - The response also includes an *expires_in* field indicating the access token's lifetime.

      Example Response:
      ```
      {
        "access_token": "ACCESS_TOKEN",
        "token_type": "Bearer",
        "expires_in": 3600
      }
      ```

1) Resource Access
    - From now on, the client includes the bew access token in the Authorization header of subsequent requests to the Tuinly API.
    - The token is sent using the Bearer authentication scheme.

      Example Request:
      ```
      curl --location 'https://graphql.tuinly.com/graphql' \
      --header 'Content-Type: application/json' \
      --header 'Authorization: Bearer ACCESS_TOKEN' \
      --data '{"query":"query MyQuery(...
      ...
      ```

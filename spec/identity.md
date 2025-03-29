# Identity Management

The identity management feature is responsible for handling the retrieval of the server's identity. This action is part of the friendship process and is used to verify the identity of the server requesting a friendship. The identity includes critical information such as the server's domain, public key, and profile, which are essential for establishing trust between servers.

The identity endpoint is protected and requires proper authentication using a JWT token.

## Requirements

#### Retrieve Identity

1. As a server admin, I want to retrieve the identity of the server (e.g., domain, public key, profile) so that I can verify its authenticity during the friendship process.
2. As a server admin, I want to receive the identity object upon successful retrieval so that I can confirm the server's details.
3. As a server admin, I want to be notified of unauthorized access if I attempt to retrieve the identity without proper authentication so that unauthorized actions are prevented.
4. As a system, I want to validate the JWT token provided in the request to ensure the request is authenticated.
5. As a system, I want to handle unexpected errors gracefully and notify the client using the `Error` schema so that issues are clearly communicated.

## Identity Validation

- The domain of the server being called must match with the domain provided in the identity response.
- The friendship token must be used as the authentication of the request, and identity must never be provided when an invalid token is provided.
- The public key is used to read the posts incoming from the server, which are expected to be encrypted using the private key owned by the server that owns the identity being validated.

## Identity Schema

The `Identity` schema defines the structure of the identity object. Below are the fields expected in the identity and their descriptions:

- **token** (required):  
  The token generated at the beginning of the friendship process.  
  Example: `"abc123"`

- **domain** (required):  
  A string representing the domain of the server.  
  Example: `"danodic.dev"`

- **publicKey** (required):  
  An object representing the public key of the server.  
  Example:  
  ```json
  {
    "key": "rsa-public-key",
    "algorithm": "rsa"
  }
  ```

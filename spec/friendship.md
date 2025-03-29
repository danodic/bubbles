# Friendship Management

The friendship management feature is responsible for handling the creation and deletion of friendships between servers. These actions require proper authentication using a JWT token.

The owner of the server is responsible for generating the JWT token and manually sharing it with the party before the other server requests the friendship. This ensures that the request comes from a trusted source.

## Friendship Workflow

The friendship feature enables servers to establish trusted relationships with each other. Below is a detailed explanation of how the friendship process works:

### Workflow Overview

1. **JWT Token Generation**  
   The owner of **Server A** generates a JWT token. This token is used as a means of authentication and must be shared manually with the owner of **Server B**. This ensures that the token is only accessible to trusted parties.

2. **Friendship Request**  
   Once the JWT token is shared, **Server B** initiates a friendship request to **Server A**. The request includes the JWT token, domain, API path, public key, and profile information of **Server B**.  
   Additionally, **Server B** proactively shares its public key as a sign of trust with **Server A**. This allows **Server A** to verify the authenticity of the request and establish a secure communication channel.

3. **Identity Verification**  
   Upon receiving the friendship request, **Server A** verifies the identity of **Server B**. This verification process uses the provided domain, token, and public key to ensure that the request is authentic. For more details on the identity verification process, refer to the [Identity Documentation](#identity).

4. **Friendship Processing**  
   If the identity verification succeeds, **Server A** processes the friendship request internally. This involves storing the friendship details and marking **Server B** as a trusted server.

5. **Reciprocal Friendship Request**  
   After successfully processing the friendship, **Server A** is expected to send a reciprocal friendship request to **Server B**. This request uses the same JWT token that was initially shared with **Server B**. This ensures that the trust is mutual and both servers recognize each other as friends.

### Key Parameters

- **Domain**: The domain of the server requesting the friendship. This is used during identity verification.
- **JWT Token**: The authentication token shared between the servers. It is critical for verifying the authenticity of the request.
- **Public Key**: The public key shared by the requesting server as a sign of trust and for secure communication.

### Notes

- The manual sharing of the JWT token ensures that only trusted parties can initiate a friendship request.
- The proactive sharing of the public key by the requesting server enhances trust and ensures secure communication.
- The reciprocal friendship request ensures that both servers acknowledge and trust each other.
- The identity verification process is a crucial step to prevent unauthorized access and ensure the integrity of the system.

For further details on the identity verification process, refer to the [Identity Documentation](#identity).

## Requirements

#### Request Friendship

1. As a server admin, I want to provide a friendship request (e.g., token, domain, API path, public key, and profile) so that I can establish a friendship with another server.
2. As a server admin, I want to receive confirmation of a successful friendship request so that I know the operation succeeded.
3. As a server admin, I want to be notified of invalid input if I provide improperly formatted friendship details so that I know the request is invalid.
4. As a server admin, I want to ensure that the JWT token used in the request that was manually shared with the requesting party to confirm their trustworthiness is passed as the authentication token of the request.

#### Delete Friendship

The delete friendship feature is an optional step. It is used to explicitly notify the owner of the other server that this server is being excluded from the bubble. The admin of the server can opt to simply ignore posts from a given server instead of sending a delete request.

The semantics of a delete request can vary depending on the server implementation. For example, the receiving server may also choose to remove the friendship from its side upon receiving the request.

1. As a server admin, I want to provide the domain of a specific friendship so that I can delete it from the server.
2. As a server admin, I want to receive confirmation of a successful deletion so that I know the operation succeeded.
3. As a server admin, I want to be notified of invalid input if I provide an improperly formatted domain so that I know the request is invalid.
4. As a server admin, I want to be notified of unauthorized access if I attempt to delete a friendship without proper authentication so that unauthorized actions are prevented.

## Friendship Schema

The `Friendship` schema defines the structure of the friendship object. Below are the fields expected in the friendship and their descriptions:

- **token** (required):  
  A string representing the authentication token for the friendship.  
  Example: `"abc123"`

- **domain** (required):  
  A string representing the domain of the server to establish a friendship with.  
  Example: `"danodic.dev"`

- **apiPath** (required):  
  A string representing the API path of the server to establish a friendship with.  
  Example: `"/api/bubbles/v1/"`

- **publicKey** (required):  
  A string representing the public key of the server to establish a friendship with.  
  Example: `"rsa-public-key"`

- **profile** (required):  
  An object representing the profile of the server to establish a friendship with.  
  Example: `{ "slug": "@server", "name": "Server Name" }`

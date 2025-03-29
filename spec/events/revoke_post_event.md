# Event: `RevokePostEvent`

The `RevokePostEvent` event is used to inform the friend server that a post has been revoked.

## Schema

The schema for the RevokePostEvent contains the following fields:

- **kind**: `revokePost`.
- **data**: An object containing the details of the revoked post. It includes:
  - **postId**: The unique identifier of the post that was revoked (UUID format).

## Example

```json
{
  "kind": "revokePost",
  ...
  "data": {
    "postId": "123e4567-e89b-12d3-a456-426614174000"
  }
}
```

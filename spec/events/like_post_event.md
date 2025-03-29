# Event: `LikePostEvent`

The `LikePostEvent` event is used to inform the friend server that a post has been liked.

## Schema

The schema for the `LikePostEvent` contains the following fields:

- **kind**: `likePost`.
- **data**: An object containing the details of the liked post. It includes:
  - **postId**: The unique identifier of the post that was liked (UUID format).

## Example

```json
{
  "kind": "likePost",
  ...
  "data": {
    "postId": "123e4567-e89b-12d3-a456-426614174000"
  }
}
```

# Event: `PutPostEvent`

The `PutPostEvent` event is used to inform the friend server that a new post has been created.

## Schema

The schema for the `PutPostEvent` contains the following fields:

- **kind**: `putPost`.
- **data**: An object containing the details of the post. It includes:
  - **post**: An object representing the post, which includes:
    - **id**: The unique identifier of the post (UUID format).
    - **contents**: The content of the post.
    - **createDate**: The date and time when the post was created, in ISO 8601 format.

## Example

```json
{
  "kind": "putPost",
  ...
  "data": {
    "post": {
      "id": "123e4567-e89b-12d3-a456-426614174000",
      "contents": "This is a new post.",
      "createDate": "2025-03-29T12:00:00Z"
    }
  }
}
```

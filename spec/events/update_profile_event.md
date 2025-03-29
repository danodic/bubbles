# Event: `UpdateProfileEvent`

The `UpdateProfileEvent` event is used to inform the friend server that a user profile has been updated.

## Schema

The schema for the `UpdateProfileEvent` contains the following fields:

- **kind**: `updateProfile`.
- **data**: An object containing the details of the updated profile. It includes:
  - **profile**: An object representing the updated profile, which includes:
    - **name**: The name of the user.
    - **slug**: The unique identifier for the user (e.g., `@username`).
    - **bio**: A short biography of the user in markdown format.
    - **lastUpdateDate**: The date and time when the profile was last updated, in ISO 8601 format.

## Example

```json
{
  "kind": "updateProfile",
  ...
  "data": {
    "profile": {
      "name": "Jao Janjao.",
      "slug": "@jao",
      "bio": "This is a sample bio.",
      "lastUpdateDate": "2025-03-29T12:00:00Z"
    }
  }
}
```

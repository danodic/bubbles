# Profile Management

The profile management feature is responsible for handling the update of the admin user's profile information. This action is restricted to the admin user and requires proper authentication using a JWT token.

The profile is used to identify the person who owns the server and to provide a unique slug that identifies the user who creates posts. This ensures that posts and other actions within the system are associated with the correct user.

## Requirements

#### Update Profile

1. As the admin, I want to provide updated profile information (e.g., name, slug, bio) so that I can modify my profile details.
2. As the admin, I want to be notified of invalid input if I provide improperly formatted profile details so that I know the request is invalid.
3. As the admin, I want to be notified of unauthorized access if I attempt to update my profile without proper authentication so that unauthorized actions are prevented.

## Profile Schema

The `Profile` schema defines the structure of the profile object. Below are the fields expected in the profile and their descriptions:

- **name** (optional):  
  A string representing the full name of the admin.  
  Example: `"Jao Janjao"`

- **slug** (required):  
  A unique string identifier for the admin's profile. This is typically used as a handle or username and is essential for identifying the user who creates posts.  
  Example: `"@jao"`

- **bio** (optional):  
  A string containing a brief description or biography of the admin. This field supports Markdown formatting.  
  Example: `"Software developer and privacy advocate."`

- **lastUpdateDate** (required):  
  A string in `date-time` format representing the last time the profile was updated.  
  Example: `"2025-03-29T12:34:56Z"`

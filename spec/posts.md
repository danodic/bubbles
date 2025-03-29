# Posts Management

The posts management feature is responsible for handling the creation, retrieval, and deletion of posts on the server. These actions are restricted to the admin user and require proper authentication using a JWT token.

Posts can only be created, retrieved, and deleted by the admin of the system.

## Requirements

#### Add Post

1. As the admin, I want to provide the contents of a new post so that I can create a post on the server.
2. As the admin, I want to receive the created post object upon successful creation so that I can confirm the post was added.
3. As the admin, I want to be notified of invalid input if I provide improperly formatted post details so that I know the request is invalid.
4. As the admin, I want to be notified of unauthorized access if I attempt to create a post without proper authentication so that unauthorized actions are prevented.

#### Retrieve All Posts

1. As the admin, I want to provide pagination parameters (page and items per page) so that I can retrieve a specific subset of posts.
2. As the admin, I want to receive a list of posts for the specified page so that I can view the posts stored on the server.
3. As the admin, I want to be notified of unauthorized access if I attempt to retrieve posts without proper authentication so that unauthorized actions are prevented.

#### Retrieve a Single Post

1. As the admin, I want to provide the ID of a specific post so that I can retrieve its details.
2. As the admin, I want to receive the post object for the specified ID so that I can view its contents.
3. As the admin, I want to be notified if the specified post ID does not exist so that I know the post cannot be retrieved.
4. As the admin, I want to be notified of unauthorized access if I attempt to retrieve a post without proper authentication so that unauthorized actions are prevented.

#### Delete Post

1. As the admin, I want to provide the ID of a specific post so that I can delete it from the server.
2. As the admin, I want to receive confirmation of a successful deletion so that I know the operation succeeded.
3. As the admin, I want to be notified if the specified post ID does not exist so that I know the post cannot be deleted.
4. As the admin, I want to be notified of unauthorized access if I attempt to delete a post without proper authentication so that unauthorized actions are prevented.

## Post Schema

The `Post` schema defines the structure of the post object. Below are the fields expected in the post and their descriptions:

- **id** (required):  
  A unique string identifier for the post in UUID format.  
  Example: `"550e8400-e29b-41d4-a716-446655440000"`

- **contents** (required):  
  A string containing the content of the post.
  Example: `"I don't like vibe coding, neither vibe documenting."`

- **createdDate** (required):  
  A string in `date-time` format representing the date and time the post was created.  
  Example: `"2025-03-29T12:00:00Z"`

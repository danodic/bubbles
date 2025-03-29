# Events Management

The events management feature is responsible for handling the posting of events to the server. Events represent various actions or updates within the system and can be of different kinds, such as creating a post, liking a post, revoking a post, or updating a profile.

Events are used to push data from the server to its friends in a one-way fashion. Information like posts, profile updates, and other actions are sent as events to each friend server. Friend servers must accept and parse these events instead of polling the originating server to fetch data.

The events endpoint is expected to be called by the server originating the events with the event data. For example, when a new post is created, the server that creates the post must invoke the events endpoint of each one of its friends to notify them of the new post.

## Requirements

#### Post Event

1. As a server admin, I want to provide the details of an event (e.g., kind, source, data) so that I can notify the server of an action or update.
2. As a server admin, I want to receive confirmation of a successful event posting so that I know the operation succeeded.
3. As a server admin, I want to be notified of invalid input if I provide improperly formatted event details so that I know the request is invalid.
4. As a server admin, I want to be notified of unauthorized access if I attempt to post an event without proper authentication so that unauthorized actions are prevented.

## Event Schema

The `Event` schema defines the structure of the event object. Below are the fields expected in the event and their descriptions:

- **kind** (required):  
  A string representing the type of event. Events can be of different kinds, such as creating a post, liking a post, revoking a post, or updating a profile.  
  Example: `"newPost"`

- **source** (required):  
  An object representing the source of the event. This includes details such as the domain, token, and timestamp of the event.
  Example:  
  ```json
  {
    "domain": "danodic.dev",
    "token": "abc123",
    "timestamp": "2025-03-29T12:34:56Z"
  }
  ```

## Events

Below is the list of events and their descriptions. Click on each event to view its detailed specification:

- [New Post Event](/spec/events/new-post.md): Triggered when a new post is created.
- [Like Post Event](/spec/events/like-post.md): Triggered when a post is liked.
- [Revoke Post Event](/spec/events/revoke-post.md): Triggered when a post is revoked.
- [Update Profile Event](/spec/events/update-profile.md): Triggered when a user profile is updated.

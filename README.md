# Bubbles

Bubbles is a decentralized, distributed microblogging protocol designed for developers who want complete control over their social media experience. It empowers developers to host their own microblogging server, manage their content, and establish trusted connections with other servers. The protocol is built with privacy, security, and flexibility in mind, making it an excellent learning tool for programming students interested in web development.

## Key Features

- **Decentralized Architecture**: Each server operates independently, giving developers full control over their content and connections.
- **Encrypted Messaging**: Ensures secure communication between servers using public/private key encryption.
- **Identity Validation**: Verifies the authenticity of servers during the friendship process.
- **Event-Driven Updates**: Servers push updates (e.g., new posts, likes, profile changes) to their friends via events.
- **Customizable Clients**: Developers can create their own client and UI, tailored to their preferences and needs.
- **Privacy-First Design**: No central authority or data collection—your server, your rules.

## Why "Bubbles"?

The name "Bubbles" reflects the protocol's elitist nature and its goal of creating isolated, developer-driven social circles. Each server represents a "bubble," a self-contained social space where developers can interact with trusted peers.

## Getting Started

### Prerequisites

To use Bubbles, you need:

1. **Programming Knowledge**: Bubbles is designed for developers. You are expected to build and host your own client.
2. **Server Hosting**: A domain and hosting environment to deploy your server.
3. **Basic Understanding of Web Development**: Familiarity with REST APIs, JSON, and authentication mechanisms.

### Usage

1. **Set Up Your Server**: Follow the [OpenAPI Specification](./openapi.yml) to implement the required endpoints for authentication, posts, profiles, friendships, and events.
2. **Develop Your Client**: Build a custom client to interact with your server. Use the provided schemas and workflows as a guide.
3. **Establish Friendships**: Share your server's JWT token and public key with trusted peers to establish connections.
4. **Post and Interact**: Use your client to create posts, like posts, and manage your profile.

## Documentation

### Protocol Overview

- **[Authentication](./spec/authentication.md)**: Manage admin authentication and password updates.
- **[Posts](./spec/posts.md)**: Create, retrieve, and delete posts.
- **[Profiles](./spec/profile.md)**: Update the admin's profile information.
- **[Friendships](./spec/friendship.md)**: Establish and manage trusted connections between servers.
- **[Identity](./spec/identity.md)**: Retrieve and validate server identity during the friendship process.
- **[Events](./spec/events.md)**: Push updates (e.g., new posts, likes) to friend servers.

### Event Specifications

- **[PutPostEvent](./spec/events/put_post_event.md)**: Notify friends of a new post.
- **[LikePostEvent](./spec/events/like_post_event.md)**: Notify friends of a liked post.
- **[RevokePostEvent](./spec/events/revoke_post_event.md)**: Notify friends of a revoked post.
- **[UpdateProfileEvent](./spec/events/update_profile_event.md)**: Notify friends of a profile update.

### OpenAPI Specification

The [OpenAPI Specification](./openapi.yml) provides a detailed description of the API endpoints, request/response schemas, and authentication mechanisms.

## Contributing

Contributions are welcome! If you'd like to improve the protocol, fix bugs, or add features, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix:
   ```bash
   git checkout -b feature-name
3. Commit your changes and push them to your fork.
4. Submit a pull request with a detailed description of your changes.

## License
This project is licensed under the Apache 2.0 License.

## Acknowledgments
Bubbles is inspired by the need for privacy-first, developer-driven social media platforms. It is designed to be a learning tool for programming students and a playground for developers who value control and customization.

---

Happy coding and bubbling!

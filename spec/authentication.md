# Authentication Management

The authentication management feature is responsible for handling the authentication of the admin user of the server. Since the system is a single-user system, the login functionality is unique to the admin. The login action allows the admin to authenticate by providing their credentials (username and password) and receive a JSON Web Token (JWT) for accessing protected resources.

The password update action enables the admin to update their password securely. 

## Requirements

#### Login

1. As the admin, I want to provide my username and password so that I can authenticate.
2. As the admin, I want to receive a JWT token upon successful authentication so that I can access protected resources.
3. As the admin, I want to be notified of invalid input if I provide improperly formatted credentials so that I know the request is invalid.
4. As the admin, I want to be notified of unauthorized access if I provide incorrect credentials so that unauthorized access is prevented.
5. As a system, I want to validate the provided credentials against the `Login` schema to ensure the username and password are present.
6. As a system, I want to confirm successful authentication by providing a `Token` object.
7. As a system, I want to handle unexpected errors gracefully and notify the client using the `Error` schema so that issues are clearly communicated.


#### Password Update

1. As the admin, I want to provide my current password and a new password so that I can update my login credentials.
2. As the admin, I want to receive confirmation of a successful password update so that I know the operation succeeded.
3. As the admin, I want to be notified of invalid input if I provide improperly formatted password details so that I know the request is invalid.
4. As the admin, I want to be notified of unauthorized access if I provide an incorrect current password so that unauthorized updates are prevented.
5. As the admin, I want to be notified of validation issues if the new password does not meet the required criteria so that I know why the update failed.

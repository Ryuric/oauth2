# oauth2
Project oauth 2 client credentials
This authorization method is a simple way to publish and interact with protected data. It is an open standard for token-based and allows an end user's account information to be used by third-party services, such as Google, Facebook, etc. without exposing the user's password.

There is many ways to get the authorization, such as:
- Authorization code grant
- Implicit grant
- Resource owner credentials grant
- Client credentials grant
- Refresh token grant

The focus of this project is client credentials grant, this method involves machine to machine authentication.
This method usually have the following actors:
- Resource owner(User): An entity capable of granting access to a protected resource. When the resource owner is a person, it is referred to as an end-user.
- Client application: The machine that needs to be authenticate.
- Authorization server: The server issuing access token to the client after successfully authenticating the resource owner and obtaining authorization.
- Resource server: The resource server is the oauth2 term for your api server. The resource server handles authenticated requests after the application has obtained an access token.

In case of client credentials grant type the user has no role to play. As previously stated it is machine to machine communication. This is typically used by clients to acccess resource about themselves rather than to access a user's resource.
                               ____ _____ 
         5. if token is valid |          |
     return requested resource| Resource |
            __ __ __ __ __ __ |  Server  |
           |                  |____ __ __|            
           | 3.request get resource |
           |                        | 4. Verify token recieved
 __ ___ __ ___  2. token ____ ______|___
| Client      | <------ | Authorization |
| Application |         |    Server     |
|__ __ __ ___ | ------> | ____ ____ ___ |
                1. grant type = client credentials
                   client id
                   client secret

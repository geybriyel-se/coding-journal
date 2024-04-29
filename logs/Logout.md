### Implementing Logout in a REST API with JWT

REST APIs are stateless, meaning each request is not aware of the previous request. 
Therefore, unlike other authentication schemes like session-based authentication, there is no direct mechanism that will invalidate the token. 

One of the ways to make sure that the user can no longer use the token once they log out is by creating a database to store the tokens associated with the user. 
There will be a _isLoggedOut_ field that will serve as a flag to determine if the JWT is still valid or not. 

In the project TOC, this is what I implemented. There is a database for the JWT. 
First thing, I made sure that only one token is valid for the user because by default, or with the initial implementation, everytime the user logs in, they will be issued a new token. 
Therefore, when logging in, I had to make sure that the other tokens associated with the user is invalidated by flagging it as logged out before issuing a new token. 

After this is implemented, next is logout. For this, I created a new class called `CustomLogoutHandler` which implements the class `LogoutHandler`. 
The logic is that when the user makes a request to the logout endpoint, their token will also be flagged as logged out. The response was also modified to display a text to the client, confirming that the logout was successful. 

Lastly, for this to take effect, in the configuration class, `SecurityConfig.java`, I instructed Spring that I have a custom logout handler. 
I also cleared the security context to make sure that the authentication details of the user is cleared after they logged out. 

```
    .logout(l -> l.logoutUrl("/logout")
    .addLogoutHandler(logoutHandler)
    .logoutSuccessHandler((request, response, authentication) -> {
    .SecurityContextHolder.clearContext();
})
```
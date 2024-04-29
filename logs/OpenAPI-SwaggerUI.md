### Create/Generate documentation for the API

First is to add the dependency for OpenAPI from this link: https://springdoc.org/

Whitelist the OpenAPI endpoints in the `SecurityConfig.java` file to permit unrestricted access to the OpenAPI documentation endpoints,
making it accessible even without logging in or registering to the API. 

After this, the documentation will be available. 

For further customization, I created a new Java config class called `OpenApiConfig.java`.
It has no contents but rather, it has the annotations to provide custom configurations for Swagger UI. 

First annotation used is `@OpenAPIDefinition` which contains the info, servers, and security details. 
Info accepts the `@Info` annotation which has various parameters such as contact, description, title, and version of the app.
The server details specifies the servers to access the app, such as PROD, DEV, LOCAL - completely depending on the project. 
The url and description of each server can be added. 
For security, it accepts the `@SecurityRequirement` to inform the users what is the security that is implemented. 

Also, more importantly, there is also the `@SecurityScheme` annotation used in the config class. 
This is help the users inject the JWT that they obtained to the succeeding requests that they make.
It is like how we add the JWT as a variable in Postman when testing the API so that we don't have to manually 
put the token every time we make a request to the API.

Below is a sample of the `@SecurityScheme` configuration:
```
@SecurityScheme(
        name = "Bearer Authentication",
        description = "JSON Web Token (JWT)",
        scheme = "Bearer",
        type = SecuritySchemeType.HTTP,
        bearerFormat = "JWT",
        in = SecuritySchemeIn.HEADER
)

```


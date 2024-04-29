### Configure response when request is Unauthorized

#### To fix: The response of the API is blank. 

This is done in `SecurityConfig.java`. What I did is specified an entry point when handling unauthorized exception.
This will intercept the default configuration of Spring Security. 

```
.exceptionHandling()
.authenticationEntryPoint((request, response, e) ->
{
    response.setContentType("application/json;charset=UTF-8");
    response.setStatus(HttpServletResponse.SC_FORBIDDEN);
    response.getWriter().write(
        objectMapper().writeValueAsString(
            objectMapper().createObjectNode()
                .put("timestamp", Instant.now().toString())
                .put("message", "Access denied")
        )
    );
})
```

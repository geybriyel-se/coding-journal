### Creating a Global Exception Handler class 

I learned about creating a global exception handler class which, in my own observation, improved code readability, 
followed the single responsibility principle and eliminated code duplication. 

This class basically contains all the exception handling that should be done when a specific Exception occurs. 
The task has been delegated here instead of having to do it in the controllers. 

To do this, the handler class must be annotated with `@RestControllerAdvice` for REST APIs and `@ControllerAdvice` for MVC.
Then the methods in this class will contain the logic for handling each type of Exception.

```
@ExceptionHandler(Exception.class)
public ApiResponse<Object> handleGenericException(Exception e) {
    return new ApiResponse<>(StatusCode.INTERNAL_SERVER_ERROR, e.getMessage());
}
```

The controller will then be free of try catch blocks. 
### I got to experience why and how serialization problems can occur and because of that, I learned what serialization is about

- So serialization allows the program to convert an object, in my case Java object, to another format that is suitable for transmission
    - for example, when creating api, the response that I am giving is in JSON format. In my program, I have Java objects. Serialization happens when Java objects are converted into JSON objects.
- In Spring Boot, this happens in the background using `Jackson`
    - it needs getter and setter methods of the objects and with that, it is able access the properties of the java object and then serialize it into JSON behind the scenes

What happened in my program is that I got an error saying that Jackson can’t serialize my response dto class. 

I put breakpoints to see where the problem arises because by this time, I had no idea what the error message meant. 
I found out that my object are being mapped properly from one object to another. 
The problem occurs when I am returning the api response. 

There I did my research on what are the specific reasons why such error happens. 
I have read that my program cannot create the response dto even tho it should be able to since spring boot does this for me as a default. 
I asked how Spring Boot does it and there I found out what the issue with my code is. 
Turns out, I forgot to add the `@Data` annotation in my class which is why Jackson couldn’t access the fields of my object, and thus it wasn’t able to serialize my object.


---

####Other info:

`FasterXML` is the organization maintaining and developing the `Jackson` library

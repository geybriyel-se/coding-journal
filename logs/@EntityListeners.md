###`@EntityListeners` from the `jakarta.validation` library.
- I used it for the `createdAt` and `updatedAt` fields of my entity classes
- this works alongside JPA in a way that it monitors if there are new entries that are being added to the table. if there is, then the specified field, which is `createdAt`, will be filled out automatically based on the logic that was written on the method that has the annotation `@BeforePersist`
- for the `updatedAt` field, it works the same way, but the method that it executes is the one annotated with `@BeforeUpdate`

###</> sample code:
```
import jakarta.persistence.PrePersist;
import jakarta.persistence.PreUpdate;
import java.time.Instant;

public class UserEntityListener {

    @PrePersist
    public void beforePersist(User user) {
        user.setCreatedAt(Instant.now());
    }

    @PreUpdate
    public void beforeUpdate(User user) {
        user.setUpdatedAt(Instant.now());
    }
}
```

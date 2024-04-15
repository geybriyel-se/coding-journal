### UTC when storing date-time
- UTC is the standard when it comes to time. It is the basis of all the timezone.
- It is the standard and recommended way to store time.
- Based on this, Java gets your system’s time then it converts it to UTC. Meanwhile, when it comes to retrieving the time from the database, UTC time is retrieved by Java then it automatically converts it to the system’s timezone.
- This can be done by using the `Instant` class from `java.time` API
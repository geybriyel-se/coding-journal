# [discontinued] Days Of Code - Log 

## Day 0: March 31, 2024 - Sunday

**✅ Today's Progress**: Added basic user field validations on ToC using annotations and implemented exception handling

**💡 Thoughts** I struggled when it comes to the validation not taking effect even tho the jar files have been downloaded and there are no compile time errors. It took a lot of time to figure out which dependencies are needed and which are not, and which library should I use: `jakarta.` or  `javax.`. There was even the Hibernate Validator that devs in forums are saying to include. In the end, I was able to just settle with springboot's starter validation and also the `javax`.

Futhermore, I think I am getting a better grip and understanding of exception handling now and it feels good to see my custom exceptions showing up in the JSON response instead of it just empty and with 40x status. I really learned a lot about this.

I also got to appreciate debugging more. It's so helpful when you want to undestand what went wrong. So I am glad I was able to learn it at my first job tho I stayed there for only ~3 months. There's more to learn about it tho.

For my next code, I need to figure out how to make custom annotations and use it as additional validator of the fields in my DTO. My code is still kind of inconsistent and I am expecting it will be better once I get to implement the annotations.

**🌐 Link to work:** [Tails on Camp](https://github.com/geybriyel-se/tails-on-camp-backend)

## Day 1: April 1, 2024 - Monday

**✅ Today's Progress**: Learned how to create custom annotations and better exception handling

**💡 Thoughts:** Creating the annotations is not that difficult. There are 3 annotations that are needed, `@Target`, `@Retention`, `@Constraint`. I used to just copy the code and modify it but now I can create them on my own. I also got to modify the exception handling of my code but there are still improvements that can be made to follow the SOLID principle. I am also learning how to use Generics more in my classes. And I got to clean up and finalize my dependencies. Now I am only using the starter validation from Spring Boot and removed the duplicate dependencies.

Today, what really took my time is figuring out why my custom annotation is not taking effect. The validator class works fine. The logic is okay, based on the unit tests that I created. The validator class is also getting registered as a bean by Spring. Just my custom annotation is not working.
The other built-in annotations are working tho and it's displaying the messages as expected. I really don't understand why it's not validating my field. I am at my wit's end today.

Tomorrow, hopefully I can finally figure it out. I still have a long way to go.

**🌐 Link to work:** [Tails on Camp](https://github.com/geybriyel-se/tails-on-camp-backend)

**🔖 Useful resources:**
- [Spring Boot - JSR 303 - The Right Way To Validate Objects by Bouali Ali](https://youtu.be/oZgP-9S1Otc?si=qIg719jmEP47XluD)
- [Spring Boot Exception Handling Made Easy by Bouali Ali](https://youtu.be/MhZl4YikM20?si=_MgD6oyZ_9jnEQGs)
- [Spring Boot - Creating a Custom Annotation for REST Validation by Java For You](https://youtu.be/oNXjHcAzQeE?si=EithA1AqVWuKjwLR)

## Day 2: April 2, 2024 - Tuesday

**✅ Today's Progress**: Partial RCA for the thrown exception in custom annotation

**💡 Thoughts:** It's driving me nuts. I figured that there's nothing wrong with the dependencies I'm using. It's not a compatibility issue or a missing jar issue because when I tried to use my validator class but not inject my service, and simply return false, it's working; the annotation is taking effect. But as soon as I try to inject the service, it breaks and throws exceptions. I might have to ask for dev help tomorrow if I can't still figure it out. I mean, there's no other way. I'm just a little shy to post questions in forums because,, idk. Just for some reason lol

Anyway, I couldn't do a lot of programming today because I barely got sleep. Just around 2 hours. So I got a headache and I'm sleepy. I gotta fix my sleep cause it affects my productivity. Hopefully tomorrow I am better in terms of health and of course with my project.

Not a lot of progress at all today but it's something. At least I showed up and I figured out something. Heh.

**🌐 Link to work:** [Tails on Camp](https://github.com/geybriyel-se/tails-on-camp-backend)

## Day 3: April 3, 2024 - Wednesday

**✅ Today's Progress**: Took a break from ToC today and worked on GUI for EDI extraction

**💡 Thoughts:** I had to take my attention off from the project because I'm running out of ideas and it's becoming a taxing thing for me to do more than a dopamine hit. I need a break from it.

With the GUI, it's just a hobby project that I'm working on so that I won't be too intimidated with JavaFX anymore. I kind of forgot the lessons already from the MOOC so it's also a refresher and I get to learn more about it, beyond from what was taught in the course. It's simpler (maybe I can only say this for now) compared to doing a frontend with html-css-js so it's good since I really want to focus on the backend more. The priject structure for JavaFX is also different. For now, what I did is just do it based on what I know and learned from the course. It seems like the methods or ways there are now outdated and there's already a better way to create applications with it so I will further refactor it.

**🌐 Link to work:** [EDI Automation App]()

## Day 4: April 4, 2024 - Thursday

**✅ Today's Progress**: Refactored some code in the GUI of the EDI Automation and went back to Codewars

**💡 Thoughts:** Today I had to report to office for work. Then it was Migo's birthday yesterday so I didn't get enough sleep; only two hours. This is why I didn't have much time today to do coding. There's not much progress. I did start with Codewars again. First reason is because it's not as time consuming and I can freely work on it while in the office. I still wasn't able to finish the problem tho but at least I was still able to code for today.

I am expecting this will more likely always be the case during RTO days. But I am aiming to improve on it by still allotting more time to code as I reach home from work.

**🌐 Link to work:** [EDI Automation App]() | [Codewars - Codewars style ranking system](https://www.codewars.com/kata/51fda2d95d6efda45e00004e)

## Day 5: April 5, 2024 - Friday

**✅ Today's Progress**: Continued with the Codewars kata and attended the JUG PH (Java Users Group PH) Meetup online

**💡 Thoughts:** I kind of finished the kata from yesterday. I am not sure what it's expecting me to do with out of the range inputs. I am already throwing Exception as it wants me to (as stated in the test cases) but it's still not passing. I have seen some other users struggling with the same test cases not passing but I am almost certain I am doing an acceptable thing. I guess the model solution is probably not expecting me to throw an exception as part of my code design but it wants it to happen naturally, like break naturally instead of throwing it intentionally.

As for the meetup, the topics were about refactoring to achieve clean code. This is especially relevant to me as of the moment since I am trying to learn how to write cleaner code and remove code smells from the programs I'm writing. The speaker also recommended a book and a hands-on activity so I'll definitely check those out.

There's also a topic about Spring modulith, and microservices. I realized that the project structure that I'm following is tightly coupled if my modules are based on the layers (eg dao, entity, service, etc). This is a monolithic architecture. I learned the reason why it's better if we structure our classes based on their functions (microservices). Like for example, one module is only for processing students. Inside this module are the Student dto, StudentService, etc. Instead of having them in separate modules. This will make our project loosely coupled, which is easier to maintain and scale, to name a few of its advantages.

**🌐 Link to work:** [Codewars - Codewars style ranking system](https://www.codewars.com/kata/51fda2d95d6efda45e00004e)
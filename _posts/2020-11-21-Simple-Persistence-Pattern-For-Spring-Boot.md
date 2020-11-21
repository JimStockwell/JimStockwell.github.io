With Spring Boot, how do you persist a collection of a given class?
Bruno Leite's tutorial,
["Build a Spring Boot Application Using Java Modules"](https://developer.okta.com/blog/2020/07/27/spring-boot-using-java-modules),
shows how easy it is.

Stepping back, what data persistence classes might we want?
1. A class that (as a collection) needs persisting.
2. A class to control the database, and
3. (Ideally) a [Data Access Object](https://en.wikipedia.org/wiki/Data_access_object).

The class to persist is "Bird" in the tutorial.
It has getters and setters as its public face.
It also has a private String field, id, annotated as @Id.

The class to control the database is "BirdRepository" in the tutorial.
It simply extends MongoRepository.
MongoRepository is generic and is made specific by providing
the class to persist ("Bird"), and the type of the id field from "Bird" (that is, "String").

The Data Access Object is "BirdPersistence" in the tutorial.
It is a POJO with two annotations that make it special.
The class overall is annotated with @Component.
The class' constructor is annotated with @Autowired
and takes a BirdRepository object as a parameter.
As a result of the annotations,
the constructor is automatically invoked by the Spring framework
and provided with a "BirdRepository" object.
The DAO provides data manipulation methods
that call down to BirdRepository.

And that's it!  That's all you need for persisting a simple collection in the Spring Boot framework.

Note: One way to easily install and run MongoDB is to use a docker container
as shown in the tutorial.

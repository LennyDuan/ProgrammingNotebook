# Pojo 
Pojo: __Plain Old Java Object__ is a Java object not bound by any restriction other than those forced by the Java Language Specification. 
## Pojo for JSON
In some of cases, Pojo is a Class created for retrieve/map JSON String. Convert a `JSON String` to a `JSON object` and then convert it to a `Java Class` via `Jackson objectMapper`.

##### Example
1. Get a JSON HTTP response:

        String jsonResult = "{\"name\": \"Lenny Duan\", \"age\": \"25\", \"email\": \"lenny.duan@fake.com\" }";
2. We want to retrieve the data `name`, `age` and `email`:
  * If we do not have a `User` Class then we create one:
  * Or we can directly map to an existence `User` Class.
  
  ```
  public class User {
    private String name;
    private String age;
    private String email;
    ...
    ## Normal Getter() & Setter()
  }
  ```
3. Use `Jackson.getObjectMapper()`, a processor for Java, to readValue from a Json String to this Class:
    
  ```
  User responseUser = Jackson.getObjectMapper().readValue(json, User.class);
  ```
  And then, use normal Getter() to get the value from Json. More usage of Jackson Object Mapper please find here [Java doc - Jackson](https://fasterxml.github.io/jackson-databind/javadoc/2.7/com/fasterxml/jackson/databind/ObjectMapper.html)

#### Notice
If you try to convert Json String to a class use `Jackson`, It should be do what you expect if you do not have _constructor()_ for that Class. __But__ if you do have a _constructor_ or you have extra attributions in that Class. Better to use `@JsonCreator` to annotate the _constructor_.

##### Example

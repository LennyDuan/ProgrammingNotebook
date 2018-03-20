# Pojo 
Pojo: Plain Old Java Object is a Java object not bound by any restriction other than those forced by the Java Language Specification. 
## Pojo for JSON
In some of cases, Pojo is a Class created for retrieve/map JSON String. Convert a `JSON String` to a `JSON object` and then convert it to a `Java Class` via `Jackson objectMapper`.

### Example
1. Get a JSON HTTP response:
        String jsonResult = "{\"name\": \"Lenny Duan\", \"age\": \"25\", \"email\": \"lenny.duan@fake.com\" }";
2. We want to retrieve the data `name`, `age` and `email`:
  * If we do not have a `User` Class then we create one:
  
```
public class User {
  private String name;
  private String age;
  private String email;
  
  ...
  ## Normal Getter & Setter
}
```
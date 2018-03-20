# Simple Logging Facade for Java
Log output is always one of the most important thing in a Java project. Try to use log4j, commons logging, java.util.logging and etc before but they all have their own disadvantages. Here I wanna introduce a very _simple-use_, _powerful_, and ___Elegant___ logging tool - __SLF4j__:

### SLF4J 
The Simple Logging Facade for Java (SLF4J) serves as a simple facade or abstraction for various logging frameworks (e.g. java.util.logging, logback, log4j) allowing the end user to plug in the desired logging framework at deployment time - [sfl4j doc](https://www.slf4j.org).

##### Simple Example:
More userful/detail info can be found in the official [Documentation](https://www.slf4j.org/docs.html):

1. Import Logger dependency:

 ```
 import org.slf4j.Logger;
 import org.slf4j.LoggerFactory;
 ```
2. Initial Logger factory with class name:

 ```
 Logger logger = LoggerFactory.getLogger(<Any>.class);
 ```

3. Use `info()`, `error()` or `debug()` to output.
 
 ```
 void anyFunction() {
    logger.info("Hello World");
    logger.debug("Hello World");
    logger.error("Hello World");
 }
 ```
4. Enjoy logger output:

 ```
 Time [anyFunction<Function name>] INFO Any<Class name> - Hello World
 Time [anyFunction<Function name>] DEBUG Any<Class name> - Hello World
Time [anyFunction<Function name>] ERROR Any<Class name> - Hello World
 ```

#### Notice
The best part I like the SLF4J is that it will not evaluate the toString() unless it going to actually print it. As well as the format SLF4J used to insert an variable into a String

##### Example

```
int age = 10;
logger.info("The age of Lenny Duan is {}", age);
```


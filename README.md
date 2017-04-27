## Spek Maven Sample

This is a sample Maven project that uses Maven to run tests (in a CI scenario for instance). You can still run tests individually 
in the IDE using the Spek IntelliJ IDEA plugin

### Setup


### Dependencies

Check the `pom.xml` to understand all the dependencies required. 

### Test Patterns

Spek uses the Maven Surefire plugin to find and run tests. Make sure that if you're not following default conventions for test location and names (often you're not with Spek), 
that you include the correct pattern in the configuration of the plugin the `pom.xml` file

In our case, tests are under src/test/kotlin/ and have the patter *Spec*.kt

```xml
 <plugin>
    <artifactId>maven-surefire-plugin</artifactId>
    <version>2.19</version>

    <dependencies>
        <dependency>
            <groupId>org.junit.platform</groupId>
            <artifactId>junit-platform-surefire-provider</artifactId>
            <version>1.0.0-M4</version>
        </dependency>
        <dependency>
            <groupId>org.junit.jupiter</groupId>
            <artifactId>junit-jupiter-engine</artifactId>
            <version>5.0.0-M4</version>
        </dependency>
    </dependencies>
    <configuration>
        <includes>
            <include>**/*Spec.*</include>
        </includes>
    </configuration>
</plugin>
```

### Running

To run individual tests, you can use the Spek IntelliJ IDEA plugin

You can run tests with Maven using `mvn test`


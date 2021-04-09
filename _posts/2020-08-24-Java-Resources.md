- A collection in the spirit of the Gang of Four's design patterns, but more specialized toward Java.
  - https://java-design-patterns.com
- Maven goal for style checking with the checkstyle plugin: "mvn checkstyle:check"
- To quickly set everything up for maven
  - Go to the directory **above** where you want yor `pom.xml` file and `src` directory.
  - Execute `mvn archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4`
    You will be promted for the following items:
    - groupId uniquely identifies your project across all projects. A group ID should follow Java's package name rules. 
      For example, `org.apache.maven`.
    - artifactId is the name of the jar without version.
      If you created it, then you can choose whatever name you want with lowercase letters and no strange symbols.
      If it's a third party jar, you have to take the name of the jar as it's distributed.
    - version if you distribute it, then you can choose any typical version with numbers and dots (1.0, 1.1, 1.0.1, ...)
      Google "Semantic Versioning".  Use 0 point something while in development with little or no stability.
    - Note that it seems to be artifactId that controls the top level directory name.
- To set up a Spring Boot environment quickly: https://start.spring.io/
- [An article](https://www.baeldung.com/jlink) explaining how to make a minimal JRE with a launch script that will run on serveral platforms. 

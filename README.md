# release-maven-example

Add some config in your file pom.xml 

    <scm>
       <connection>scm:git:{link your respository}</connection>
       <developerConnection>scm:git:{link your respository}</developerConnection>
       <url>{link your wiki page}</url>
       <tag>@{project.version}</tag>
    </scm>

Ex:
  
    <scm>
       <connection>scm:git:https://github.com/thuytiendang206/release-maven-example.git</connection>
       <developerConnection>scm:git:https://github.com/thuytiendang206/release-maven-example.git</developerConnection>
       <url>https://mgm-tp.atlassian.net/wiki/spaces/WFG/overview</url>
       <tag>@{project.version}</tag>
    </scm>
    
    
Add configuration for pom.xml

    <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-release-plugin</artifactId>
        <version>2.5.3</version>
        <configuration>
          <goals>pre-integration-test</goals>
          <preparationGoals>package</preparationGoals>
          <allowTimestampedSnapshots>true</allowTimestampedSnapshots>
          <tagNameFormat>@{project.version}</tagNameFormat>
          <remoteTagging>false</remoteTagging>
        </configuration>
    </plugin>
    

Run command

    mvn release:prepare

This will 
- update your pom.xml release numbers and make a new tag for the release.

Run command
 
    mvn release:perform
 
     
This will:
- Run tests
- Compiles code and package it
- Put the binary package in your local Maven repository.
# release-maven-example
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
    
Run command

    mvn release:prepare

This will 
- update your pom.xml release numbers and make a new tag for the release.
 
     mvn release:perform
     
This will:
- Run tests
- Compiles code and package it
- Put the binary package in your local Maven repository.
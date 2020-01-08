# Maven Notes

Generate project with:
* ```mvn archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.1```
* ```xml
  <project
 	  xmlns="http://maven.apache.org/POM/4.0.0"
  	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  
    <modelVersion>4.0.0</modelVersion>
  
    <groupId>com.ul</groupId>
    <artifactId>testApp</artifactId>
    <version>1.0</version>
    <packaging>jar</packaging>
  
    <name>testApp</name>
    <url>http://maven.apache.org</url>
  
    <properties>
  		<maven.compiler.source>1.7</maven.compiler.source>
  		<maven.compiler.target>1.7</maven.compiler.target>
    </properties>
  
    <dependencies>
      <dependency>
        <groupId>junit</groupId>
        <artifactId>junit</artifactId>
        <version>4.12</version>
        <scope>test</scope>
      </dependency>
    </dependencies>
  
  	<build>
  		<plugins>
  			<plugin>
  				<groupId>org.apache.maven.plugins</groupId>
  				<artifactId>maven-jar-plugin</artifactId>
  				<version>2.4</version>
  				<configuration>
  					<archive>
  						<manifest>
  							<mainClass>
  								!!packageName.classname!!testApp.App
  							</mainClass>
  						</manifest>
  					</archive>
  				</configuration>
  			</plugin>
  		</plugins>
  	</build>
  </project>
	```

To build a project:
* ```mvn clean```
* ```mvn install```
* ```mvn package```
	* This will create a jar file in /target/
		* run the jar file with ```java -jar FILENAME``` or ```java -cp target/my-app-1.0.jar PACKAGENAME.CLASSNAME```

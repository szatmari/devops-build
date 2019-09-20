# DevOps Build

1. Open your GitHub account (Register if needed)
2. Create new repository "maven-test" + README
3. Clone xour repository to your client
```bash
git clone https://your-git-url
```
5. Create GitHub issue and a branch to create a new maven application
6. Pull your repository and initialize a maven demo application
```bash
mvn -B archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DgroupId=hu.bme.mit.devops -DartifactId=maven-app
```
6. Build and package the code
```bash
mvn package
```
7. Try to execute the artefact
```bash
java -jar %%jar file name%%
```
9. Add mainClass name  
```xml
<project>
  ...
  <build>
		<plugins>
			<plugin>
				<groupId>org.apache.maven.plugins</groupId>
				<artifactId>maven-jar-plugin</artifactId>
				<configuration>
					<archive>
						<manifest>
							<mainClass>hu.bme.mit.devops.App</mainClass>
						</manifest>
					</archive>
				</configuration>
			</plugin>
		</plugins>
	</build>
</project>
```
9. Execute again
```bash
java -jar %%jar file name%%
```
10. Commit and push your code, review and close your issue, while merge your code.
```bash
git commit, merge
```
13. Create a new issue and branch to create a Gradle application
```bash
mkdir gradle-app 
cd gradle-app
gradle init --type java-application
./gradlew run
```
14. Commit and push your code, review and close your issue, while merge your code.
16. Create an issue for maven to gradle conversion
17. Convert your maven project into a gradle project and try to execute it
```bash
gradle init --type pom
./gradlew run
```
19. Extend build.gradle
```
apply plugin: 'application'
mainClassName = 'hu.bme.mit.devops.App'
```
19. Create new repository for the demo SpringBoot RESTFul application
19. Clone spring example
```bash
git clone https://github.com/szatmari/devops-build.git
```
20. Set new origin
```bash
git remote -v
git remote add myorigin https://your-springboot-git-url
git remote -v
git pull myorigin master --allow-unrelated-histories
```
21. Commit and push to `myorigin`
21. Run the SpringBoot REST App
```bash
./gradlew bootRun
```
22. Test the application: 
```bash
curl http://localhost:8080/greeting?name=Zoltan
```
24. Add dependency (`src/main/java/hello/Greeting.java`)
```java
import org.joda.time.LocalTime;
...
    public String getContent() {
        LocalTime currentTime = new LocalTime();
        return content +" " + currentTime;
    }
```
24. Test the application again
```bash
curl http://localhost:8080/greeting?name=Zoltan
```

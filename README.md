# maven-devops-practice

A Java project built, tested and packaged by an automated Jenkins CI pipeline. The app is a minimal "Hello World"; the focus is the build and CI workflow around it.

## Pipeline

```
GitHub push -> Jenkins -> Maven build -> JUnit tests -> JAR package
```

| Stage | Command | Purpose |
|-------|---------|---------|
| Build | `mvn clean compile` | Compile the source |
| Test | `mvn test` | Run JUnit 5 tests |
| Package | `mvn package` | Create `my-app-1.0-SNAPSHOT.jar` |

The pipeline is defined as code in the [`Jenkinsfile`](Jenkinsfile).

## Tech stack

- Java 8
- Maven 3.9.16
- JUnit 5
- Jenkins 2.555.3
- Git / GitHub

## Run locally

```bash
mvn clean package
java -cp target/my-app-1.0-SNAPSHOT.jar com.demo.App
```

Expected output: `Hello World!`

## Project structure

```
my-app/
├── Jenkinsfile
├── pom.xml
└── src/
    ├── main/java/com/demo/App.java
    └── test/java/com/demo/AppTest.java
```

## Roadmap

- [ ] Auto-trigger builds on every push
- [ ] Docker image build
- [ ] GitHub Actions workflow

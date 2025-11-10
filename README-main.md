# myproject (Gradle + Spring Boot + CodeQL)

This repo is set up to build a simple Spring Boot app with Gradle (JDK 17) and run GitHub CodeQL.

## Layout
```
src/main/java/com/example/MyApplication.java  # main class (@SpringBootApplication)
build.gradle                                  # Gradle build (toolchain + mainClass)
settings.gradle                               # rootProject.name
.github/workflows/codeql.yml                  # CodeQL with Gradle wrapper bootstrap
```

## Local build
```bash
# if wrapper already exists:
./gradlew clean build -x test

# otherwise generate the wrapper locally (optional; CI will bootstrap if missing):
gradle wrapper --gradle-version 8.7 --distribution-type bin
./gradlew clean build -x test
```

## Important
- Remove or move `pom.xml` out of the repository root to avoid Maven/Gradle conflicts during CodeQL. This project uses **Gradle**.
- CI workflow bootstraps the Gradle wrapper if it's missing; you can commit the wrapper later for faster builds.

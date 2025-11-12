
# Spring Boot + CodeQL (Gradle) Starter

Minimal Spring Boot 3 app built with Gradle, ready for GitHub CodeQL code scanning.

## How to use
1. Create a new GitHub repo and upload these files (or upload the ZIP).
2. Push to the `main` branch. GitHub Actions will run CodeQL automatically.
3. See findings under **Security > Code scanning alerts** in your repo.

## Build locally (optional)
```bash
# Requires Java 17+ and Gradle
gradle bootRun
# or
gradle build -x test
```

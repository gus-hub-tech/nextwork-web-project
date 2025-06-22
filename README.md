# Nextwork Web Project

## Overview

**Nextwork Web Project** is a Java-based web application managed with Maven. The project is packaged as a WAR (Web Application Archive) and is designed to be easily built and deployed using modern CI/CD practices. This repository includes configuration for AWS CodeBuild and supports automated packaging and artifact management.

## Features

- **Java Web Application**: Built using Java (Corretto 8).
- **Maven Managed**: Dependency management and build lifecycle handled by Maven.
- **Unit Testing**: Integrated with JUnit for test coverage.
- **CI/CD Integration**: Includes `buildspec.yml` for AWS CodeBuild automation.
- **Deployment Scripts**: Custom deployment and artifact scripts included.
- **Cloud Ready**: Artifacts are prepared for deployment to cloud environments.

## Architecture Overview

![Architecture Overview](./aws-cicd-image.png)

## Project Structure

```
.
├── appspec.yml               # Deployment specification (used in AWS CodeDeploy)
├── buildspec.yml             # Build instructions for AWS CodeBuild
├── pom.xml                   # Maven project file
├── scripts/                  # Utility and deployment scripts
├── settings.xml              # Maven settings (repository, credentials, etc)
├── src/                      # Main source code directory
└── target/                   # Maven build output (WAR files, etc)
```

## Build & Deployment

### Prerequisites

- Java 8 (Corretto 8)
- Maven
- AWS CLI (for artifact upload/deploy, if using AWS CodeBuild/CodeDeploy)

### Building the Project

You can compile and package the project using Maven:

```bash
mvn -s settings.xml compile
mvn -s settings.xml package
```

The output WAR file will be located in the `target/` directory.

### CI/CD Pipeline

The project comes with a pre-configured `buildspec.yml` for AWS CodeBuild, which handles:

- Environment setup (Java runtime, auth tokens)
- Build and package steps
- Artifact upload and management

### Deployment

Deployment is managed using `appspec.yml` and scripts under the `scripts/` directory, suitable for AWS CodeDeploy or similar services.

## Customization

- **Dependencies**: Add or update Maven dependencies in `pom.xml`.
- **Build Settings**: Modify `buildspec.yml` and `settings.xml` for custom build or deployment needs.
- **Scripts**: Place any custom deployment or utility scripts in the `scripts/` directory.

## Future updates and to-do!

- Ensure python script works to enable sensitive account information redaction.

## License

This project is for educational and demonstration purposes.  
See individual files for additional licensing information if present.

---

*Feel free to expand, adapt, or integrate this template to fit your own applications!*

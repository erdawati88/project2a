# Project 2A – DevOps CI/CD Pipeline

This project implements an automated CI/CD pipeline for a Java Maven application using Jenkins, JUnit, Mockito, JaCoCo, SonarQube and GitHub. The pipeline supports automated testing, code coverage reporting, static code analysis and Quality Gate validation.

## Unit Testing and Code Coverage

- Implemented 26 comprehensive JUnit test cases for `Student.java` and `ClassGroup.java`
- Covered positive, negative, edge and boundary scenarios
- Used Mockito appropriately to demonstrate mocking in unit testing
- Integrated JaCoCo for automated code coverage measurement
- Achieved 100% instruction and branch coverage

## Jenkins CI/CD Pipeline

The pipeline is defined using a `Jenkinsfile` with three stages:

1. **Build & Test** – Builds the project, executes the JUnit tests and generates the JaCoCo coverage report
2. **SonarQube Analysis** – Performs static code analysis and imports the JaCoCo coverage results
3. **Quality Gate** – Evaluates the SonarQube Quality Gate before allowing the pipeline to complete successfully

JUnit test results and the JaCoCo HTML coverage report are also published in Jenkins.

## Automation and Quality Assurance

- Integrated Jenkins with GitHub for source code retrieval
- Enabled Poll SCM to automatically detect repository changes and trigger the Jenkins pipeline
- Integrated Jenkins with SonarQube for automated code quality analysis
- Configured a SonarQube webhook for Quality Gate evaluation
- Configured Jenkins to monitor the merged `master` branch

## Pipeline Failure and Recovery Validation

Controlled failure-and-recovery scenarios were performed to validate the CI/CD pipeline:

- Demonstrated a Jenkins CI test failure using an intentionally incorrect JUnit assertion
- Restored the correct assertion and verified successful pipeline recovery
- Demonstrated Quality Gate enforcement using a temporary stricter coverage threshold
- Restored the default SonarQube Quality Gate and verified successful pipeline recovery

These scenarios demonstrate that the pipeline can detect both unit test failures and code quality policy failures.

## Branch Integration

The completed `feature/pipeline` branch was merged into `master` through a GitHub pull request. The local repository and Jenkins configuration were then synchronized with the merged `master` branch, with Poll SCM configured to monitor subsequent repository changes.

## Technologies Used

- Java 17
- Eclipse IDE
- Maven 3.9.10
- JUnit 5
- Mockito
- JaCoCo
- Jenkins
- SonarQube 10.7
- Git and GitHub

## Project Status

The project implementation is complete, with the CI/CD pipeline configured to automatically validate changes made to the `master` branch.

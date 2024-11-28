# Maven Jenkins CI/CD Pipeline

This project automates the build, test, and delivery process of a Maven-based Java application using Jenkins.

## Overview

The pipeline automates the following steps:
1. **Build**: Builds the application using Maven.
2. **Test**: Runs unit tests and publishes test results.
3. **Deliver**: Executes a custom delivery script for deployment.

## Technologies Used

- **Jenkins**: CI/CD automation.
- **Docker**: Maven container image for building the project.
- **Maven**: Builds and tests the Java application.
- **JUnit**: Test framework for Java unit tests.

## Pipeline Stages

1. **Build**: 
   - Runs `mvn clean package` to build the project and skip tests during the build.
   
2. **Test**:
   - Executes `mvn test` to run unit tests and gather results.
   - The results are published using JUnit format (`target/surefire-reports/*.xml`).

3. **Deliver**:
   - Executes a custom delivery script (`./jenkins/scripts/deliver.sh`) for deployment.

## Setup

### Requirements:
1. **Jenkins**: With the Docker and Maven plugins installed.
2. **Docker**: To run the Maven container (`maven:3-alpine`).
3. **Maven Project**: A Maven-based project with tests and the `deliver.sh` script.

### Configuration:
1. **Jenkins**: Configure a Jenkins pipeline job and add the provided pipeline script.
2. **Docker**: Ensure Docker is installed on the Jenkins agent for building the Maven container.

## Usage

1. **Run Pipeline**: The Jenkins pipeline will automatically build, test, and deliver the project.
2. **Monitor**: View test results in Jenkins and check the logs for the delivery process.

## Troubleshooting

- **Maven Issues**: Ensure the `maven:3-alpine` Docker image is correctly used for the build environment.
- **Test Failures**: Review the test reports in Jenkins for any failing tests.
- **Delivery Script Issues**: Ensure that the `deliver.sh` script is available in the project and has the correct permissions.

 

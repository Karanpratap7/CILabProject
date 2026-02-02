# CI Lab Project - Calculator Application

A simple Java-based calculator application designed to demonstrate Continuous Integration (CI) and Continuous Deployment (CD) practices using Jenkins and Maven.

## Overview

This project implements a basic calculator with arithmetic operations and includes a complete CI/CD pipeline configuration. It serves as a practical example for learning and implementing automated build, test, and deployment workflows.

## Features

- **Basic Arithmetic Operations**:
  - Addition
  - Subtraction
- **Automated Testing**: JUnit test suite with comprehensive test coverage
- **CI/CD Pipeline**: Jenkins pipeline configuration with automated build, test, and deployment stages
- **Maven Build System**: Standardized build and dependency management

## Prerequisites

Before running this project, ensure you have the following installed:

- **Java**: JDK 17 or higher
- **Maven**: Version 3.6 or higher
- **Jenkins**: (Optional) For CI/CD pipeline execution

## Project Structure

```
CILabProject/
├── src/
│   ├── main/
│   │   └── java/
│   │       └── Calculator.java          # Main calculator implementation
│   └── test/
│       └── java/
│           └── CalculatorTest.java      # JUnit test cases
├── scripts/
│   ├── build.sh                         # Build script
│   └── deploy.sh                        # Deployment script
├── Jenkinsfile                          # Jenkins pipeline configuration
├── pom.xml                              # Maven project configuration
└── README.md                            # Project documentation
```

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Karanpratap7/CILabProject.git
   cd CILabProject
   ```

2. **Build the project**:
   ```bash
   mvn clean compile
   ```

## Usage

### Running Tests

Execute the test suite using Maven:

```bash
mvn test
```

Or use the provided build script:

```bash
./scripts/build.sh
```

### Building the JAR

To create an executable JAR file:

```bash
mvn clean package
```

The compiled JAR will be located in the `target/` directory.

## CI/CD Pipeline

This project includes a Jenkins pipeline with three main stages:

1. **Build Stage**: Compiles the source code
   ```bash
   mvn clean compile
   ```

2. **Test Stage**: Runs all unit tests
   ```bash
   mvn test
   ```

3. **Deploy Stage**: Executes deployment (only on `main` branch)
   ```bash
   ./scripts/deploy.sh
   ```

### Setting up Jenkins

1. Create a new Pipeline job in Jenkins
2. Point the repository URL to this project
3. Jenkins will automatically detect the `Jenkinsfile`
4. Configure Maven tool as 'Maven-3' in Jenkins Global Tool Configuration
5. Run the pipeline

## Development

### Adding New Operations

To add new calculator operations:

1. Add the method to `src/main/java/Calculator.java`
2. Create corresponding tests in `src/test/java/CalculatorTest.java`
3. Run tests to verify: `mvn test`

### Running Locally

```bash
# Compile the code
mvn clean compile

# Run tests
mvn test

# Package the application
mvn package
```

## Testing

The project uses JUnit 4.13.2 for testing. Current test coverage includes:

- Addition operations
- Subtraction operations

Test reports are generated in the `target/surefire-reports/` directory after running `mvn test`.

## Technologies Used

- **Java 17**: Programming language
- **Maven**: Build automation and dependency management
- **JUnit 4.13.2**: Testing framework
- **Jenkins**: CI/CD automation server

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-operation`)
3. Commit your changes (`git commit -am 'Add new operation'`)
4. Push to the branch (`git push origin feature/new-operation`)
5. Create a Pull Request

## License

This is an educational project for learning CI/CD practices.

## Author

Karanpratap7

## Acknowledgments

This project was created as part of a CI/CD lab exercise to demonstrate:
- Java application development
- Unit testing with JUnit
- Maven build automation
- Jenkins pipeline configuration
- Automated deployment workflows

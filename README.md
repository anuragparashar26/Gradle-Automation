# Gradle Automation

## Overview
This is a Java project built using Gradle, designed for automation testing with Selenium. It includes a basic application structure with source code in `src/main/java` and Selenium tests in `src/test/java`. The project uses the **Gradle Wrapper** for consistent builds across environments.

## Prerequisites

- **Java Development Kit (JDK):** OpenJDK 21.0.7 *(or Java 17 as an alternative for older Gradle versions)*
- **Gradle:** Version 8.7 *(included via Gradle Wrapper)*
- **Google Chrome:** Stable version (e.g., `126.0.6478.126` or later, as of May 2025)
- **ChromeDriver:** Matching version for your Chrome browser *(managed via WebDriverManager in the project)*
- **Operating System:** Tested on Ubuntu 24.04 *(should work on other Linux distributions, macOS, or Windows with adjustments)*

## Project Structure

```

src/
├── main/java        # Main application source code
└── test/java        # Selenium test source code (e.g., WebpageTest)
build.gradle         # Gradle build configuration
settings.gradle      # Gradle settings file
gradlew              # Gradle Wrapper script (Unix)
gradlew\.bat          # Gradle Wrapper script (Windows)
gradle-wrapper.jar   # Gradle Wrapper JAR file

````

## Getting Started

### Clone the Repository

```bash
git clone https://github.com/anuragparashar26/Gradle-Automation.git
cd Gradle-Automation
````

### Set Up Java

Ensure Java 21 is installed and configured:

```bash
java -version
```

If not installed, install OpenJDK 21 on Ubuntu:

```bash
sudo apt update
sudo apt install openjdk-21-jdk
```

Set `JAVA_HOME`:

```bash
export JAVA_HOME=/usr/lib/jvm/java-21-openjdk-amd64
echo "export JAVA_HOME=/usr/lib/jvm/java-21-openjdk-amd64" >> ~/.bashrc
source ~/.bashrc
```

### Set Up Google Chrome (for Selenium Tests)

Install Google Chrome if not already installed:

```bash
wget -q -O - https://dl.google.com/linux/linux_signing_key.pub | sudo tee /etc/apt/trusted.gpg.d/google-chrome.asc
sudo sh -c 'echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" > /etc/apt/sources.list.d/google-chrome.list'
sudo apt update
sudo apt install google-chrome-stable
```

Verify Chrome installation:

```bash
google-chrome --version
```

## Build the Project

Use the Gradle Wrapper to build the project (compiles code, runs tests, and creates a JAR):

```bash
./gradlew build
```

For Windows:

```cmd
gradlew.bat build
```

## Run the Application *(Optional)*

If your project has a `main` class and the `application` plugin is configured in `build.gradle`, you can run the application:

```bash
./gradlew run
```

Alternatively, run the JAR manually:

```bash
java -jar build/libs/Gradle-Automation.jar
```

> **Note:** The `run` task is not required if your goal is only to build and test (e.g., for CI/CD).

## Run Tests Explicitly

To execute tests separately:

```bash
./gradlew test
```

Test reports are generated at:
`build/reports/tests/test/index.html`

## Troubleshooting

* **Selenium Test Failures:**
  If tests fail with `SessionNotCreatedException`, ensure Chrome and ChromeDriver versions match.
  This project uses **WebDriverManager** to automate ChromeDriver setup.

* **Java Version Issues:**
  If using an older Gradle version, downgrade to Java 17:

```bash
sudo apt install openjdk-17-jdk
export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
```

---

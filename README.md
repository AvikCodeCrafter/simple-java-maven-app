# 🚀 Java CI/CD Pipeline with Jenkins, Maven & AWS EC2

![Java](https://img.shields.io/badge/Java-8%2F17-orange?logo=java)
![Maven](https://img.shields.io/badge/Maven-Build%20Tool-blue?logo=apachemaven)
![Jenkins](https://img.shields.io/badge/Jenkins-CI%2FCD-red?logo=jenkins)
![AWS](https://img.shields.io/badge/AWS-EC2-yellow?logo=amazonaws)
![Build](https://img.shields.io/badge/Build-Passing-brightgreen)
![License](https://img.shields.io/badge/License-MIT-green)

This repository is for the
[Build a Java app with Maven](https://jenkins.io/doc/tutorials/build-a-java-app-with-maven/)
tutorial in the [Jenkins User Documentation](https://jenkins.io/doc/).
------------------------------------------------------------------------

![CI/CD Architecture](image.png)

------------------------------------------------------------------------
## 🧩 Architecture Overview

    Developer → GitHub → Jenkins → Maven Build → JUnit Tests → Package JAR → Deploy to AWS EC2

------------------------------------------------------------------------

## 🛠 Tech Stack

  Category            Technology
  ------------------- --------------------------------
  📦 Source Control   Git + GitHub
  🔁 CI/CD Tool       Jenkins (Declarative Pipeline)
  ☕ Build Tool       Maven
  🧪 Testing          JUnit
  💻 Runtime          Java (Corretto 8 / 17)
  ☁️ Cloud            AWS EC2 (Amazon Linux 2023)
  📦 Artifact         Executable JAR

------------------------------------------------------------------------

# 🔄 End-to-End CI/CD Workflow

## 1️⃣ Code Push

-   Developer pushes code to GitHub
-   GitHub Webhook triggers Jenkins

## 2️⃣ Jenkins Pipeline Execution

-   Jenkins checks out source code
-   Runs on Jenkins agent

## 3️⃣ Build Stage

``` bash
mvn clean package
```

-   Compiles Java source
-   Runs JUnit tests
-   Generates JAR artifact

## 4️⃣ Archive Artifact

``` groovy
archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
```

## 5️⃣ Deploy Stage

-   Copies JAR to AWS EC2
-   Runs:

``` bash
java -jar my-app-1.0-SNAPSHOT.jar
```

------------------------------------------------------------------------

# 📊 Visual Pipeline Diagram

``` mermaid
flowchart LR
    A[👨‍💻 Developer] -->|Push Code| B[🐙 GitHub]
    B -->|Webhook Trigger| C[🧑‍🍳 Jenkins]
    C --> D[📥 Checkout Code]
    D --> E[☕ Maven Build]
    E --> F[🧪 Run Tests]
    F --> G[📦 Package JAR]
    G --> H[☁️ Deploy to AWS EC2]
    H --> I[🌍 Application Running]
```

------------------------------------------------------------------------

# 📂 Project Structure

    simple-java-maven-app/
    │
    ├── src/main/java/
    │   └── App.java
    │
    ├── src/test/java/
    │   └── AppTest.java
    │
    ├── pom.xml
    └── Jenkinsfile

------------------------------------------------------------------------

# 🏆 What This Demonstrates

✅ Continuous Integration\
✅ Automated Testing\
✅ Artifact Management\
✅ Cloud Deployment\
✅ Real-world DevOps Workflow

------------------------------------------------------------------------

# 👨‍💻 Author

**Avik Banerjee**\
Cloud & DevOps Engineer\
AWS Certified \| Jenkins \| Docker \| CI/CD

------------------------------------------------------------------------

⭐ Built as part of hands-on CI/CD practice using Jenkins Declarative
Pipeline and Maven.

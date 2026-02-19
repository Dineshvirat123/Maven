
# 1️ Introduction

In real-time projects, a developer does not just write code.
There is a full flow like this:

```
Developer → GitHub → Maven → Tomcat → Application Running
```

Let’s understand this clearly and simply.

---

# 2️ Developer → GitHub → Maven → Tomcat Flow

###  Step 1: Developer

* Writes Java code in local system.
* Tests it.
* Pushes code to GitHub repository.

###  Step 2: GitHub

* Stores the source code.
* Maintains version control.
* Team members can pull the code.

###  Step 3: Maven (Build Tool)

* Downloads dependencies.
* Compiles Java code.
* Runs tests.
* Packages the project into:

  * `.jar`
  * `.war`
  * `.ear`

###  Step 4: Tomcat

* WAR file is deployed into **Apache Tomcat**
* Tomcat runs the web application.
* Application becomes accessible in browser.

---

# 3️ What is Build?

Build is an automated process of:

* Compiling source code
* Downloading dependencies
* Running tests
* Packaging the application

Output files:

* JAR
* WAR
* EAR

---

# 4️ What is Maven?

* Maven is a build automation tool.
* Mainly used for Java projects.
* Developed by the **Apache Software Foundation**
* Open-source tool.
* Platform independent.
* Comes as `.zip` or `.tar.gz` (not .exe)

Download link:
[https://maven.apache.org/download.cgi](https://maven.apache.org/download.cgi)

---

# 5️ Why Do We Need Maven?

Without Maven:

* Manually download JAR files.
* Manually compile.
* Difficult dependency management.
* Hard to maintain large projects.

With Maven:

* Automatic dependency management.
* Standard project structure.
* Easy build process.
* Easy team collaboration.

---

# 6️ Types of Build Tools

## Java

* Ant
* Maven
* Gradle

## Python

* PyBuilder

## .NET

* MS Build
* NAnt

## Ruby

* Rake

## Go

* go build tool

---

# 7️ What is JAR, WAR, EAR?

## 1️ JAR (Java Archive)

Used for standalone applications.

Contains:

* Compiled `.class` files
* Java libraries

Example:

* Simple Java application

---

## 2️ WAR (Web Archive)

Used for web applications.

Contains:

* Java code
* HTML
* CSS
* JavaScript
* Images
* JAR files

Deployed into:

* Tomcat server

---

## 3️ EAR (Enterprise Archive)

Used for enterprise-level applications.

Contains:

* JAR files
* WAR files
* Web modules
* Enterprise modules

Used in large enterprise applications.

---

# 8️ Maven Directory Structure

After extracting Maven:

```
apache-maven-3.x.x/
│
├── bin     → mvn command
├── boot    → runtime jar files
├── conf    → configuration files (settings.xml)
├── lib     → library jar files
```

---

# 9️ Default Build File Names

| Tool   | File Name    |
| ------ | ------------ |
| Maven  | pom.xml      |
| Ant    | build.xml    |
| Gradle | build.gradle |

---

#  Maven Installation (Linux – EC2)

---

## System Requirements

* JDK 8 or above (Maven 3.9+)
* 10MB disk space
* Any OS (Linux/Windows)

---

## Step 0: Launch EC2 Instance

Connect to instance.

---

## Step 1: Switch to Root

```bash
sudo su -
```

---

## Step 2: Install Java

```bash
yum update -y
```

Check Java:

```bash
java -version
javac -version
```

Search Java packages:

```bash
sudo yum search java | grep -i openjdk
```

Install Java 21:

```bash
yum install java-21-openjdk-devel -y
```

---

## Step 3: Install Maven

### 1️ Go to /opt directory

```bash
cd /opt
```

Install required tools:

```bash
yum install wget unzip tree git -y
```

---

### 2️ Download Maven

Example:

```bash
wget https://dlcdn.apache.org/maven/maven-3/3.9.12/binaries/apache-maven-3.9.12-bin.zip
```

Unzip:

```bash
unzip apache-maven-3.9.12-bin.zip
```

---

### 3️ Set Environment Variables

Edit profile:

```bash
vi ~/.bash_profile
```

Add:

```bash
export M2_HOME=/opt/apache-maven-3.9.12
export PATH=$PATH:$M2_HOME/bin
```

Load file:

```bash
source ~/.bash_profile
```

Verify:

```bash
mvn -version
```

---

# 1️1️ Important Notes

* All external software usually stored in `/opt`
* Java is mandatory before Maven
* `pom.xml` is heart of Maven project
* Maven uses repository:

  * Local repository (`~/.m2`)
  * Central repository (online)

---

# 1️2️ Real-Time Example Flow

1. Developer writes code.
2. Pushes to GitHub.
3. CI tool runs:

   ```
   mvn clean package
   ```
4. WAR file generated.
5. WAR deployed to Tomcat.
6. Application runs in browser.

---

# 1️3️ Common Maven Commands

```bash
mvn clean
mvn compile
mvn test
mvn package
mvn install
mvn deploy
```

---

# 1️4️ Simple Summary

* Build = automation process.
* Maven = Java build tool.
* JAR = standalone app.
* WAR = web app.
* EAR = enterprise app.
* Java required before Maven.
* `pom.xml` controls everything.


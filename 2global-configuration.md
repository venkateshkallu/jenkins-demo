# Phase 3: Global Configuration

## Objective

Configure Jenkins global settings, tools, and system parameters required for CI/CD operations.

---

# Task 1: Configure System Message

## Navigation

```text
Manage Jenkins
→ System
```

## Configuration

Locate **System Message** and enter:

```text
Welcome to Jenkins CI/CD Server
```

## Verification

Verify the message appears on the Jenkins dashboard.

## Screenshot
![System Message](../jenkins/screenshot/Global%20Configuration/Screenshot%20from%202026-06-22%2011-06-05.png)

---

# Task 2: Configure Executors

## Navigation

```text
Manage Jenkins
→ Nodes
→ Built-In Node
```

or

```text
Manage Jenkins
→ System
```

## Configuration

Locate:

```text
# of executors
```

Set value:

```text
2
```
![system message](../jenkins/screenshot/Global%20Configuration/2-Screenshot%20from%202026-06-22%2011-08-30.png)

## Verification

Understand executor usage:

```text
1 Executor = 1 Build at a Time
2 Executors = 2 Parallel Builds
```

## Screenshot

```text
executors-config.png
```

---

# Task 3: Configure Git Tool

## Verify Git Installation

```bash
git --version
which git
```

Expected Output:

```text
git version 2.43.0
/usr/bin/git
```

## Navigation

```text
Manage Jenkins
→ Tools
```
---

# Task 4: Configure JDK

## Verify Java Installation

```bash
java -version
javac -version
which java
```

## Find JAVA_HOME

```bash
readlink -f $(which java)
```

Example:

```text
/usr/lib/jvm/java-21-openjdk-amd64
```

## Navigation

```text
Manage Jenkins
→ Tools
```

## Configuration

Under **JDK Installations**:

```text
Name: JDK21
JAVA_HOME: /usr/lib/jvm/java-21-openjdk-amd64
```

Click Save.

## Verification

Confirm Jenkins recognizes the installed JDK.



---

# Task 5: Configure Maven

## Verify Maven Installation

```bash
mvn -version
```

If Maven is not installed:

```bash
sudo apt update
sudo apt install maven -y
```

Verify:

```bash
mvn -version
which mvn
```

Expected Output:

```text
Apache Maven 3.x
/usr/bin/mvn
```

## Navigation

```text
Manage Jenkins
→ Tools
```

## Configuration

Under **Maven Installations**:

```text
Name: Maven
```

Save the configuration.

## Verification

Confirm Jenkins can access Maven.

## Screenshot
## Screenshot

![system message](../jenkins/screenshot/Global%20Configuration/3-Screenshot%20from%202026-06-22%2011-11-49.png)

---



# Deliverables

## Completed Configurations

* System Message
* Executors Configuration
* Git Tool Configuration
* JDK Configuration
* Maven Configuration
* Email Notification Configuration (Optional)

## Screenshots

```text
system-message.png
executors-config.png
maven-config.png

```

## Learning Outcomes

* Understood Jenkins Global Configuration
* Configured Build Executors
* Configured Java Development Kit (JDK)
* Configured Maven Build Tool


```
```

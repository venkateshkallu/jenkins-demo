# Phase 10: Jenkins Maven Build and GitHub Integration

## Create Maven Web Application

Navigate to the working directory:

```bash
mkdir -p ~/jenkins-projects
cd ~/jenkins-projects
```

Create Maven Web Application:

```bash
mvn archetype:generate \
-DgroupId=com.demo \
-DartifactId=webapp \
-DarchetypeArtifactId=maven-archetype-webapp \
-DinteractiveMode=false
```

Navigate to project:

```bash
cd webapp
```

Verify project structure:

```bash
ls
```

Expected:

```text
pom.xml
src/
```

---

## Fix Maven WAR Plugin Compatibility Issue

Build project:

```bash
mvn clean package
```

Observed error:

```text
BUILD FAILURE
maven-war-plugin:2.2
Cannot access defaults field of Properties
```

Cause:

```text
Java 21 is incompatible with the old Maven WAR Plugin version 2.2
```

Open POM file:

```bash
nano pom.xml
```

Update build section:

```xml
<build>
    <finalName>webapp</finalName>

    <plugins>

        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-war-plugin</artifactId>
            <version>3.4.0</version>
        </plugin>

    </plugins>

</build>
```

Save file.

---

## Build Maven Application

Execute build:

```bash
mvn clean package
```

Build completed successfully:

```text
BUILD SUCCESS
```

Verify WAR file:

```bash
ls target
```

Expected:

```text
maven-archiver
webapp
webapp.war
```

---

## Initialize Git Repository

Initialize Git:

```bash
git init
```

Add project files:

```bash
git add .
```

Create first commit:

```bash
git commit -m "Initial Maven Web Application"
```

---

## Create GitHub Repository

Repository Name:

```text
tomcat-deploy-demo
```

Add remote repository:

```bash
git remote add origin https://github.com/venkateshkallu/tomcat-deploy-demo.git
```

Set main branch:

```bash
git branch -M main
```

Push source code:

```bash
git push -u origin main
```

Verify repository upload on GitHub.

---

## Remove Build Artifacts from Repository

Check tracked files:

```bash
git ls-files | grep target
```

Observed:

```text
target/maven-archiver/pom.properties
target/webapp.war
target/webapp/WEB-INF/web.xml
target/webapp/index.jsp
```

Create .gitignore:

```bash
echo "target/" >> .gitignore
```

Remove target directory from Git tracking:

```bash
git rm -r --cached target
```

Add .gitignore:

```bash
git add .gitignore
```

Commit changes:

```bash
git commit -m "Add gitignore"
```

Push updates:

```bash
git push
```

Verify target folder is no longer tracked:

```bash
git ls-files | grep target
```

Expected:

```text
No Output
```

---

## Configure Maven in Jenkins

Navigate:

```text
Manage Jenkins
→ Tools
→ Maven Installations
```

Add Maven installation:

```text
Name: Maven
Install Automatically: Enabled
Version: Latest Stable Version
```

Save configuration.

---

## Create Jenkins Build Job

Navigate:

```text
Dashboard
→ New Item
```

Enter:

```text
tomcat-deploy-dem
```

Select:

```text
Freestyle Project
```

Click:

```text
OK
```

---

## Configure GitHub Repository

Navigate:

```text
Source Code Management
→ Git
```

Repository URL:

```text
https://github.com/venkateshkallu/tomcat-deploy-demo.git
```

Branch:

```text
*/main
```

Save configuration.

---

## Configure Maven Build

Navigate:

```text
Build
→ Add Build Step
→ Invoke Top-Level Maven Targets
```

Goals:

```text
clean package
```

Maven Version:

```text
Maven
```

Save configuration.

---

## Execute Jenkins Build

Click:

```text
Build Now
```

Verify Console Output:

```text
Git Clone Successful
Maven Build Started
Packaging webapp
Building webapp.war
BUILD SUCCESS
```

---

## Verify Jenkins Workspace

Navigate:

```text
Job
→ Workspace
```

Open:

```text
target
```

Verify:

```text
webapp.war
```

Generated WAR File:

```text
target/webapp.war
```

---

## Phase 10 Completed

Successfully completed:

* Maven Web Application Creation
* Maven WAR Plugin Upgrade
* Maven Build Execution
* WAR Artifact Generation
* Git Repository Initialization
* GitHub Repository Creation
* GitHub Push Operations
* Git Ignore Configuration
* Jenkins Maven Configuration
* Jenkins GitHub Integration
* Jenkins Build Automation
* Jenkins Workspace Verification
* WAR Artifact Verification

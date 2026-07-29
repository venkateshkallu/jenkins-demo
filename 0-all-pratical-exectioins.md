# Jenkins Complete Practical Guide

## Objective

Perform all Jenkins practical exercises from installation to CI/CD pipelines, document each activity, capture screenshots, and maintain evidence for evaluation and learning.

---

# Phase 1: Prerequisites

## 1. Install Java (JDK)

### Verify Java

```bash
java -version
javac -version
```

### Configure Environment Variables (if required)

```text
JAVA_HOME
JRE_HOME
PATH
```

### Verification

```bash
java -version
javac -version
```

### Screenshots

* Java Version
* Environment Variables

---

# Phase 2: Jenkins Installation

## 2. Install Jenkins

### Linux

```bash
sudo apt update
sudo apt install jenkins -y
```

### Verify Service

```bash
sudo systemctl status jenkins
```

### Enable Service

```bash
sudo systemctl enable jenkins
```

### Access Jenkins

```text
http://localhost:8080
```

### Unlock Jenkins

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

### Install Suggested Plugins

```text
Install Suggested Plugins
```

### Create Admin User

Configure:

```text
Username
Password
Email
```

### Screenshots

* Jenkins Dashboard
* Plugin Installation
* Admin User Creation

---

# Phase 3: Global Configuration

## 3. Configure Jenkins System

Navigate:

```text
Manage Jenkins
→ System
```

Configure:

### System Message

```text
Welcome to Jenkins CI/CD Server
```

### Number of Executors

```text
2
```

### Email Notifications

Configure SMTP:

```text
SMTP Host
SMTP Port
Authentication
Test Email
```

### Global Tool Configuration

Configure:

```text
Git
JDK
Maven
```

### Screenshots

* System Configuration
* Email Configuration
* Global Tool Configuration

---

# Phase 4: Freestyle Job

## 4. Create First Job

Navigate:

```text
New Item
→ Freestyle Project
```

Name:

```text
demo-job
```

### Build Step

```text
Execute Shell
```

Commands:

```bash
echo "Hello Jenkins"
hostname
date
```

### Build

```text
Build Now
```

### Verify

```text
Build History
Console Output
```

### Screenshots

* Job Creation
* Build Success
* Console Output

---

# Phase 5: Build Automation

## 5. Periodic Build Trigger

Navigate:

```text
Build Triggers
```

Enable:

```text
Build Periodically
```

Schedule:

```text
* * * * *
```

### Verify

Wait 1 minute and confirm automatic build execution.

### Screenshots

* Trigger Configuration
* Automated Build History

---

# Phase 6: Security & RBAC

## 6. Role-Based Access Control

### Install Plugin

```text
Role-Based Authorization Strategy
```

### Enable Strategy

Navigate:

```text
Manage Jenkins
→ Security
→ Authorization
```

Select:

```text
Role-Based Strategy
```

### Create Role

Navigate:

```text
Manage and Assign Roles
→ Manage Roles
```

Create:

```text
developer
```

Permissions:

```text
Overall Read
Job Read
Job Build
Job Discover
```

### Create User

Navigate:

```text
Manage Users
```

Create:

```text
dev1
```

### Assign Role

Navigate:

```text
Assign Roles
```

Assign:

```text
dev1 → developer
```

### Verification

Login using developer account.

### Screenshots

* Role Creation
* User Creation
* Role Assignment
* Developer Login

---

# Phase 7: GitHub Integration

## 7. Configure Git

Verify:

```bash
git --version
which git
```

Configure:

```text
Manage Jenkins
→ Tools
→ Git
```

Path:

```text
/usr/bin/git
```

### Create GitHub Repository

Example:

```text
jenkins-demo
```

Files:

```text
README.md
hello.sh
```

Example Script:

```bash
#!/bin/bash
echo "Hello Jenkins"
date
hostname
```

Push repository to GitHub.

### Jenkins Integration

Navigate:

```text
Source Code Management
→ Git
```

Provide:

```text
Repository URL
Credentials
```

### Build Step

```bash
chmod +x hello.sh
./hello.sh
```

### Build

```text
Build Now
```

### Verify

```text
Console Output
```

### Screenshots

* GitHub Repository
* Jenkins SCM Configuration
* Build Success

---

# Phase 8: Maven Setup

## 8. Install Maven

Verify:

```bash
mvn -version
```

Install:

```bash
sudo apt install maven -y
```

Verify:

```bash
mvn -version
```

### Configure Maven in Jenkins

Navigate:

```text
Manage Jenkins
→ Global Tool Configuration
```

Add Maven installation.

### Screenshots

* Maven Installation
* Maven Configuration

---

# Phase 9: Tomcat Setup

## 9. Install Tomcat

Download and extract Tomcat.

### Change Port

Edit:

```text
conf/server.xml
```

Change:

```text
8080 → 8081
```

### Configure Deployment User

Edit:

```text
conf/tomcat-users.xml
```

Add:

```xml
<role rolename="manager-script"/>
<role rolename="manager-gui"/>

<user
username="deployer"
password="Password123"
roles="manager-script,manager-gui"/>
```

### Start Tomcat

```bash
startup.sh
```

### Verify

```text
http://localhost:8081
```

### Screenshots

* Tomcat Running
* Tomcat Manager Login

---

# Phase 10: Maven Build & Deployment

## 10. Deploy Web Application

### Install Plugin

```text
Deploy to Container
```

### Create Maven Job

Source:

```text
Git Repository
```

### Build Step

```text
Invoke Top-Level Maven Targets
```

Goal:

```text
clean package
```

### Post Build Action

```text
Deploy WAR/EAR to Container
```

Configuration:

```text
WAR Path: **/*.war
Container: Tomcat 9.x
URL: http://localhost:8081
Credentials: deployer
```

### Execute Build

```text
Build Now
```

### Verify

```text
Application Deployed
```

### Screenshots

* Maven Build
* WAR Deployment
* Application Access

---

# Phase 11: Jenkins Agents

## 11. Distributed Builds

### Enable Agent Port

Navigate:

```text
Manage Jenkins
→ Security
```

Enable:

```text
TCP Port for Inbound Agents
```

### Create Node

```text
Manage Nodes
→ New Node
```

Name:

```text
agent1
```

Configure:

```text
Remote Directory
Executors
Labels
```

### Connect Agent

Download:

```text
agent.jar
```

Run:

```bash
java -jar agent.jar ...
```

### Verify

```text
Node Status = Online
```

### Run Job on Agent

Enable:

```text
Restrict where project can run
```

Select:

```text
agent1
```

### Screenshots

* Agent Configuration
* Agent Online
* Job Running on Agent

---

# Phase 12: Backup & Recovery

## 12. Backup Jenkins

Install:

```text
Backup Plugin
```

Configure:

```text
Backup Directory
ZIP Format
```

Run:

```text
Backup Jenkins Configuration
```

### Verify Backup

Check generated archive.

### Screenshots

* Backup Configuration
* Backup Archive

---

# Phase 13: Job Chaining

## 13. Upstream & Downstream Jobs

Create:

```text
job1
job2
```

Configure:

```text
Post Build Actions
→ Build Other Projects
```

Trigger:

```text
job2
```

### Verify

Build:

```text
job1
```

Confirm:

```text
job2
```

runs automatically.

### Screenshots

* Job Chaining
* Build Flow

---

# Phase 14: Jenkins Pipelines

## 14. Pipeline as Code

Create:

```text
New Item
→ Pipeline
```

Example:

```groovy
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Build Stage'
            }
        }

        stage('Test') {
            steps {
                echo 'Test Stage'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy Stage'
            }
        }
    }
}
```

### Execute

```text
Build Now
```

### Verify

```text
Stage View
```

### Screenshots

* Pipeline Code
* Pipeline Execution

---

# Phase 15: Jenkinsfile from GitHub

## 15. Pipeline from SCM

Create:

```text
Jenkinsfile
```

Push to GitHub.

Configure:

```text
Pipeline Script from SCM
```

Select:

```text
Git
```

Provide:

```text
Repository URL
```

### Execute

```text
Build Now
```

### Screenshots

* Jenkinsfile
* SCM Configuration
* Successful Build

---

# Phase 16: Parallel Pipeline Execution

## 16. Parallel Stages

Create parallel execution pipeline.

Example:

```groovy
parallel {
    stage('Linux') {
        steps {
            echo 'Linux Tests'
        }
    }

    stage('Windows') {
        steps {
            echo 'Windows Tests'
        }
    }
}
```

### Verify

Observe simultaneous execution.

### Screenshots

* Parallel Pipeline
* Stage View

---

# Phase 17: Maintenance

## Restart Jenkins

Safe Restart:

```text
http://localhost:8080/safeRestart
```

Immediate Restart:

```text
http://localhost:8080/restart
```

---

# Final Deliverables

* Jenkins Installation
* Global Configuration
* Freestyle Jobs
* Build Triggers
* RBAC
* GitHub Integration
* Maven Setup
* Tomcat Deployment
* Jenkins Agents
* Backup & Recovery
* Job Chaining
* Jenkins Pipelines
* Jenkinsfile from SCM
* Parallel Pipelines
* Screenshots
* GitHub Documentation Repository

# Phase 7: GitHub Integration

## Configure Git

### Verify Git Installation

```bash
git --version
which git
```

### Configure Git in Jenkins

Navigate to:

```text
Manage Jenkins
→ Tools
→ Git Installations
```

Configure:

```text
Name: Git
Path: /usr/bin/git
```

---

## Create GitHub Repository

Repository Name:

```text
jenkins-demo
```

Create Files:

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

Push Repository to GitHub.

---

## Create Jenkins Freestyle Project

Navigate to:

```text
New Item
→ Freestyle Project
```

Project Name:

```text
github-demo
```

---

## Configure Source Code Management

Navigate to:

```text
Source Code Management
→ Git
```

Provide:

```text
Repository URL
GitHub Credentials (if private repository)
```

---

## Configure Build Step

Navigate to:

```text
Build
→ Execute Shell
```

Add:

```bash
chmod +x hello.sh
./hello.sh
```

---

## Execute Build

Click:

```text
Build Now
```

---

## Verify Build Execution

Navigate to:

```text
Build History
→ Build Number
→ Console Output
```

Expected Output:

```text
Hello Jenkins
Current Date
Hostname
Finished: SUCCESS
```

---

## Screenshots

* GitHub Repository
* Jenkins SCM Configuration
* Build Configuration
* Build History
* Console Output
* Successful Build Status

---

## Outcome

* Git Installed and Configured
* GitHub Repository Connected
* Source Code Pulled from GitHub
* Build Executed Successfully
* Console Output Verified

# Phase 8: Maven Setup

## Install Maven

Verify Maven installation:

```bash
mvn -version
```

Install Maven:

```bash
sudo apt update
sudo apt install maven -y
```

Verify installation:

```bash
mvn -version
```

---

## Configure Maven in Jenkins

Navigate to:

```text
Manage Jenkins
→ Tools
→ Maven Installations
```

Add Maven configuration:

```text
Name: Maven

```

Save configuration.

---

## Verify Maven Configuration

Create a test Freestyle Job.

Navigate to:

```text
New Item
→ Freestyle Project
```

Add Build Step:

```text
Invoke Top-Level Maven Targets
```

Goals:

```text
--versioin
```

Save and execute the build.

Verify successful Maven execution from Console Output.

![system messaga](../jenkins/screenshot/7MavenSetup/1-Screenshot%20from%202026-06-22%2012-45-19.png)

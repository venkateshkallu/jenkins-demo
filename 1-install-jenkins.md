If you're using **Ubuntu/Linux**, these are the standard Jenkins installation steps you should learn.

# Jenkins Installation on Ubuntu

### Step 1: Update Packages

```bash
sudo apt update
```

---

### Step 2: Install Java (Jenkins Requirement)

Check Java:

```bash
java -version
```

If not installed:

```bash
sudo apt install openjdk-17-jdk -y
```

Verify:

```bash
java -version
```

---

### Step 3: Add Jenkins Repository Key

```bash
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
```

---

### Step 4: Add Jenkins Repository

```bash
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
/etc/apt/sources.list.d/jenkins.list > /dev/null
```

---

### Step 5: Update Repository

```bash
sudo apt update
```

---

### Step 6: Install Jenkins

```bash
sudo apt install jenkins -y
```

---

### Step 7: Start Jenkins

```bash
sudo systemctl start jenkins
```

Enable auto-start:

```bash
sudo systemctl enable jenkins
```

---

### Step 8: Verify Jenkins Service

```bash
sudo systemctl status jenkins
```

Expected:

```text
active (running)
```

---

### Step 9: Open Port 8080

If UFW is enabled:

```bash
sudo ufw allow 8080
```

---

### Step 10: Access Jenkins

Browser:

```text
http://localhost:8080
```

or

```text
http://<server-ip>:8080
```

---

### Step 11: Get Initial Admin Password

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

Copy the password.

---

### Step 12: Unlock Jenkins

Paste password into:

```text
http://localhost:8080
```

---

### Step 13: Install Suggested Plugins

Click:

```text
Install Suggested Plugins
```

Wait for completion.

---

### Step 14: Create Admin User

Provide:

```text
Username
Password
Email
```

---

### Step 15: Jenkins Ready

Dashboard:

```text
Manage Jenkins
New Item
Build Jobs
Pipelines
```

---

### For Your Timesheet

**Task:**

```text
Jenkins Installation and Configuration
```

**What I Learned:**

```text
Understood Jenkins installation and configuration on Linux, Java prerequisites, repository setup, Jenkins service management, accessing Jenkins through the web interface, initial administrator setup, plugin installation, and Jenkins dashboard configuration.
```

If you actually perform the installation, change **"Understood"** to **"Installed and configured"**.

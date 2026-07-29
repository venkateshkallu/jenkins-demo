# Phase 4: Freestyle Job

## Create Freestyle Project

Navigate to:

```text
New Item
→ Freestyle Project
```

Provide:

```text
Job Name: demo-job
```

Save the configuration.

![system message](../jenkins/screenshot/3-freestylejobs/1-Screenshot%20from%202026-06-22%2011-43-09.png)

---

## Configure Build Step

Navigate to:

```text
Build
→ Add Build Step
→ Execute Shell
```

Add:

```bash
echo "Hello Jenkins"
hostname
date
```

Save the configuration.


![system message](../jenkins/screenshot/3-freestylejobs/2-Screenshot%20from%202026-06-22%2011-45-09.png)

---

## Execute Build

Navigate to:

```text
Build Now
```

Trigger the build manually.

---

## Verify Build Execution

Navigate to:

```text
Build History
→ Build Number
→ Console Output
```

![system message](../jenkins/screenshot/3-freestylejobs/3-Screenshot%20from%202026-06-22%2011-46-07.png)

Verify:

```text
Hello Jenkins
Hostname
Current Date and Time
Finished: SUCCESS
```

---

## Capture Screenshots

Capture:

```text
Job Configuration
Build History
Console Output
Successful Build Status
```

---

## Expected Outcome

```text
Freestyle Project Created
Build Executed Successfully
Console Output Verified
Jenkins Job Completed Successfully
```

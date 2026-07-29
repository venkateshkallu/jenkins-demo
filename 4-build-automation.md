# Phase 5: Build Automation

## Build Periodically Configuration

Navigate:

```text
Job Configuration
→ Build Triggers
```

Enable:

```text
Build Periodically
```

Schedule:

```text
* * * * *
```

This schedule triggers the job every minute.

Save the configuration.

![system message](../jenkins/screenshot/4-schedule/1-Screenshot%20from%202026-06-22%2011-52-41.png)

---

## Build Trigger Verification

Wait for the configured schedule to execute.

Navigate:

```text
Build History
```


![system message](../jenkins/screenshot/4-schedule/2-Screenshot%20from%202026-06-22%2011-54-56.png)

Verify:

- Automatic build execution
- New build entries generated without manual intervention
- Successful build status

---

## Screenshots

- Build Trigger Configuration
- Cron Schedule Configuration
- Automatic Build Execution
- Build History
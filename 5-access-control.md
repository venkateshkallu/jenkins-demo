# Phase 6: Security & Role-Based Access Control (RBAC)

## Install Role-Based Authorization Strategy Plugin

Navigate to:

```text
Manage Jenkins
→ Plugins
→ Available Plugins
```

Search and install:

```text
Role-Based Authorization Strategy
```

Restart Jenkins if required.

![system message](../jenkins/screenshot/5-access-control/1-Screenshot%20from%202026-06-22%2012-07-18.png)
---

## Enable Role-Based Strategy

Navigate to:

```text
Manage Jenkins
→ Security
```

Under Authorization, select:

```text
Role-Based Strategy
```

Save the configuration.

![system message](../jenkins/screenshot/5-access-control/2-Screenshot%20from%202026-06-22%2012-08-45.png)
---

## Create Role

Navigate to:

```text
Manage Jenkins
→ Manage and Assign Roles
→ Manage Roles
```

Create a role:

```text
developer
```

Assign permissions:

```text
Overall Read
Job Read

```

Save the role configuration.

![system message](../jenkins/screenshot/5-access-control/3-Screenshot%20from%202026-06-22%2012-09-48.png)
---

## Create User

Navigate to:

```text
Manage Jenkins
→ Users
→ Create User
```

Example:

```text
Username: dev1
Password: ********
```

Save the user.

---

## Assign Role to User

Navigate to:

```text
Manage Jenkins
→ Manage and Assign Roles
→ Assign Roles
```

Add the user:

```text
dev1
```

Assign:

```text
developer
```

Save the configuration.
![system message](../jenkins/screenshot/5-access-control/4-Screenshot%20from%202026-06-22%2012-11-02.png)
---

## Verify Role Permissions

Logout from the administrator account.

Login using:

```text
dev1
```

Verify:

```text
✓ View Jobs
✓ Trigger Builds
✓ View Build History

✗ Manage Jenkins
✗ Install Plugins
✗ Create Users
✗ Modify Global Configuration

![system message](../jenkins/screenshot/5-access-control/5-Screenshot%20from%202026-06-22%2012-12-03.png)

![system message](../jenkins/screenshot/5-access-control/6-Screenshot%20from%202026-06-22%2012-14-50.png)
```

---

## Screenshots

* Role-Based Strategy Enabled
* Role Creation
* User Creation
* Role Assignment
* Developer Login
* Permission Verification

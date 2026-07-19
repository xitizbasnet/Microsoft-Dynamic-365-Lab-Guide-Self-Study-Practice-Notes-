# LAB 1.4 — Common D365 Troubleshooting Scenarios

> **Lab Objective**
>
> Diagnose and resolve common Microsoft Dynamics 365 support issues.

---

# Learning Objectives

After completing this lab, you will be able to:

* Troubleshoot user access issues.
* Resolve missing or read-only form field problems.
* Diagnose email synchronization issues.
* Verify why workflows and Power Automate flows are not triggering.
* Apply Dynamics 365 troubleshooting best practices.

---

# Prerequisites

Before starting this lab, ensure you have:

* Access to the **Power Platform Admin Center**.
* Administrative permissions in Microsoft Dynamics 365.
* Access to the Microsoft 365 Admin Center.
* Appropriate permissions to review security roles, mailboxes, and processes.

---

# Lab Steps

## Step 1 — User Cannot Access Dynamics 365 App

**Objective:** Verify the most common causes of application access issues.

### Procedure

Perform the following checks:

| Check                    | Action                                                                                                                                   |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------- |
| **Dynamics 365 License** | Verify that the user has a Dynamics 365 license assigned.<br><br>Navigate to:<br>`admin.microsoft.com` → **Licenses**                    |
| **Environment Access**   | Confirm that the user has been added to the Dynamics 365 environment.<br><br>Navigate to:<br>**Power Platform Admin Center** → **Users** |
| **Security Role**        | Verify that a security role has been assigned. If not, assign the minimum required role: **Basic User**                                  |
| **Environment URL**      | Ensure the user is accessing the correct organization-specific environment URL instead of a generic Microsoft login page.                |

> ⚠️ **Important**
>
> A valid license alone does not grant access. The user must also be added to the environment and assigned an appropriate security role.

---

## Step 2 — Form Fields Missing or Read-Only

**Objective:** Identify security-related causes of unavailable form fields.

### Procedure

1. Verify whether the assigned **Security Role** includes:

* Create privilege
* Write privilege

for the affected entity.

2. Navigate to:

**Admin** → **Security Role**

3. Verify the assigned **Field-Level Security Profile**.

4. Check whether a **Field-Level Security Profile** is restricting access to the affected field for the user.

> 💡 **Tip**
>
> Field-level security overrides standard entity permissions for protected fields.

---

## Step 3 — Emails Not Syncing with Dynamics 365

**Objective:** Diagnose mailbox and email synchronization issues.

### Procedure

1. Navigate to:

**Settings** → **Email Configuration** → **Mailboxes**

2. Select the user's mailbox.

3. Click:

**Test & Enable Mailbox**

4. Review any reported errors, including:

* Authentication failures
* Server-side synchronization issues

5. Verify that **Server-Side Synchronization** is enabled in **Email Settings**.

6. Confirm that the environment is **not** configured to use the legacy **Dynamics Email Router**.

> ℹ️ **Note**
>
> Server-Side Synchronization is the recommended email integration method for modern Dynamics 365 environments.

---

## Step 4 — Workflows / Flows Not Triggering

**Objective:** Determine why automated processes are not executing.

### Procedure

#### For Power Automate

1. Open **Power Automate**.

2. Verify that the flow is turned **ON**.

3. Review the **Run History**.

4. Check for common errors such as:

* Permission denied
* Missing required field

#### For Classic Workflows

1. Navigate to:

**Settings** → **Processes**

2. Verify that the workflow status is:

```text
Activated
```

> ✅ **Validation**
>
> Confirm that the flow or workflow is enabled and that recent executions completed successfully without errors.

---

# 🛠️ Best Practice Tips

> **Important**

✔ Use the **Dynamics 365 Unified Interface** instead of the legacy interface, as Microsoft has deprecated the older UI.

✔ Before escalating an issue, open the browser developer tools (**F12**) and review the **JavaScript Console** for client-side errors.

✔ Monitor asynchronous operations by navigating to:

**Settings** → **Data Management** → **System Jobs**

Review failed jobs to identify background processing issues.

✔ Always reproduce issues using an **Incognito/InPrivate** browser session to eliminate browser cache and extension-related problems.

---

# Troubleshooting Checklist

| Issue                           | Primary Verification                                            |
| ------------------------------- | --------------------------------------------------------------- |
| User cannot access Dynamics 365 | License, environment membership, security role, environment URL |
| Missing or read-only fields     | Security role privileges and Field-Level Security Profile       |
| Email synchronization failure   | Mailbox configuration, Server-Side Sync, mailbox test results   |
| Workflow or flow not running    | Flow status, run history, activated workflow, permissions       |

---

# Summary

In this lab, you completed the following tasks:

* Verified user access and licensing issues.
* Diagnosed missing or read-only form fields.
* Troubleshot mailbox and email synchronization problems.
* Verified Power Automate flows and classic workflows.
* Reviewed common troubleshooting techniques and Dynamics 365 support best practices.

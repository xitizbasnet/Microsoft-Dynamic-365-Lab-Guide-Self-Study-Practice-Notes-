# LAB 5.2 — Active Directory & Group Policy

> **Lab Objective**
>
> Manage users in Active Directory, reset passwords, unlock accounts, and apply Group Policy Objects (GPOs).

---

# Learning Objectives

After completing this lab, you will be able to:

* Manage Active Directory user accounts.
* Reset passwords and unlock locked accounts.
* Disable accounts following IT offboarding procedures.
* Perform Active Directory administration using PowerShell.
* Create and configure Group Policy Objects.
* Troubleshoot Group Policy application issues.
* Apply Active Directory administration best practices.

---

# Prerequisites

Before starting this lab, ensure you have:

* A Windows Server Active Directory domain environment.
* Domain Administrator or delegated administrative permissions.
* Access to:

  * Active Directory Users and Computers.
  * Group Policy Management Console.
  * PowerShell Active Directory module.

---

# Active Directory Management Overview

Active Directory (AD) provides centralized identity and access management for Windows environments.

Common administrator tasks include:

* User account management.
* Password resets.
* Account unlocks.
* Security policy enforcement.
* Group Policy configuration.

---

# Lab Steps

## Step 1 — Common AD Tasks Using ADUC

**Objective:** Perform common user administration tasks using Active Directory Users and Computers.

---

## Open Active Directory Users and Computers

Launch:

```text id="8q4nkm"
Active Directory Users and Computers (dsa.msc)
```

---

## Reset User Password

### Procedure

1. Find the required user account.

2. Right-click the user.

3. Select:

```text id="m7v2qx"
Reset Password
```

4. Configure password settings.

5. Uncheck:

```text id="c5n8wp"
User must change password at next logon
```

> 💡 **Tip**
>
> Password reset procedures should follow organizational security policies.

---

## Unlock User Account

### Procedure

1. Right-click the user account.

2. Select:

```text id="w4r9kd"
Properties → Account tab
```

3. Select:

```text id="p2m6xa"
Unlock Account
```

---

## Disable User Account

### Procedure

1. Right-click the user.

2. Select:

```text id="z6t3qn"
Disable Account
```

### Usage Scenario

For employee departures:

* Disable the account.
* Move the account to the appropriate organizational unit.
* Do not delete immediately.

> ⚠️ **Important**
>
> Disabled accounts preserve audit history and allow recovery if required.

---

# Step 2 — PowerShell Active Directory Administration

**Objective:** Perform AD administration tasks using PowerShell commands.

---

## View User Information

```powershell id="g8k2mr"
Get-ADUser -Identity jsmith -Properties *
```

Purpose:

* Displays complete user account information.

---

## Reset User Password

```powershell id="q3m7vx"
Set-ADAccountPassword -Identity jsmith -Reset -NewPassword (Read-Host -AsSecureString)
```

Purpose:

* Resets the password for the specified user.

---

## Unlock User Account

```powershell id="r6n9kp"
Unlock-ADAccount -Identity jsmith
```

Purpose:

* Removes account lockout status.

---

## Find Disabled Accounts

```powershell id="y5w8cm"
Get-ADUser -Filter 'Enabled -eq $false' | Select Name, SamAccountName
```

Purpose:

* Lists disabled Active Directory accounts.

---

# Step 3 — Create & Manage Group Policy Objects (GPO)

**Objective:** Create security policies using Group Policy Management.

---

## Open Group Policy Management Console

Launch:

```text id="f9k3vd"
Group Policy Management Console (gpmc.msc)
```

---

## Create a New GPO

### Procedure

1. Right-click the required Organizational Unit (OU).

2. Select:

```text id="h7q2mz"
Create a GPO
```

3. Name the policy:

```text id="j4p8nx"
Desktop Lockdown Policy
```

---

## Edit the GPO

Navigate to:

```text id="v3m6qs"
Computer Configuration → Policies → Windows Settings → Security Settings
```

---

## Example Security Settings

Configure:

| Policy Setting            | Value             |
| ------------------------- | ----------------- |
| Minimum Password Length   | 12                |
| Account Lockout Threshold | 5 failed attempts |

> ℹ️ **Note**
>
> Group Policy Objects allow administrators to centrally enforce security and configuration settings across domain computers.

---

# Step 4 — Troubleshoot GPO Not Applying

**Objective:** Diagnose Group Policy processing issues.

---

## Force Group Policy Update

Run on the affected machine:

```cmd id="n8x4kp"
gpupdate /force
```

---

## Review Applied Policies

Run:

```cmd id="b6r9qm"
gpresult /r
```

---

## Generate Detailed GPO Report

Run:

```cmd id="t5v2wy"
gpresult /h C:\gpreport.html
```

Open the generated file in a browser.

---

## GPO Troubleshooting Checklist

Check the following:

✔ Is the machine in the correct OU?

✔ Is the GPO linked correctly?

✔ Is the GPO enabled?

✔ Is the WMI filter correct?

---

## Advanced GPO Reporting Commands

### Computer-Applied GPOs

```cmd id="p8m4zr"
gpresult /scope computer /v
```

Purpose:

* Shows GPOs applied to the computer account.

---

### User-Applied GPOs

```cmd id="q7w3nc"
gpresult /scope user /v
```

Purpose:

* Shows GPOs applied to the user account.

---

# 🔐 Best Practice Tips

> **Important**

✔ Never delete Active Directory accounts immediately for leavers.

Recommended process:

1. Disable the account.
2. Move it to:

```text id="m5x8qa"
Disabled Users OU
```

3. Retain the account for audit and recovery purposes.

---

✔ Test GPOs on a:

* Pilot group.
* Test OU.

before deploying domain-wide.

---

✔ Use:

```text id="d3k7vp"
Block Inheritance
```

sparingly.

Excessive use makes GPO troubleshooting more difficult.

---

✔ Audit Active Directory changes.

Enable:

```text id="x6q9mt"
Audit Account Management
```

through:

```text id="r2v5nk"
Default Domain Controllers Policy
```

---

# Validation Checklist

| Task                          | Expected Result                 |
| ----------------------------- | ------------------------------- |
| ADUC opened                   | User management available       |
| Password reset completed      | User password updated           |
| Account unlocked              | User can authenticate           |
| Account disabled              | Leaver account secured          |
| PowerShell commands tested    | AD tasks completed successfully |
| GPO created                   | Security policy configured      |
| GPO troubleshooting performed | Applied policies verified       |

---

# Summary

In this lab, you completed the following tasks:

* Managed Active Directory user accounts.
* Reset passwords and unlocked accounts.
* Disabled accounts using proper offboarding practices.
* Used PowerShell for AD administration.
* Created and configured Group Policy Objects.
* Troubleshot GPO application issues.
* Applied Active Directory security best practices.

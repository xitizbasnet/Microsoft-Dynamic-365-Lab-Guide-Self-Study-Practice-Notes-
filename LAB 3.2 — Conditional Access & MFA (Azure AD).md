# LAB 3.2 — Conditional Access & MFA (Azure AD)

> **Lab Objective**
>
> Create Conditional Access policies and enforce Multi-Factor Authentication (MFA) for user sign-ins using Azure Active Directory.

> **Note**
>
> Microsoft Azure Active Directory is now known as **Microsoft Entra ID**. This lab uses **Azure AD** terminology to match the original lab content and portal navigation.

---

# Learning Objectives

After completing this lab, you will be able to:

* Enable Security Defaults for basic MFA protection.
* Create Conditional Access policies.
* Require MFA for user authentication.
* Register MFA methods for users.
* Test Conditional Access policies.
* Review sign-in logs and MFA results.
* Apply identity security best practices.

---

# Prerequisites

Before starting this lab, ensure you have:

* An Azure AD (Microsoft Entra ID) tenant.
* Azure AD Administrator permissions.
* A test user account.
* Microsoft Authenticator installed on a mobile device.
* Access to Azure AD sign-in logs.

---

# Lab Steps

## Step 1 — Enable Security Defaults (Quick MFA for Small Organizations)

**Objective:** Enable Microsoft-managed security settings to quickly protect user accounts.

### Procedure

1. Navigate to:

   **Azure AD** → **Properties**

2. Select:

   **Manage Security Defaults**

3. Enable:

```text
Enable: Yes
```

4. Save the configuration.

### Security Defaults Provide:

* MFA enforcement for administrators.
* Blocking of legacy authentication.
* Protection against risky sign-ins.

> ⚠️ **Important**
>
> Disable Security Defaults if you plan to use custom Conditional Access policies, as both configurations should not be managed simultaneously.

---

## Step 2 — Create a Conditional Access Policy

**Objective:** Create a policy requiring MFA for user access.

### Procedure

1. Navigate to:

   **Azure AD** → **Security** → **Conditional Access**

2. Select:

   **+ New Policy**

3. Configure the policy:

| Setting         | Value                         |
| --------------- | ----------------------------- |
| **Policy Name** | Require MFA for All Users     |
| **Users**       | All Users (or specific group) |
| **Cloud Apps**  | All Cloud Apps                |
| **Conditions**  | Leave default for now         |

4. Configure Access Controls:

Navigate to:

**Access Controls** → **Grant**

5. Select:

```text
Require Multi-Factor Authentication
```

6. Click:

**Select**

7. Enable the policy:

```text
Enable Policy: On
```

8. Click:

**Create**

> 💡 **Tip**
>
> Conditional Access policies provide identity-based security controls by evaluating users, devices, locations, and applications before granting access.

---

## Step 3 — Register MFA Method for a User

**Objective:** Configure a user account for MFA authentication.

### Procedure

1. Sign in using the test user account.

2. The user will be prompted:

```text
Set up Microsoft Authenticator app
```

3. Install the **Microsoft Authenticator** application on a mobile device.

4. Scan the displayed QR code.

5. Complete MFA registration.

### Verify MFA Registration

Administrators can view MFA status by navigating to:

```text
Azure AD → Users → Per-User MFA
```

> ℹ️ **Note**
>
> MFA registration must be completed before users can successfully satisfy Conditional Access MFA requirements.

---

## Step 4 — Test the Conditional Access Policy

**Objective:** Verify that the Conditional Access policy correctly enforces MFA.

### Procedure

1. Open a private/incognito browser window.

2. Sign in using the test user account.

3. Verify that the user is prompted for MFA.

Expected authentication method:

```text
Microsoft Authenticator app notification
```

4. Review the sign-in activity:

Navigate to:

```text
Azure AD → Sign-in Logs
```

5. Confirm the result:

```text
MFA Satisfied
```

> ✅ **Validation**
>
> The Conditional Access policy is working correctly when the user sign-in shows MFA as successfully satisfied.

---

# 🔐 Best Practice Tips

> **Important**

✔ Always create a **Break-Glass Administrator account** that is excluded from Conditional Access policies to prevent accidental tenant lockout.

✔ Use **Report-Only mode** first to evaluate the impact of a Conditional Access policy before enforcing it.

✔ Block legacy authentication protocols:

* IMAP
* POP3
* SMTP AUTH

These protocols can bypass modern authentication and MFA protections.

✔ Configure **Named Locations** (IP whitelisting) to reduce MFA prompts for trusted office network users.

---

# Validation Checklist

| Task                              | Expected Result                            |
| --------------------------------- | ------------------------------------------ |
| Security Defaults enabled         | MFA protection enabled                     |
| Conditional Access policy created | Require MFA policy active                  |
| MFA method registered             | User successfully registered Authenticator |
| Policy tested                     | User prompted for MFA                      |
| Sign-in logs reviewed             | MFA Satisfied result confirmed             |

---

# Summary

In this lab, you completed the following tasks:

* Enabled Security Defaults for quick MFA protection.
* Created a Conditional Access policy requiring MFA.
* Registered Microsoft Authenticator for a user.
* Tested MFA enforcement through Conditional Access.
* Reviewed sign-in logs for authentication results.
* Applied identity security best practices.

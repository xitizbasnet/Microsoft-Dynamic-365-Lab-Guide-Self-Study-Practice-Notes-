# LAB 2.2 — Azure Active Directory & User Provisioning

> **Lab Objective**
>
> Create and manage Azure Active Directory (Azure AD) users, groups, and assign administrative roles.

> **Note**
>
> Microsoft Azure Active Directory is now known as **Microsoft Entra ID**. This lab uses the term **Azure Active Directory (Azure AD)** to match the portal navigation and the original lab content.

---

# Learning Objectives

After completing this lab, you will be able to:

* Navigate Azure Active Directory (Microsoft Entra ID).
* Create and manage Azure AD users.
* Create Security Groups.
* Assign Azure AD administrative roles.
* Perform basic Azure AD user management using PowerShell.
* Apply identity management best practices.

---

# Prerequisites

Before starting this lab, ensure you have:

* An active Azure subscription.
* Access to the Azure Portal.
* Azure AD (Microsoft Entra ID) administrative permissions.
* Windows PowerShell (running as Administrator).
* Internet connectivity.

---

# Lab Steps

## Step 1 — Navigate Azure Active Directory

**Objective:** Locate your Azure AD tenant information.

### Procedure

1. Sign in to the Azure Portal.

2. Search for:

   **Azure Active Directory**

3. Open **Overview**.

4. Review the following tenant information:

| Property           | Description                                |
| ------------------ | ------------------------------------------ |
| **Tenant ID**      | Unique identifier for your Azure AD tenant |
| **Primary Domain** | `yourdomain.onmicrosoft.com`               |

> 💡 **Tip**
>
> The Tenant ID and Primary Domain are frequently required during application integrations and identity configuration.

---

## Step 2 — Create a New User

**Objective:** Provision a new Azure AD user account.

### Procedure

1. Navigate to:

   **Azure AD** → **Users**

2. Select:

   **+ New User** → **Create User**

3. Configure the following user information:

| Property       | Value                                       |
| -------------- | ------------------------------------------- |
| **Username**   | `it.support@[yourdomain].onmicrosoft.com`   |
| **Name**       | IT Support User                             |
| **Password**   | Auto-generate (copy the temporary password) |
| **Job Title**  | Desktop Support L2                          |
| **Department** | IT                                          |

4. Create the user.

> ⚠️ **Important**
>
> Copy and securely store the temporary password. The user will typically be required to change it during the first sign-in.

---

## Step 3 — Create a Security Group

**Objective:** Organize users by using Azure AD Security Groups.

### Procedure

1. Navigate to:

   **Azure AD** → **Groups**

2. Select:

   **+ New Group**

3. Configure the group:

| Setting             | Value            |
| ------------------- | ---------------- |
| **Group Type**      | Security         |
| **Group Name**      | Dubai-IT-Support |
| **Membership Type** | Assigned         |

4. Add Members.

5. Select the user created in the previous step.

6. Click **Create**.

> 💡 **Tip**
>
> Security Groups simplify permission management by allowing administrators to assign permissions to a group rather than individual users.

---

## Step 4 — Assign an Azure AD Role

**Objective:** Grant administrative permissions through Azure AD roles.

### Procedure

1. Navigate to:

   **Azure AD** → **Roles and Administrators**

2. Search for:

   **Helpdesk Administrator**

3. Open the role.

4. Select:

   **+ Add Assignments**

5. Select the appropriate user or Security Group.

6. Review the following commonly used roles for L1/L2 support personnel:

| Azure AD Role              | Purpose                                       |
| -------------------------- | --------------------------------------------- |
| **Helpdesk Administrator** | Reset passwords and manage user support tasks |
| **User Administrator**     | Manage users and groups                       |
| **Reports Reader**         | View Azure reports and sign-in information    |

> ℹ️ **Note**
>
> Assigning roles to Security Groups instead of individual users simplifies ongoing administration.

---

## Step 5 — PowerShell – Azure AD User Management

**Objective:** Manage Azure AD users by using PowerShell.

### Install the Azure AD PowerShell Module

Run PowerShell as **Administrator**, then execute:

```powershell
Install-Module -Name AzureAD
```

### Connect to Azure AD

```powershell
Connect-AzureAD
```

### Search for a User

```powershell
Get-AzureADUser -SearchString "IT Support"
```

### Update the User's Department

```powershell
Set-AzureADUser -ObjectId [UserID] -Department "IT Operations"
```

> 💡 **Tip**
>
> Replace **[UserID]** with the Object ID of the target Azure AD user.

---

# 🔐 Best Practice Tips

> **Important**

✔ Enable **Multi-Factor Authentication (MFA)** for all administrator accounts. This is a non-negotiable security baseline.

✔ Use **Guest Users** for external contractors. Never create standard internal accounts for external users.

✔ Assign permissions through **Security Groups** instead of assigning roles directly to individual users whenever possible.

✔ Review **Sign-in Logs** on a weekly basis to identify unusual login patterns and investigate potential security concerns.

---

# Validation Checklist

| Task                         | Expected Result                                   |
| ---------------------------- | ------------------------------------------------- |
| Azure AD tenant reviewed     | Tenant ID and Primary Domain identified           |
| User created                 | IT Support User available in Azure AD             |
| Security Group created       | Dubai-IT-Support exists with assigned member      |
| Azure AD role assigned       | Helpdesk Administrator assigned successfully      |
| PowerShell commands executed | User information queried and updated successfully |

---

# Summary

In this lab, you completed the following tasks:

* Navigated Azure Active Directory (Microsoft Entra ID).
* Created a new Azure AD user.
* Created a Security Group and added members.
* Assigned Azure AD administrative roles.
* Managed Azure AD users using PowerShell.
* Reviewed Azure identity and access management best practices.

# LAB 1.2 — User Management & Security Roles

> **Lab Objective**
>
> Create users, assign security roles, and manage teams in Microsoft Dynamics 365.

---

# Learning Objectives

After completing this lab, you will be able to:

* Access the Power Platform Admin Center.
* Add users to a Dynamics 365 environment.
* Assign security roles to users.
* Create teams and assign team-based security roles.
* Understand security role inheritance and permission management.

---

# Prerequisites

Before starting this lab, ensure you have:

* A Dynamics 365 trial or sandbox environment.
* Power Platform Administrator or System Administrator permissions.
* Access to the Microsoft 365 Admin Center.
* An Azure Active Directory (Microsoft Entra ID) user account available for assignment.

---

# Lab Steps

## Step 1 — Access the Power Platform Admin Center

**Objective:** Open your Dynamics 365 environment and navigate to user management.

### Procedure

1. Go to:

   ```text
   admin.powerplatform.microsoft.com
   ```

2. Select **Environments**.

3. Select your organization (environment).

4. Click:

   **Settings** → **Users + Permissions** → **Users**

> 💡 **Tip**
>
> This page allows administrators to manage users, permissions, security roles, and environment access.

---

## Step 2 — Add a New User

**Objective:** Add an existing Microsoft 365 user to the Dynamics 365 environment.

### Procedure

1. Click **+ Add User**.

2. Search for a user from **Azure Active Directory (Microsoft Entra ID)**.

   > **Requirement:** The user must already exist in Microsoft 365.

3. If the user is **not found**:

   * Go to:

     ```text
     admin.microsoft.com
     ```

   * Navigate to **Active Users**.

   * Add the user first.

4. Return to **Dynamics 365 Users**.

5. Refresh the page.

6. Search again to locate the newly created user.

> ℹ️ **Note**
>
> Newly created Microsoft 365 users may take a short time to synchronize with Dynamics 365.

---

## Step 3 — Assign a Security Role

**Objective:** Grant the appropriate permissions to a user.

### Procedure

1. Select the desired user.

2. Click **Manage Roles**.

3. Assign the following security role:

   * **Customer Service Representative**

4. Become familiar with these common security roles:

| Security Role                              | Description                                                         |
| ------------------------------------------ | ------------------------------------------------------------------- |
| **System Administrator**                   | Full administrative access across the environment.                  |
| **System Customizer**                      | Customize applications without full administrative privileges.      |
| **Customer Service Representative (CSR)**  | Standard permissions for customer service agents.                   |
| **Customer Service Manager (CSR Manager)** | Additional management capabilities for customer service operations. |
| **Basic User**                             | Limited access to standard user functionality.                      |

5. Click **OK**.

6. Confirm that the assigned role appears under the user's profile.

> ⚠️ **Important**
>
> Security roles determine which records, entities, and actions a user can access within Dynamics 365.

---

## Step 4 — Create a Team and Assign a Role

**Objective:** Manage permissions through team-based security.

### Procedure

1. Navigate to:

   **Settings** → **Teams**

2. Click **+ New Team**.

3. Create a team with the following details:

| Property      | Value            |
| ------------- | ---------------- |
| **Team Name** | Dubai L2 Support |

4. Add team members.

5. Assign the following security role to the team:

* **Customer Service Manager**

6. Verify that individual members inherit the permissions assigned at the team level.

> 💡 **Tip**
>
> Team-based security simplifies permission management for groups of users performing similar responsibilities.

---

# 🔐 Best Practice Tips

> **Important**

✔ Follow the **Principle of Least Privilege**—assign only the minimum permissions required for users to perform their tasks.

✔ Security roles are **additive**. If a user has **two roles**, they receive the combined privileges from both roles.

✔ Use **Teams** to manage permissions for multiple users instead of assigning roles individually.

✔ Audit role changes by navigating to:

```text
Admin Center → Analytics → Power Platform Admin Activity
```

This helps administrators monitor permission changes and maintain governance.

---

# Summary

In this lab, you completed the following tasks:

* Accessed the Power Platform Admin Center.
* Added users to a Dynamics 365 environment.
* Assigned security roles to users.
* Created a team and assigned team-level permissions.
* Verified inherited permissions for team members.
* Reviewed Dynamics 365 security and permission management best practices.

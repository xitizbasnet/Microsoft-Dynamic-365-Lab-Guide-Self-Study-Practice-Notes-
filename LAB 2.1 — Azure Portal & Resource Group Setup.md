# LAB 2.1 — Azure Portal & Resource Group Setup

> **Lab Objective**
>
> Navigate the Microsoft Azure Portal, create resource groups, and apply resource tags for organization and management.

---

# Learning Objectives

After completing this lab, you will be able to:

* Access the Azure Portal.
* Set up an Azure Free Account.
* Create and manage Resource Groups.
* Apply tags to Azure resources.
* Execute basic Azure CLI commands using Azure Cloud Shell.
* Apply Azure resource management best practices.

---

# Prerequisites

Before starting this lab, ensure you have:

* A Microsoft account.
* Internet access.
* An Azure Free Account (or an active Azure subscription).
* Permission to create Azure resources within your subscription.

---

# Lab Steps

## Step 1 — Access the Azure Portal & Set Up a Free Account

**Objective:** Sign in to the Azure Portal and familiarize yourself with the interface.

### Procedure

1. Navigate to:

   ```text
   portal.azure.com
   ```

2. Sign in using your Microsoft account.

3. If you are a new Azure user:

   * Visit:

     ```text
     azure.microsoft.com/free
     ```

   * Sign up for:

     * **$200 Azure credit** for the first **30 days**
     * Access to Azure Free Tier services

4. Personalize your Azure Dashboard by pinning frequently used services.

   * Drag and drop tiles to organize your workspace.

> 💡 **Tip**
>
> Customizing the dashboard provides quick access to frequently used Azure services and administrative tools.

---

## Step 2 — Create a Resource Group

**Objective:** Create a logical container for Azure resources.

### Procedure

1. In the Azure Portal search bar, search for:

   **Resource Groups**

2. Select **+ Create**.

3. Configure the following settings:

| Setting            | Value                                |
| ------------------ | ------------------------------------ |
| **Subscription**   | Azure Free Tier                      |
| **Resource Group** | RG-Dubai-IT                          |
| **Region**         | UAE North (or East US for Free Tier) |

4. Select:

* **Review + Create**
* **Create**

> ℹ️ **Note**
>
> Resource Groups are logical containers used to organize Azure resources. Creating a Resource Group does **not** incur any cost by itself.

---

## Step 3 — Apply Tags to Resources

**Objective:** Organize Azure resources using metadata tags.

### Procedure

1. Open the **RG-Dubai-IT** Resource Group.

2. Select **Tags** from the left navigation menu.

3. Click **+ Add Tag**.

4. Configure the following tags:

| Key             | Value      |
| --------------- | ---------- |
| **Environment** | Production |
| **Owner**       | IT-Support |

5. Save the tags.

> 💡 **Tip**
>
> Tags simplify resource organization, cost allocation, reporting, automation, and filtering across Azure subscriptions.

---

## Step 4 — Explore Azure CLI Basics

**Objective:** Execute basic Azure Resource Group management commands using Azure Cloud Shell.

### Procedure

1. Open **Azure Cloud Shell** by selecting the **>_** icon in the Azure Portal toolbar.

2. Select **Bash** as the shell environment.

3. Run the following commands.

### List Resource Groups

```bash
az group list --output table
```

### Create a Resource Group

```bash
az group create --name RG-Test --location uaenorth
```

### Delete a Resource Group

```bash
az group delete --name RG-Test --yes --no-wait
```

> ⚠️ **Warning**
>
> Deleting a Resource Group permanently deletes **all resources contained within it**.

---

# ☁️ Best Practice Tips

> **Important**

✔ Use a consistent naming convention for Azure resources.

Example:

```text
[workload]-[env]-[region]-[instance]
```

Example resource name:

```text
vm-prod-uae-01
```

✔ Design Resource Groups around the lifecycle of your workloads.

> Deleting a Resource Group deletes **all** resources inside it.

✔ Monitor Azure spending daily by using **Azure Cost Management + Billing**.

✔ Apply **Resource Locks** (**Read-only** or **Delete**) to production Resource Groups to help prevent accidental modifications or deletions.

---

# Validation Checklist

| Task                   | Expected Result                              |
| ---------------------- | -------------------------------------------- |
| Azure Portal accessed  | Successfully signed in                       |
| Resource Group created | RG-Dubai-IT is available                     |
| Tags applied           | Environment and Owner tags are visible       |
| Azure CLI tested       | Resource Group commands execute successfully |

---

# Summary

In this lab, you completed the following tasks:

* Accessed the Microsoft Azure Portal.
* Created an Azure Resource Group.
* Applied metadata tags for resource organization.
* Executed Azure CLI commands using Azure Cloud Shell.
* Reviewed Azure resource management and governance best practices.

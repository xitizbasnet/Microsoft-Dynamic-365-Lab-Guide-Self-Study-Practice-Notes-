# LAB 3.4 — Data Loss Prevention (DLP) Policies

> **Lab Objective**
>
> Create a Data Loss Prevention (DLP) policy to protect sensitive data in Microsoft 365, including Email, SharePoint, OneDrive, and Teams.

---

# Learning Objectives

After completing this lab, you will be able to:

* Access Microsoft Purview Compliance Portal.
* Create and configure Microsoft 365 DLP policies.
* Define sensitive information detection rules.
* Configure DLP actions and user notifications.
* Test DLP policy behavior.
* Review DLP policy match reports.
* Apply data protection best practices.

---

# Prerequisites

Before starting this lab, ensure you have:

* Access to a Microsoft 365 tenant.
* Appropriate permissions for Microsoft Purview Compliance Portal.
* Access to:

  * Exchange Online.
  * SharePoint Online.
  * OneDrive.
  * Microsoft Teams.
* A test user account for DLP validation.

---

# Lab Steps

## Step 1 — Open Microsoft Purview Compliance Portal

**Objective:** Access the Data Loss Prevention management area.

### Procedure

1. Navigate to:

```text id="6f3j8q"
compliance.microsoft.com
```

2. Open:

**Data Loss Prevention** → **Policies**

3. Review existing policies (if any) before creating new ones.

> 💡 **Tip**
>
> Reviewing existing policies helps prevent duplicate rules and unintended policy conflicts.

---

# Step 2 — Create a DLP Policy

**Objective:** Create a policy to identify and protect sensitive information.

### Procedure

1. Select:

**+ Create Policy**

2. Choose one of the following approaches:

### Option 1 — Use a Template

Select:

```text id="m7j2pk"
Start from Template: Financial
```

Configure:

```text id="x5w8qv"
UAE Financial Data
```

### Option 2 — Create a Custom Policy

Select:

```text id="2q4h8m"
Custom Policy
```

Configure:

| Setting         | Value                     |
| --------------- | ------------------------- |
| **Policy Name** | Block Credit Card Sharing |

3. Configure policy locations:

| Location           | Enabled |
| ------------------ | ------- |
| **Exchange Email** | Yes     |
| **SharePoint**     | Yes     |
| **OneDrive**       | Yes     |
| **Teams Chat**     | Yes     |

> ℹ️ **Note**
>
> DLP policies can protect sensitive information across multiple Microsoft 365 workloads.

---

# Step 3 — Define Policy Rules

**Objective:** Configure conditions, actions, and notifications for sensitive data protection.

### Procedure

1. Configure content detection:

| Setting                        | Value                |
| ------------------------------ | -------------------- |
| **Content Contains**           | Sensitive Info Types |
| **Sensitive Information Type** | Credit Card Number   |
| **Instance Count**             | 1 or more            |
| **Confidence Level**           | High                 |

2. Configure policy actions:

| Action                  | Configuration                     |
| ----------------------- | --------------------------------- |
| **Sharing Restriction** | Block sharing with external users |
| **User Notification**   | Notify user with policy tip       |

3. Configure incident reports:

* Send alert to the compliance administrator email.

> ⚠️ **Important**
>
> DLP policies help prevent accidental or unauthorized sharing of sensitive information while providing users with guidance.

---

# Step 4 — Test the Policy

**Objective:** Verify that the DLP policy detects and responds to sensitive data.

### Procedure

1. Send an email to an external address.

2. Include a fake credit card number:

```text id="y4p1dc"
4111 1111 1111 1111
```

3. Verify that the Outlook policy tip appears:

```text id="3m0j9r"
This message may contain sensitive info
```

4. Review DLP reports:

Navigate to:

```text id="q2z6ka"
compliance.microsoft.com → Reports → DLP Policy Matches
```

> ✅ **Validation**
>
> Confirm that the test message is detected and appears in DLP policy match reports.

---

# 🔐 Best Practice Tips

> **Important**

✔ Enable DLP policies in **audit or simulation mode first** to evaluate impact before enforcing blocking actions.

✔ Educate users about **DLP policy tips**. They help staff correct risky actions without requiring IT intervention.

✔ Coordinate DLP configuration with the **legal and compliance teams** before blocking external sharing.

✔ Test DLP policies using **Microsoft sample sensitive data**. Never use real Personally Identifiable Information (PII) during testing.

---

# Validation Checklist

| Task                                  | Expected Result                             |
| ------------------------------------- | ------------------------------------------- |
| Purview Compliance Portal accessed    | DLP management page opened                  |
| DLP policy created                    | Policy available in Policies list           |
| Sensitive information rule configured | Credit Card Number detection enabled        |
| Protection actions configured         | External sharing blocked and users notified |
| Test performed                        | Policy tip displayed and match recorded     |
| Reports reviewed                      | DLP policy match visible                    |

---

# Summary

In this lab, you completed the following tasks:

* Accessed Microsoft Purview Compliance Portal.
* Created a Microsoft 365 Data Loss Prevention policy.
* Configured sensitive information detection rules.
* Protected Email, SharePoint, OneDrive, and Teams locations.
* Tested DLP policy behavior using sample sensitive data.
* Reviewed DLP reporting and data protection best practices.

# LAB 3.3 — Audit Logs & Threat Detection

> **Lab Objective**
>
> Review audit logs in Microsoft 365 and investigate suspicious activity.

> **Note**
>
> Microsoft Azure Active Directory is now known as **Microsoft Entra ID**. This lab uses **Azure AD** terminology to match the original lab content and navigation references.

---

# Learning Objectives

After completing this lab, you will be able to:

* Access Microsoft 365 audit logs.
* Search and export audit data.
* Investigate suspicious sign-in activity.
* Configure Identity Protection risk policies.
* Review Microsoft 365 Defender incidents.
* Apply security monitoring and threat detection best practices.

---

# Prerequisites

Before starting this lab, ensure you have:

* Access to a Microsoft 365 tenant.
* Appropriate permissions to access:

  * Microsoft Purview Audit logs.
  * Azure AD / Microsoft Entra ID sign-in logs.
  * Identity Protection.
  * Microsoft 365 Defender.
* A test user account for investigation activities.

---

# Lab Steps

## Step 1 — Access Microsoft 365 Audit Logs

**Objective:** Review user authentication activity through Microsoft 365 audit logs.

### Procedure

1. Navigate to:

```text id="yq3c5n"
compliance.microsoft.com
```

2. Open:

**Audit** → **Search**

3. Configure the audit search:

| Setting        | Value          |
| -------------- | -------------- |
| **Activities** | User logged in |
| **Date Range** | Last 7 days    |

4. Click:

**Search**

5. Export the results:

* Export results to CSV.
* Analyze the exported data using Microsoft Excel.

> 💡 **Tip**
>
> Audit logs provide visibility into user activities and are essential for investigating account behavior and security events.

---

# Step 2 — Investigate a Suspicious Sign-in

**Objective:** Identify potentially malicious authentication activity.

### Procedure

1. Navigate to:

```text id="3v9f1n"
Azure AD → Sign-in Logs
```

2. Apply the filter:

```text id="s9n7wl"
Status = Failure
```

3. Review suspicious activity indicators:

* Multiple failed attempts from the same IP address.
* Sign-ins from unusual countries.
* Authentication attempts during unusual hours.

4. Select a suspicious sign-in entry.

5. Open the:

**Details** tab

6. Review:

* Risk Level.
* Risk Events.

> ⚠️ **Warning**
>
> Multiple failed sign-ins or unusual authentication patterns may indicate brute-force attacks, compromised credentials, or unauthorized access attempts.

---

# Step 3 — Enable Identity Protection Alerts

**Objective:** Configure risk-based identity security controls.

### Procedure

1. Navigate to:

```text id="n8j5b0"
Azure AD → Security → Identity Protection
```

2. Open:

**User Risk Policy**

3. Configure the following settings:

| Setting       | Value                                   |
| ------------- | --------------------------------------- |
| **Condition** | User Risk = High                        |
| **Control**   | Block Access or Require Password Change |

4. Configure the **Sign-in Risk Policy**:

| Setting        | Value       |
| -------------- | ----------- |
| **Risk Level** | Medium/High |
| **Control**    | Require MFA |

> 💡 **Tip**
>
> Identity Protection uses risk signals to automatically detect and respond to suspicious authentication activity.

---

# Step 4 — Microsoft 365 Defender — Incidents Dashboard

**Objective:** Investigate security incidents across Microsoft security solutions.

### Procedure

1. Navigate to:

```text id="7hmb84"
security.microsoft.com
```

2. Open:

**Incidents & Alerts** → **Incidents**

3. Review available incidents.

4. Understand incident aggregation:

Each incident combines related alerts from multiple security areas:

* 📧 Email
* 🔐 Identity
* 💻 Endpoint

5. Investigate an incident:

* Click an incident.
* Review:

  * Evidence.
  * Affected users.
  * Recommended actions.

> ℹ️ **Note**
>
> Microsoft 365 Defender correlates security signals across workloads to provide a unified incident investigation process.

---

# 🛡️ Best Practice Tips

> **Important**

✔ Audit log retention:

| License | Retention Period |
| ------- | ---------------- |
| **E3**  | 90 days          |
| **E5**  | 1 year           |

Plan retention requirements according to compliance requirements.

✔ Alert on **Impossible Travel** sign-ins.

Example:

```text id="l6k9p2"
User logged in from UAE and USA within 1 hour
```

✔ Correlate Azure AD and Microsoft 365 logs. Attackers often compromise identity first, then target email systems.

✔ Use **Microsoft Sentinel (SIEM)** for automated threat detection and investigation at enterprise scale.

---

# Investigation Checklist

| Investigation Area       | Expected Result                         |
| ------------------------ | --------------------------------------- |
| Microsoft 365 Audit Logs | User login activity reviewed            |
| Exported Audit Data      | CSV file generated for analysis         |
| Sign-in Logs             | Failed authentication events identified |
| Risk Events              | Suspicious activity reviewed            |
| Identity Protection      | Risk policies configured                |
| Defender Incidents       | Evidence and affected users analyzed    |

---

# Summary

In this lab, you completed the following tasks:

* Accessed Microsoft 365 audit logs.
* Searched user login activities.
* Exported audit results for analysis.
* Investigated suspicious sign-in activity.
* Reviewed risk events and identity protection settings.
* Investigated Microsoft 365 Defender incidents.
* Applied audit logging and threat detection best practices.

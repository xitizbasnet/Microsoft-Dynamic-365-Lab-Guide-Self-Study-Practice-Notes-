# LAB 4.3 — ServiceNow Ticketing Walkthrough

> **Lab Objective**
>
> Navigate ServiceNow to log, manage, and resolve IT incidents.

---

# Learning Objectives

After completing this lab, you will be able to:

* Access a ServiceNow Developer Instance.
* Create and manage IT incident records.
* Work incidents through the support lifecycle.
* Use Work Notes and Comments correctly.
* Resolve incidents and generate reports.
* Apply ServiceNow ticket management best practices.

---

# Prerequisites

Before starting this lab, ensure you have:

* A ServiceNow Developer Instance.
* Internet access.
* A supported web browser.
* Basic understanding of IT incident management processes.
* Knowledge of Incident Management concepts.

---

# ServiceNow Incident Management Overview

ServiceNow Incident Management provides a structured workflow for:

1. Logging user issues.
2. Assigning incidents to support teams.
3. Tracking investigation progress.
4. Documenting resolution steps.
5. Reporting on service performance.

---

# Lab Steps

## Step 1 — Set Up ServiceNow Developer Instance (Free)

**Objective:** Create and access a free ServiceNow development environment.

### Procedure

1. Navigate to:

```text id="4r8qkd"
developer.servicenow.com
```

2. Select:

```text id="6p3x1m"
Sign Up
```

3. Request a:

```text id="k5z9fh"
Free Developer Instance
```

4. Access the instance using the following URL format:

```text id="3m7qvb"
https://[instance-id].service-now.com
```

5. Sign in using the default credentials:

| Field        | Value |
| ------------ | ----- |
| **Username** | admin |
| **Password** | admin |

6. Change the default password immediately after first login.

> ⚠️ **Important**
>
> Default credentials should never remain unchanged in any environment.

---

# Step 2 — Create an Incident in ServiceNow

**Objective:** Log a new IT support incident.

### Procedure

1. Navigate using the left menu:

```text id="0n6c2s"
Incident → Create New
```

2. Complete the incident details:

| Field                 | Value                              |
| --------------------- | ---------------------------------- |
| **Caller**            | Search and select a user           |
| **Category**          | Software                           |
| **Subcategory**       | Email                              |
| **Short Description** | Outlook not opening on user laptop |

3. Review priority calculation:

```text id="5m1v8j"
Impact (2 – Medium) + Urgency (2 – Medium) = P3
```

4. Assign the incident to:

```text id="9x4wq2"
IT Support L1 Group
```

5. Select:

```text id="q8t3pd"
Submit
```

> 💡 **Tip**
>
> ServiceNow automatically calculates priority based on Impact and Urgency values.

---

# Step 3 — Work the Incident

**Objective:** Investigate, document, and escalate the incident.

### Procedure

1. Open the incident record.

2. Understand the difference between:

| Field          | Visibility                     |
| -------------- | ------------------------------ |
| **Work Notes** | Internal support communication |
| **Comments**   | Visible to the end user        |

3. Add an internal Work Note:

```text id="m6r2yt"
Attempted profile rebuild — issue persists. Escalating to L2
```

4. Update the incident:

| Field              | Value         |
| ------------------ | ------------- |
| **State**          | In Progress   |
| **Assigned Group** | IT Support L2 |

5. Configure the Watch List:

* Add manager email for visibility on P2+ tickets.

> ℹ️ **Note**
>
> Work Notes should contain technical investigation details, while Comments should be used for customer-facing communication.

---

# Step 4 — Resolve & Generate Reports

**Objective:** Complete incident resolution and review service metrics.

### Resolve the Incident

1. Configure resolution details:

| Field                | Value                  |
| -------------------- | ---------------------- |
| **Resolution Code**  | Software Configuration |
| **Resolution Notes** | Detailed fix steps     |

2. Change the incident state:

```text id="h9v2rx"
Resolved
```

3. Verify:

* The system sends an automatic notification to the user.

---

## Generate Incident Reports

### Procedure

1. Navigate to:

```text id="w3k6mz"
Reports → Create New
```

2. Create the report:

```text id="e4n8qp"
Incident volume by category (last 30 days)
```

3. Export the report:

* PDF format.

or

* Schedule weekly email distribution.

> 💡 **Tip**
>
> Scheduled reports help support teams monitor trends and identify recurring service issues.

---

# 🛠️ Best Practice Tips

> **Important**

✔ Use ServiceNow's:

```text id="d7k1qa"
My Work
```

dashboard to track all tickets assigned to you.

✔ Remember:

* **Work Notes** are internal.
* **Comments** update the end user.

✔ SLA timers start when a ticket is created.

Always check the:

```text id="p2y6bc"
SLA tab
```

on each incident.

✔ Automate repetitive tasks using:

```text id="r5m9xf"
ServiceNow Flow Designer
```

(no-code automation).

---

# Validation Checklist

| Task                       | Expected Result                        |
| -------------------------- | -------------------------------------- |
| Developer Instance created | ServiceNow environment available       |
| Incident created           | Incident record submitted successfully |
| Incident worked            | Notes, assignment, and status updated  |
| Incident resolved          | Resolution details documented          |
| Report generated           | Incident volume report created         |

---

# Summary

In this lab, you completed the following tasks:

* Created a ServiceNow Developer Instance.
* Logged a new IT incident.
* Assigned and managed incident ownership.
* Used Work Notes and Comments appropriately.
* Escalated incidents between support levels.
* Resolved incidents and generated reports.
* Reviewed ServiceNow incident management best practices.

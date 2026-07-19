# LAB 4.2 — Problem & Change Management

> **Lab Objective**
>
> Raise a Problem Record from recurring incidents and manage a Change Request following ITIL Problem and Change Management practices.

---

# Learning Objectives

After completing this lab, you will be able to:

* Identify recurring incidents that require Problem Management.
* Create and manage Problem Records.
* Perform Root Cause Analysis (RCA) using the 5 Whys technique.
* Create and submit Change Requests (RFCs).
* Understand change approval, implementation, and closure processes.
* Apply ITIL Problem and Change Management best practices.

---

# Prerequisites

Before starting this lab, ensure you have:

* Understanding of ITIL Incident Management concepts.
* Access to an IT Service Management (ITSM) platform.
* Knowledge of incident, problem, and change records.
* Understanding of Change Advisory Board (CAB) processes.

---

# Problem & Change Management Lifecycle Overview

Problem Management focuses on identifying and eliminating the root causes of recurring incidents.

The lifecycle includes:

1. **Problem Identification**
2. **Root Cause Analysis (RCA)**
3. **Change Request Creation**
4. **Change Implementation**
5. **Problem Closure**

---

# Lab Steps

## Step 1 — Identify Recurring Incidents & Raise Problem Record

**Objective:** Convert repeated incidents into a Problem Record for root cause investigation.

### Scenario

A recurring issue is identified:

```text id="m9k4tx"
5 users reported Outlook crashes every Monday morning over 3 weeks
```

---

### Procedure

1. Create a Problem Record.

2. Enter the following details:

| Field                | Value             |
| -------------------- | ----------------- |
| **Problem Record**   | PR-2025-0042      |
| **Category**         | Email             |
| **Linked Incidents** | INC-101, 115, 132 |

3. Assign the Problem Record to:

```text id="p7c3yn"
Problem Manager
```

4. Begin investigation.

> 💡 **Tip**
>
> Problem Management focuses on identifying the cause of incidents. The immediate goal is investigation, not necessarily an instant fix.

---

# Step 2 — Root Cause Analysis (RCA)

**Objective:** Identify the underlying cause of recurring incidents.

### Technique: 5 Whys Analysis

Use the following analysis:

| Question  | Finding                                                 |
| --------- | ------------------------------------------------------- |
| **Why 1** | Outlook crashes → OST file corruption                   |
| **Why 2** | OST corrupt → auto-sync fails → disk quota exceeded     |
| **Why 3** | Disk quota issue → mailbox limit policy not enforced    |
| **Why 4** | Mailbox limit not set → migration left default settings |

---

## Root Cause Identified

```text id="8y5r2m"
Exchange mailbox size limits not configured post-migration
```

> ℹ️ **Note**
>
> Root Cause Analysis helps prevent repeated incidents by addressing the underlying technical or process failure.

---

# Step 3 — Raise a Change Request (RFC)

**Objective:** Create a controlled change to resolve the identified problem.

### Change Record Details

Create the following Change Request:

| Field               | Value                                                       |
| ------------------- | ----------------------------------------------------------- |
| **Change Record**   | CR-2025-0089                                                |
| **Change Type**     | Standard Change (pre-approved, low risk)                    |
| **Description**     | Apply mailbox size limits (50 GB) to all migrated mailboxes |
| **Risk Assessment** | Low                                                         |
| **Rollback Plan**   | Remove limits if performance issue                          |

---

### Change Approval Process

1. Submit the Change Request to:

```text id="z2f9qa"
Change Advisory Board (CAB)
```

2. Obtain approval.

3. Schedule the maintenance window.

> ⚠️ **Important**
>
> All production changes should follow an approved change management process to minimize business impact.

---

# Step 4 — Implement Change & Close Problem

**Objective:** Verify the solution and complete the Problem Management lifecycle.

### Implementation Procedure

1. Implement the change during the approved maintenance window.

Example:

```text id="r4t8vk"
Sunday 2 AM – 4 AM
```

2. Perform validation:

* Test mailboxes.
* Confirm Outlook synchronization is working.
* Verify no further crashes occur.

3. Close the Problem Record:

| Field         | Value                |
| ------------- | -------------------- |
| **Status**    | Known Error resolved |
| **Reference** | Link RFC to PR       |

4. Communicate with stakeholders:

```text id="w6q1pn"
Change implemented, no further incidents expected
```

> ✅ **Validation**
>
> The problem can be closed after confirming the change successfully prevents recurrence.

---

# 🔧 Best Practice Tips

> **Important**

✔ Problem Management is proactive. Do not wait for incidents to recur 10 times before investigating.

✔ Document Known Errors in a:

```text id="v8c2lz"
Known Error Database (KEDB)
```

This enables faster future resolution.

✔ Respect **Change Freeze Periods**, such as:

* Ramadan.
* Fiscal year-end.

No changes should be performed during freeze periods without:

```text id="j4m7qs"
VP Approval
```

✔ Separate the roles of:

| Role                 | Responsibility                                   |
| -------------------- | ------------------------------------------------ |
| **Problem Manager**  | Investigates root causes and prevents recurrence |
| **Incident Manager** | Restores services quickly                        |

Avoid combining these roles to prevent conflicts of interest.

---

# Validation Checklist

| Task                           | Expected Result                                |
| ------------------------------ | ---------------------------------------------- |
| Recurring incidents identified | Problem Record created                         |
| Problem Record assigned        | Investigation started                          |
| RCA completed                  | Root cause documented                          |
| RFC created                    | Change submitted for approval                  |
| CAB approval completed         | Maintenance window scheduled                   |
| Change implemented             | Mailbox limits applied successfully            |
| Problem closed                 | Known Error resolved and stakeholders notified |

---

# Summary

In this lab, you completed the following tasks:

* Identified recurring incidents requiring Problem Management.
* Created a Problem Record and linked related incidents.
* Performed Root Cause Analysis using the 5 Whys method.
* Created a Change Request (RFC).
* Submitted the change for CAB approval.
* Implemented the change and closed the Problem Record.
* Reviewed ITIL Problem and Change Management best practices.

# LAB 4.1 — Incident Management Workflow

> **Lab Objective**
>
> Understand and execute the full ITIL Incident Management lifecycle.

---

# Learning Objectives

After completing this lab, you will be able to:

* Understand the ITIL Incident Management process lifecycle.
* Log and categorize incidents correctly.
* Perform initial troubleshooting and diagnosis.
* Escalate incidents according to SLA requirements.
* Document resolutions and close incidents properly.
* Apply incident management best practices.

---

# Prerequisites

Before starting this lab, ensure you have:

* Basic understanding of IT Service Management (ITSM) concepts.
* Access to an incident management or ticketing system.
* Knowledge of ITIL incident lifecycle processes.
* Understanding of priority, impact, urgency, and SLA concepts.

---

# Incident Management Lifecycle Overview

The ITIL Incident Management lifecycle focuses on restoring normal service operation as quickly as possible while minimizing business impact.

The lifecycle includes:

1. **Incident Identification & Logging**
2. **Categorization & Initial Diagnosis**
3. **Escalation**
4. **Resolution & Closure**

---

# Lab Steps

## Step 1 — Incident Identification & Logging

**Objective:** Record the incident details and assign the correct priority.

### Scenario

A user reports:

```text id="q6w9hm"
"Outlook not loading since 9 AM"
```

The incident is reported through:

* 📞 Phone
* 📧 Email
* 🌐 Portal

---

### Procedure

1. Log the incident with the following information:

| Field            | Value                      |
| ---------------- | -------------------------- |
| **Incident ID**  | Generated ticket reference |
| **Date/Time**    | Incident creation time     |
| **User Details** | Reporting user information |
| **Category**     | Email                      |
| **Priority**     | P2                         |

2. Assign impact and urgency:

| Attribute   | Value                         |
| ----------- | ----------------------------- |
| **Impact**  | High (affects 1 person)       |
| **Urgency** | High (critical business need) |

3. Apply the Priority Matrix:

| Priority | Description |
| -------- | ----------- |
| **P1**   | Critical    |
| **P2**   | High        |
| **P3**   | Medium      |
| **P4**   | Low         |

> 💡 **Tip**
>
> Correct prioritization ensures incidents are handled according to business impact and urgency.

---

# Step 2 — Incident Categorization & Initial Diagnosis

**Objective:** Perform first-level troubleshooting and determine the incident scope.

### L1 Troubleshooting Process

1. Determine whether the issue affects:

* Outlook Desktop application.
* Outlook Web App (OWA).

2. Use this information to identify whether the issue is:

* A client-side issue.
* A server-side issue.

---

### L1 Troubleshooting Checklist

Perform the following checks:

✔ Restart Outlook.

✔ Clear Outlook cache:

```text id="u2c8dv"
outlook /cleanprofile
```

✔ Verify internet connectivity.

✔ Determine whether the issue affects:

* A single user.
* Multiple users.

✔ Look for signs of a **Major Incident**.

> ⚠️ **Important**
>
> Widespread email failures may indicate a major incident requiring immediate escalation.

---

# Step 3 — Escalation to L2

**Objective:** Escalate unresolved incidents according to SLA requirements.

### Escalation Criteria

Escalate when:

```text id="7xk5pn"
L1 cannot resolve in 30 minutes
```

---

### Procedure

1. Update the ticket before escalation.

2. Add detailed notes including:

* Troubleshooting performed.
* Error messages.
* User impact.
* Current status.

3. L2 performs advanced checks:

| Check            | Tool / Location       |
| ---------------- | --------------------- |
| Mailbox Health   | Exchange Admin Center |
| Message Tracking | Message Trace         |
| Authentication   | MFA Status            |

4. Communicate with the user:

```text id="d1v8qk"
Ticket escalated, ETA 2 hours for resolution
```

> 💡 **Tip**
>
> Clear communication during escalation improves user confidence and reduces repeated follow-up requests.

---

# Step 4 — Resolution & Closure

**Objective:** Confirm service restoration and complete incident documentation.

### Procedure

1. Document:

* Root cause.
* Steps taken.
* Resolution applied.

2. Verify with the user:

```text id="x5m3pt"
Is Outlook working now? Can you send/receive emails?
```

3. Close the ticket with:

| Field          | Value                   |
| -------------- | ----------------------- |
| **Category**   | Email Issue             |
| **Resolution** | Outlook Profile Rebuilt |

4. Send closure confirmation to the user.

Include:

* Resolution summary.
* Incident reference number.
* Confirmation of service restoration.

> ✅ **Validation**
>
> The incident should only be closed after confirming that the user can successfully access the affected service.

---

# 🎯 Best Practice Tips

> **Important**

✔ Every incident must be logged—even if it is resolved within 5 minutes.

✔ Keep users updated proactively. Even a message such as **"still working on it"** improves user experience.

✔ Distinguish between:

| Type         | Purpose                                |
| ------------ | -------------------------------------- |
| **Incident** | Restore service as quickly as possible |
| **Problem**  | Identify and eliminate the root cause  |

✔ Use the priority matrix consistently:

* Escalate **P1 incidents immediately**.
* Never delay critical incident escalation.

---

# Incident Management Checklist

| Phase          | Completed Activity                            |
| -------------- | --------------------------------------------- |
| Identification | User issue reported and logged                |
| Categorization | Incident category and priority assigned       |
| Diagnosis      | L1 troubleshooting completed                  |
| Escalation     | L2 engaged when SLA threshold reached         |
| Resolution     | Fix applied and user verified                 |
| Closure        | Documentation completed and confirmation sent |

---

# Summary

In this lab, you completed the following tasks:

* Logged an IT service incident.
* Applied impact, urgency, and priority classification.
* Performed L1 troubleshooting and diagnosis.
* Escalated unresolved issues to L2 support.
* Documented root cause and resolution details.
* Closed incidents following ITIL best practices.

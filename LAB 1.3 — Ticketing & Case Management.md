# LAB 1.3 — Ticketing & Case Management

> **Lab Objective**
>
> Create, route, and resolve support cases using Microsoft Dynamics 365 Customer Service Hub.

---

# Learning Objectives

After completing this lab, you will be able to:

* Create a new support case.
* Use the Business Process Flow (BPF) to manage case progression.
* Route cases to queues.
* Resolve and close support cases.
* Apply Dynamics 365 case management best practices.

---

# Prerequisites

Before starting this lab, ensure you have:

* Access to the **Customer Service Hub**.
* Appropriate security permissions to create and manage cases.
* A customer (Contact or Account) available for case creation.
* Access to queues (or permission to create them).

---

# Lab Steps

## Step 1 — Create a New Case

**Objective:** Create a customer support case in Dynamics 365.

### Procedure

1. Open:

   **Customer Service Hub** → **Cases** → **+ New Case**

2. Complete the required information:

| Field          | Value                          |
| -------------- | ------------------------------ |
| **Case Title** | Enter an appropriate title     |
| **Customer**   | Search for or create a contact |
| **Origin**     | Email / Phone / Web            |
| **Priority**   | Normal / High                  |
| **Subject**    | IT Support                     |

3. Save the case.

4. Note the automatically generated **Case Number**.

Example:

```text
CAS-XXXXX
```

> 💡 **Tip**
>
> The Case Number uniquely identifies each support request and is commonly referenced during customer communications.

---

## Step 2 — Use the Business Process Flow

**Objective:** Track and manage the lifecycle of a support case.

### Procedure

1. Observe the **Business Process Flow (BPF)** displayed at the top of the case.

2. Review the available stages:

* Identify
* Research
* Resolve

3. Move the case to the **Research** stage.

4. Document findings in the **Notes/Timeline** section.

5. Add an activity:

* 📞 Phone Call
* 📧 Email to the customer regarding the status update

> ℹ️ **Note**
>
> The Business Process Flow provides a guided process to help ensure consistent case handling.

---

## Step 3 — Route the Case to a Queue

**Objective:** Assign the case to the appropriate support queue.

### Procedure

1. Click **Add to Queue**.

2. Select:

```text
L2 Support Queue
```

3. If a queue does not already exist, create one by navigating to:

**Settings** → **Service Management** → **Queues** → **+ New**

4. Assign queue items by using one of the following approaches:

* Assign to a specific support agent.
* Allow support agents to **Pick** cases from the queue.

> 💡 **Tip**
>
> Queues help distribute workload efficiently across support teams.

---

## Step 4 — Resolve & Close the Case

**Objective:** Complete the support process by resolving the case.

### Procedure

1. Click **Resolve Case**.

2. Enter the following resolution:

```text
Issue resolved — driver updated
```

3. Specify:

* Billable Time
* Total Time Spent

4. Save the resolution.

5. Verify that:

* The case moves to **Resolved** status.
* The customer receives an automatic email notification (if configured).

> ✅ **Validation**
>
> Confirm that the case status is **Resolved** and the resolution details are recorded in the Timeline.

---

# 🎯 Best Practice Tips

> **Important**

✔ Always log every action in the **Timeline** to maintain a complete audit trail.

✔ Use **Quick Create** forms to rapidly log cases during customer phone calls.

✔ Configure **Routing Rule Sets** to automate queue assignments and reduce manual effort.

✔ Monitor **SLA timers** displayed on the case:

| SLA Status   | Indicator |
| ------------ | --------- |
| **Warning**  | 🟡 Yellow |
| **Violated** | 🔴 Red    |

Prompt action before SLA violations helps maintain service quality and customer satisfaction.

---

# Summary

In this lab, you completed the following tasks:

* Created a new customer support case.
* Used the Business Process Flow to progress the case through its lifecycle.
* Documented activities and updates in the Timeline.
* Routed the case to an appropriate support queue.
* Resolved and closed the case.
* Reviewed Dynamics 365 Customer Service case management best practices.

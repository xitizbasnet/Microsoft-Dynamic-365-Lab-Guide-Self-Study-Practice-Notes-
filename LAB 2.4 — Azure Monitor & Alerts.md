# LAB 2.4 — Azure Monitor & Alerts

> **Lab Objective**
>
> Set up monitoring, create alerts, and view diagnostic logs for Azure resources.

---

# Learning Objectives

After completing this lab, you will be able to:

* Enable diagnostic settings for Azure Virtual Machines.
* Create Azure Monitor alert rules.
* View performance metrics in Azure Monitor.
* Query logs using Kusto Query Language (KQL).
* Apply Azure monitoring and alerting best practices.

---

# Prerequisites

Before starting this lab, ensure you have:

* An active Azure subscription.
* A deployed Azure Virtual Machine.
* Access to Azure Monitor.
* A Log Analytics Workspace.
* Permissions to configure monitoring and alerts.

---

# Lab Steps

## Step 1 — Enable Diagnostics on a Virtual Machine

**Objective:** Enable guest-level monitoring and collect diagnostic data.

### Procedure

1. Open the Azure Virtual Machine.

2. Navigate to:

   **Diagnostic Settings**

3. Enable **Guest-Level Monitoring**.

4. Select the following data sources:

| Diagnostic Setting       | Selection           |
| ------------------------ | ------------------- |
| **Performance Counters** | Enabled             |
| **Event Logs**           | System, Application |

5. Select or create a **Storage Account**.

6. Click **Save**.

> 💡 **Tip**
>
> Guest-level diagnostics provide valuable operating system performance and event log data that can be used for troubleshooting and monitoring.

---

## Step 2 — Create a CPU Alert

**Objective:** Configure an alert that triggers when CPU utilization exceeds a defined threshold.

### Procedure

1. Navigate to:

   **Monitor** → **Alerts**

2. Click:

   **+ Create** → **Alert Rule**

3. Configure the alert rule:

| Setting       | Value                              |
| ------------- | ---------------------------------- |
| **Scope**     | Select your Virtual Machine        |
| **Condition** | Percentage CPU > 80% for 5 minutes |

4. Create an **Action Group**.

| Setting               | Value    |
| --------------------- | -------- |
| **Action Group Name** | AlertOps |

5. Configure notifications:

* Email
* SMS

6. Enter your notification address.

7. Click **Create Alert Rule**.

> ⚠️ **Important**
>
> Alerts enable administrators to respond quickly to performance issues before they affect users or workloads.

---

## Step 3 — View Metrics in Azure Monitor

**Objective:** Analyze Virtual Machine performance metrics.

### Procedure

1. Navigate to:

   **Monitor** → **Metrics**

2. Select the target Virtual Machine.

3. Configure the metric:

| Setting         | Value          |
| --------------- | -------------- |
| **Metric**      | Percentage CPU |
| **Aggregation** | Average        |
| **Timeframe**   | Last 24 Hours  |

4. Review the performance chart.

5. Pin the chart to the Azure Dashboard for quick daily visibility.

> 💡 **Tip**
>
> Pinning commonly used metrics to the Azure Dashboard allows administrators to monitor resource health without repeatedly navigating through the portal.

---

## Step 4 — Query Logs with Kusto Query Language (KQL)

**Objective:** Analyze monitoring data using Log Analytics queries.

### Procedure

1. Navigate to:

   **Monitor** → **Logs**

2. Select your **Log Analytics Workspace**.

3. Execute the following KQL queries.

### Heartbeat Summary

```kusto id="h8p7qf"
Heartbeat
| where TimeGenerated > ago(24h)
| summarize count() by Computer
```

### Error Events

```kusto id="p6n5ax"
Event
| where EventLevelName == "Error"
| take 50
```

### Delete Operations

```kusto id="36k2gb"
AzureActivity
| where OperationName contains "delete"
| take 20
```

> ℹ️ **Note**
>
> Kusto Query Language (KQL) enables administrators to search, analyze, and troubleshoot Azure resources by querying collected telemetry and log data.

---

# 📊 Best Practice Tips

> **Important**

✔ Configure monitoring and alert rules **before** issues occur. Reactive monitoring alone is often too late to prevent service impact.

✔ Use **Azure Monitor Workbooks** to build rich, interactive dashboards using metrics and Log Analytics data.

✔ The default **Log Analytics retention period** is **30 days**. Increase the retention period where required to meet organizational or regulatory compliance requirements.

✔ Assign alert **severity levels (Sev0–Sev4)** and route notifications to the appropriate operations or support team queue.

---

# Validation Checklist

| Task                      | Expected Result                               |
| ------------------------- | --------------------------------------------- |
| Guest diagnostics enabled | Performance counters and event logs collected |
| CPU alert created         | Alert rule configured with Action Group       |
| Metrics reviewed          | CPU utilization chart displayed               |
| Dashboard updated         | Metric pinned successfully                    |
| KQL queries executed      | Log results returned from Log Analytics       |

---

# Summary

In this lab, you completed the following tasks:

* Enabled guest-level diagnostics for an Azure Virtual Machine.
* Created an Azure Monitor CPU alert rule.
* Reviewed performance metrics using Azure Monitor.
* Queried diagnostic logs using Kusto Query Language (KQL).
* Reviewed Azure monitoring, logging, and alerting best practices.

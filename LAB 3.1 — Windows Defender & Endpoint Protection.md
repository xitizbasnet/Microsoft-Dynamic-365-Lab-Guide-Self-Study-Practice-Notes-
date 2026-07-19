# LAB 3.1 — Windows Defender & Endpoint Protection

> **Lab Objective**
>
> Configure Windows Defender, run antivirus scans, and review Windows security events.

---

# Learning Objectives

After completing this lab, you will be able to:

* Navigate the Windows Security Center.
* Update Microsoft Defender Antivirus definitions.
* Perform Quick and Full antivirus scans.
* Manage Microsoft Defender using PowerShell.
* Review Windows Security Event Logs.
* Identify common security-related Event IDs.
* Apply endpoint protection best practices.

---

# Prerequisites

Before starting this lab, ensure you have:

* A Windows 10 or Windows 11 device (or Windows Server with Microsoft Defender enabled).
* Local Administrator privileges.
* Windows Security (Microsoft Defender Antivirus) enabled.
* Windows PowerShell access.
* Event Viewer available.

---

# Lab Steps

## Step 1 — Open Windows Security Center

**Objective:** Verify that Microsoft Defender Antivirus is healthy and up to date.

### Procedure

1. Open:

   **Start** → **Windows Security**

2. Review all protection areas.

> 🟢 **Healthy Status**
>
> A green indicator signifies that the protection area is operating normally.

3. Navigate to:

   **Virus & Threat Protection** → **Protection Updates**

4. Update Microsoft Defender security definitions.

5. Verify that the following protection features are enabled:

| Protection Feature             | Status |
| ------------------------------ | ------ |
| **Real-time Protection**       | ON     |
| **Cloud-delivered Protection** | ON     |
| **Tamper Protection**          | ON     |

> 💡 **Tip**
>
> Keeping security definitions updated ensures Microsoft Defender can detect the latest malware and threats.

---

## Step 2 — Run a Full Antivirus Scan

**Objective:** Scan the system for malware and review previous detections.

### Procedure

1. Navigate to:

   **Windows Security** → **Virus & Threat Protection** → **Scan Options**

2. Select:

   **Full Scan**

3. Click:

   **Scan Now**

> ℹ️ **Note**
>
> A Full Scan may require **30–60 minutes** on physical hardware, depending on system performance and disk size.

4. For a faster inspection, select:

   **Quick Scan**

> Quick Scan focuses on common malware locations.

5. Review:

   **Protection History**

6. Examine previously detected threats and remediation actions.

---

## Step 3 — Configure Microsoft Defender via PowerShell

**Objective:** Manage Microsoft Defender Antivirus using PowerShell.

### View Defender Status

```powershell id="2wkmjy"
Get-MpComputerStatus
```

### Update Security Signatures

```powershell id="vx0wgr"
Update-MpSignature
```

### Start a Quick Scan

```powershell id="ncd4j3"
Start-MpScan -ScanType QuickScan
```

### View Detected Threats

```powershell id="jlwmad"
Get-MpThreatDetection
```

> 💡 **Tip**
>
> PowerShell provides an efficient way to automate Microsoft Defender administration across multiple systems.

---

## Step 4 — Review Windows Event Logs for Security Events

**Objective:** Analyze Windows Security logs for authentication and account management events.

### Procedure

1. Open:

   **Event Viewer**

2. Navigate to:

   **Windows Logs** → **Security**

3. Review the following commonly used Security Event IDs:

| Event ID | Description                      |
| -------- | -------------------------------- |
| **4624** | Successful Logon                 |
| **4625** | Failed Logon                     |
| **4648** | Logon Using Explicit Credentials |
| **4720** | User Account Created             |

4. Filter the Security log.

Navigate to:

**Action** → **Filter Current Log**

5. Enter:

```text
Event ID: 4625
```

6. Review failed logon events for signs of brute-force attack patterns.

> ⚠️ **Important**
>
> Repeated failed logon attempts from the same account or source may indicate unauthorized access attempts.

---

# 🛡️ Best Practice Tips

> **Important**

✔ Keep Microsoft Defender Antivirus definitions updated **daily**. Use **Windows Server Update Services (WSUS)** or **Microsoft Intune** to manage updates in enterprise environments.

✔ Microsoft Defender **Exclusions** should always be documented, reviewed, and formally approved. Unauthorized exclusions can introduce significant security risks.

✔ A sudden increase in **Event ID 4625 (Failed Logon)** events may indicate a brute-force attack and should be escalated immediately for investigation.

✔ **Microsoft Defender for Endpoint (MDE)** extends Microsoft Defender Antivirus with enterprise-grade **Endpoint Detection and Response (EDR)** capabilities for advanced threat detection and response.

---

# Validation Checklist

| Task                         | Expected Result                                       |
| ---------------------------- | ----------------------------------------------------- |
| Windows Security reviewed    | All protection areas show healthy status              |
| Security definitions updated | Latest protection updates installed                   |
| Antivirus scan completed     | Scan finishes without critical issues                 |
| PowerShell commands executed | Defender status and scan information displayed        |
| Event Viewer reviewed        | Security Event IDs successfully filtered and analyzed |

---

# Summary

In this lab, you completed the following tasks:

* Reviewed Microsoft Defender Antivirus protection status.
* Updated antivirus security definitions.
* Performed Quick and Full system scans.
* Managed Microsoft Defender using PowerShell.
* Investigated Windows Security Event Logs.
* Reviewed endpoint protection and security monitoring best practices.

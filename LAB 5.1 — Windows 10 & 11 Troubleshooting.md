# LAB 5.1 — Windows 10 & 11 Troubleshooting

> **Lab Objective**
>
> Diagnose and fix common Windows 10/11 issues using built-in troubleshooting tools and administrative utilities.

---

# Learning Objectives

After completing this lab, you will be able to:

* Diagnose Windows performance issues.
* Troubleshoot Windows startup and boot failures.
* Identify and resolve driver-related problems.
* Repair Windows Update failures.
* Use built-in Windows troubleshooting utilities.
* Apply professional troubleshooting documentation practices.

---

# Prerequisites

Before starting this lab, ensure you have:

* A Windows 10 or Windows 11 workstation.
* Local administrator permissions.
* Access to PowerShell and Command Prompt.
* Basic understanding of Windows administration tools.

---

# Windows Troubleshooting Methodology

A structured troubleshooting approach should follow:

1. **Identify the issue**
2. **Collect information**
3. **Analyze symptoms**
4. **Apply corrective action**
5. **Verify resolution**
6. **Document the solution**

---

# Lab Steps

## Step 1 — System Performance Issues (High CPU/RAM)

**Objective:** Identify processes consuming excessive system resources.

---

## Using Task Manager

### Procedure

1. Open Task Manager:

```text id="4x9mkt"
Ctrl + Shift + Esc
```

2. Navigate to:

```text id="m6q2vp"
Processes tab
```

3. Sort processes by:

* CPU usage.
* Memory usage.

4. Identify high-resource processes.

5. Right-click the process and select:

* **Search Online**
* **End Task**

---

## Using Resource Monitor

1. Open:

```text id="w3n8qa"
Performance tab → Open Resource Monitor
```

2. Use Resource Monitor for deeper analysis of:

* CPU usage.
* Memory consumption.
* Disk activity.
* Network utilization.

---

## PowerShell Performance Check

Run:

```powershell
Get-Process | Sort-Object CPU -Descending | Select-Object -First 10
```

This command displays the top 10 processes sorted by CPU consumption.

---

# Step 2 — Windows Won't Boot — Safe Mode Diagnostics

**Objective:** Start Windows in Safe Mode and diagnose startup problems.

---

## Enter Windows Recovery Environment (WinRE)

### Procedure

1. Force restart the computer three times.

2. Windows automatically enters:

```text id="v8c5zr"
Windows Recovery Environment (WinRE)
```

3. Navigate to:

```text id="r7m2kx"
Troubleshoot → Advanced Options → Startup Settings → Restart
```

4. Select:

```text id="k9p4ws"
F4 — Safe Mode
```

---

## Safe Mode Diagnostics

In Safe Mode:

1. Run System File Checker:

```cmd
sfc /scannow
```

2. Review Event Viewer for boot errors.

---

## Windows Repair Commands

### System File Checker

```cmd
sfc /scannow
```

Purpose:

```text id="c6v8qm"
System File Checker
```

Repairs corrupted Windows system files.

---

### DISM Windows Image Repair

```cmd
DISM /Online /Cleanup-Image /RestoreHealth
```

Purpose:

```text id="h5q1px"
Repair Windows image
```

---

# Step 3 — Driver Issues — Device Manager

**Objective:** Identify and repair hardware driver problems.

---

## Procedure

1. Open Device Manager:

```text id="p8r3md"
Right-click Start → Device Manager
```

2. Look for:

```text id="z4m7vk"
Yellow ! warning icons
```

These indicate possible driver issues.

---

## Update Driver

1. Right-click the affected device.

2. Select:

```text id="t6x9qa"
Update Driver → Search Automatically
```

---

## Manual Driver Installation

If automatic installation fails:

1. Visit the manufacturer website.

2. Download the correct driver.

3. Install manually.

---

## Roll Back Driver

If a recent driver update caused issues:

Navigate to:

```text id="b2n5kc"
Device Properties → Driver tab → Roll Back Driver
```

> 💡 **Tip**
>
> Driver rollback is useful when hardware problems begin immediately after a driver update.

---

# Step 4 — Windows Update Troubleshooting

**Objective:** Resolve common Windows Update failures.

---

## Check Windows Update Status

Navigate to:

```text id="q8w3hf"
Settings → Windows Update
```

Review errors such as:

```text id="m4r9yd"
0x800F081F
```

---

## Run Windows Update Troubleshooter

Navigate to:

```text id="x2k7pv"
Settings → Troubleshoot → Other Troubleshooters
```

Run:

```text id="d5m8qa"
Windows Update Troubleshooter
```

---

## Reset Windows Update Components

Run the following commands:

```cmd
net stop wuauserv
net stop bits
rd /s /q C:\Windows\SoftwareDistribution\Download
net start wuauserv && net start bits
```

These commands:

* Stop Windows Update services.
* Stop Background Intelligent Transfer Service (BITS).
* Clear corrupted update download files.
* Restart update services.

---

# 🔧 Best Practice Tips

> **Important**

✔ Document every troubleshooting step.

If the issue occurs again, documentation provides a troubleshooting baseline.

✔ Always create a System Restore point before making significant changes.

✔ Check Windows Event Viewer:

```text id="n7q4kc"
System + Application logs
```

before using additional troubleshooting tools.

✔ Use Reliability Monitor:

```text id="j3m6wt"
reliabmonitor.exe
```

to view a timeline of recent system failures.

---

# Troubleshooting Checklist

| Area              | Tool / Action        | Expected Result                     |
| ----------------- | -------------------- | ----------------------------------- |
| Performance       | Task Manager         | High CPU/RAM processes identified   |
| Advanced Analysis | Resource Monitor     | Detailed resource usage reviewed    |
| Boot Issues       | Safe Mode            | Windows starts with minimal drivers |
| System Files      | SFC / DISM           | Corrupted files repaired            |
| Drivers           | Device Manager       | Driver issues resolved              |
| Updates           | Windows Update Tools | Update errors corrected             |

---

# Summary

In this lab, you completed the following tasks:

* Diagnosed Windows performance problems.
* Used Task Manager and Resource Monitor for analysis.
* Booted Windows into Safe Mode for troubleshooting.
* Repaired system files using SFC and DISM.
* Updated and rolled back device drivers.
* Resolved Windows Update issues.
* Applied Windows troubleshooting best practices.

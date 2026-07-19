# LAB 5.3 — Office 365 & Outlook Issues

> **Lab Objective**
>
> Troubleshoot common Office 365 and Outlook problems end-to-end using Microsoft 365 administration tools and built-in troubleshooting methods.

---

# Learning Objectives

After completing this lab, you will be able to:

* Diagnose Outlook startup and performance issues.
* Troubleshoot email sending and synchronization failures.
* Resolve OneDrive and SharePoint synchronization problems.
* Troubleshoot Microsoft Teams loading and audio issues.
* Use Microsoft 365 diagnostic tools.
* Apply Office 365 troubleshooting best practices.

---

# Prerequisites

Before starting this lab, ensure you have:

* A Microsoft 365 user account.
* Microsoft Outlook installed.
* Access to Microsoft 365 services:

  * Exchange Online.
  * OneDrive.
  * SharePoint Online.
  * Microsoft Teams.
* Basic understanding of Microsoft 365 administration.

---

# Microsoft 365 Troubleshooting Methodology

A structured troubleshooting approach should follow:

1. **Identify the affected service**
2. **Determine client-side vs server-side impact**
3. **Test using alternative access methods**
4. **Apply corrective actions**
5. **Verify service restoration**
6. **Document the resolution**

---

# Lab Steps

## Step 1 — Outlook Not Launching / Crashing

**Objective:** Diagnose and resolve Outlook startup failures.

---

## Launch Outlook in Safe Mode

### Procedure

1. Open Run:

```text id="8q4mxp"
Start → Run
```

2. Execute:

```cmd id="m7v2qc"
outlook /safe
```

---

## Identify Faulty Add-ins

If Outlook works in Safe Mode:

1. A faulty add-in is likely causing the issue.

2. Navigate to:

```text id="v3n8ka"
File → Options → Add-ins
```

3. Disable all add-ins.

4. Restart Outlook normally.

> 💡 **Tip**
>
> Safe Mode starts Outlook without most customizations and add-ins, helping isolate application-level issues.

---

## Repair Microsoft 365 Installation

### Procedure

Navigate to:

```text id="x5k9rm"
Control Panel → Programs → Microsoft 365 → Change
```

Select:

```text id="q2m7vd"
Quick Repair
```

---

## Rebuild Outlook Profile

If the issue continues:

Navigate to:

```text id="r6p3wy"
Control Panel → Mail → Show Profiles
```

Then:

1. Select:

```text id="h8q4nk"
Add new profile
```

2. Configure the account again.

---

# Step 2 — Email Not Sending / Stuck in Outbox

**Objective:** Resolve Outlook email delivery problems.

---

## Check Work Offline Status

### Procedure

1. Open Outlook.

2. Navigate to:

```text id="z3m6qa"
Send/Receive tab
```

3. Verify:

```text id="k7v2px"
Work Offline = OFF
```

---

## Clear Stuck Messages

Procedure:

1. Delete the stuck email from:

```text id="w4n8mc"
Outbox
```

2. Restart Outlook.

3. Re-compose and send the message.

---

## Check Message Trace

Navigate to:

```text id="p9x5mv"
Microsoft 365 Admin → Exchange Admin → Mail Flow → Message Trace
```

Review:

* Message delivery status.
* Mail flow errors.
* Recipient issues.

---

## Test Using Outlook Web Access (OWA)

Access:

```text id="n6q2kr"
outlook.office.com
```

Validation:

* If OWA works:

  * The issue is likely with the local Outlook client.

* If OWA fails:

  * Investigate Exchange Online or account issues.

> 💡 **Tip**
>
> OWA is a fast method to determine whether an issue is caused by Outlook locally or by Microsoft 365 services.

---

# Step 3 — OneDrive & SharePoint Sync Issues

**Objective:** Troubleshoot file synchronization problems.

---

## Check OneDrive Sync Problems

### Procedure

1. Open the OneDrive icon:

```text id="t5m8qw"
Taskbar → OneDrive cloud icon
```

2. Right-click.

3. Select:

```text id="c4n7xp"
View Sync Problems
```

---

## Common OneDrive Fixes

### Option 1 — Pause and Resume Sync

Procedure:

1. Pause synchronization.
2. Resume synchronization.

---

### Option 2 — Reconnect OneDrive

Procedure:

1. Unlink the PC.

2. Sign in again.

---

## Reset OneDrive

Run:

```cmd id="y8p4mk"
Win+R → %localappdata%\Microsoft\OneDrive\onedrive.exe /reset
```

---

## SharePoint Synchronization Limits

Important limits:

| Setting              | Limit                    |
| -------------------- | ------------------------ |
| Maximum synced items | 300,000 items            |
| Maximum file size    | 250 GB                   |
| Maximum path length  | Less than 400 characters |

---

# Step 4 — Teams Not Loading / Audio Issues

**Objective:** Troubleshoot Microsoft Teams application and meeting issues.

---

## Clear Teams Cache

### Procedure

1. Close Microsoft Teams.

2. Navigate to:

```text id="b7q3nx"
%appdata%\Microsoft\Teams
```

3. Delete:

* Cache
* blob_storage
* databases

4. Restart Teams.

---

## Troubleshoot Audio Devices

Navigate to:

```text id="m9r5kp"
Teams → Settings → Devices
```

Verify:

* Correct speaker selected.
* Correct microphone selected.

---

## Check Network Requirements

Microsoft Teams requires:

```text id="q6w8mt"
UDP 3478-3481 outbound
```

Verify:

* Firewall rules.
* Network restrictions.

---

## Test Meeting Audio

Navigate to:

```text id="d2v7qa"
Teams Settings → Devices → Make a test call
```

Confirm:

* Microphone works.
* Speaker works.
* Audio quality is acceptable.

---

# 🔧 Best Practice Tips

> **Important**

✔ OWA is your best diagnostic tool.

It helps isolate:

* Client issues.
* Server-side issues.

within seconds.

---

✔ Keep Office applications updated.

Most Outlook issues are resolved through:

* Monthly channel updates.
* Microsoft application fixes.

---

✔ Use OneDrive selective sync.

Only synchronize required folders to:

* Reduce local disk usage.
* Improve synchronization performance.

---

✔ Use:

```text id="x9m4pk"
Microsoft Support and Recovery Assistant (SaRA)
```

for automated Microsoft 365 diagnostics.

---

# Troubleshooting Checklist

| Issue Area     | Diagnostic Action  | Expected Result              |
| -------------- | ------------------ | ---------------------------- |
| Outlook Launch | Safe Mode test     | Add-in issues identified     |
| Office Repair  | Quick Repair       | Application repaired         |
| Email Delivery | Message Trace      | Mail flow verified           |
| OWA Testing    | Browser validation | Client/server issue isolated |
| OneDrive       | Sync diagnostics   | Synchronization restored     |
| Teams Audio    | Test Call          | Audio devices verified       |

---

# Summary

In this lab, you completed the following tasks:

* Troubleshot Outlook startup and crash issues.
* Used Safe Mode and add-in isolation techniques.
* Repaired Microsoft 365 applications.
* Rebuilt Outlook profiles.
* Diagnosed email delivery problems.
* Troubleshot OneDrive and SharePoint synchronization.
* Resolved Microsoft Teams loading and audio issues.
* Applied Microsoft 365 support best practices.

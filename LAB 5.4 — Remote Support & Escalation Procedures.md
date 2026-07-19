# LAB 5.4 — Remote Support & Escalation Procedures

> **Lab Objective**
>
> Provide effective remote desktop support and handle escalations professionally using approved remote access tools and IT support procedures.

---

# Learning Objectives

After completing this lab, you will be able to:

* Understand common remote support tools.
* Enable and use Remote Desktop services.
* Perform secure remote troubleshooting.
* Follow professional remote support etiquette.
* Create effective escalation notes.
* Communicate incidents clearly between support levels.

---

# Prerequisites

Before starting this lab, ensure you have:

* Windows 10/11 workstation access.
* Appropriate remote access permissions.
* Knowledge of IT support ticketing procedures.
* Understanding of L1/L2/L3 escalation processes.

---

# Remote Support Overview

Remote support allows IT teams to:

* Troubleshoot user issues without physical presence.
* Reduce resolution time.
* Provide faster assistance to distributed users.
* Collaborate between support teams.

A successful remote support session requires:

* User communication.
* Permission before access.
* Clear documentation.
* Secure handling of credentials and data.

---

# Lab Steps

## Step 1 — Remote Desktop Tools Overview

**Objective:** Understand available remote support technologies.

---

## Microsoft Quick Assist

**Built-in Windows 10/11 remote assistance tool.**

### Procedure

1. Open:

```text id="7m4qxv"
Start → Quick Assist
```

2. Select:

```text id="k8p2mr"
Give assistance
```

3. Provide the assistance code to the user.

> 💡 **Tip**
>
> Quick Assist is recommended for Microsoft 365 environments because it does not require additional software installation.

---

## TeamViewer

### Procedure

Access:

```text id="n5w8kp"
remote.teamviewer.com
```

Required information:

* User ID.
* Password.

Requirement:

* User must install the TeamViewer agent.

---

## Azure Virtual Desktop

Used for:

* Session-based remote desktop access.
* Cloud-hosted Windows environments.
* Remote user productivity scenarios.

Access:

```text id="r3m7qa"
Azure portal
```

---

## Remote Desktop Protocol (RDP)

### Procedure

Launch:

```text id="m6q9vx"
mstsc.exe
```

Enter:

* Target IP address.
* Hostname.

Connect using:

* Domain credentials.

---

# Step 2 — Enable & Use Remote Desktop

**Objective:** Configure and connect to a Windows device using Remote Desktop.

---

## Enable Remote Desktop

### On the Target PC:

Navigate to:

```text id="q4n8mc"
Settings → System → Remote Desktop
```

Enable:

```text id="x7p2kd"
Remote Desktop
```

Requirement:

* Windows Pro or Enterprise edition.

---

## Firewall Requirements

Remote Desktop requires:

```text id="c9m5wr"
TCP 3389 inbound
```

Alternative:

Use Quick Assist:

```text id="v6q8mp"
HTTPS 443
```

---

## PowerShell Remoting

### Enable PowerShell Remoting

```powershell id="a4n7kx"
Enable-PSRemoting -Force
```

Purpose:

* Enables Windows Remote Management (WinRM).

---

### Connect to Remote Computer

```powershell id="t3m8qp"
Enter-PSSession -ComputerName PC-DUBAI-01 -Credential domain\admin
```

Purpose:

* Creates a remote PowerShell session.

---

# Step 3 — Remote Troubleshooting Best Practices

**Objective:** Provide professional and transparent remote assistance.

---

## Communicate During the Session

Always explain your actions.

Example:

```text id="p8r5mq"
I'm now checking Event Viewer for errors
```

---

## Maintain User Confidence

Follow these guidelines:

✔ Never work in silence.

The user may think:

* The session disconnected.
* The technician is no longer working.

---

✔ Ask permission before accessing:

* Personal files.
* Desktop contents.

---

✔ End the Session Correctly:

1. Disconnect cleanly.
2. Confirm the user has control back.

---

# Step 4 — Escalation Procedure Template

**Objective:** Provide complete information when transferring issues to another support team.

---

## Escalation Note Format

Use the following structure:

```text id="y7k3mp"
[Ticket ID] | [User] | [Issue Summary] | [Steps taken] | [Reason for escalation] | [Urgency]
```

---

## Example Escalation Note

```text id="w5m9qx"
INC-1052 | Ali Al Rashidi | Outlook crashing on startup | Tried safe mode, profile rebuild — no fix | Possible Exchange mailbox corruption | P2 – escalate to Exchange team
```

---

## Escalation Communication Requirements

Always:

✔ Verbally brief the L2 engineer.

In addition to:

✔ Providing written ticket notes.

---

## Follow-Up Procedure

After escalation:

Wait 1 hour and follow up:

```text id="z4n8kc"
Has L2 contacted the user?
```

---

# 🔐 Best Practice Tips

> **Important**

✔ Follow remote support etiquette.

Always ask:

```text id="h6q2mv"
Is it okay if I take control of your screen?
```

before accessing the user's device.

---

✔ Document all remote session actions in the ticket.

This applies even when:

* The user watches the troubleshooting process.
* The issue is resolved quickly.

---

✔ Prefer Quick Assist in Microsoft 365 environments.

Benefits:

* Built into Windows 10/11.
* No additional software required.

---

✔ For sensitive roles such as:

* Finance.
* HR.

Obtain explicit manager approval before remote access.

---

# Remote Support Checklist

| Activity                  | Expected Result                  |
| ------------------------- | -------------------------------- |
| Remote tool selected      | Approved tool used               |
| User permission obtained  | Remote session authorized        |
| Troubleshooting explained | User understands actions         |
| Session documented        | Ticket contains complete history |
| Escalation completed      | L2 receives required information |
| Follow-up performed       | User communication maintained    |

---

# Summary

In this lab, you completed the following tasks:

* Reviewed remote support technologies.
* Used Quick Assist, TeamViewer, Azure Virtual Desktop, and RDP concepts.
* Enabled and configured Remote Desktop.
* Used PowerShell Remoting.
* Applied professional remote troubleshooting practices.
* Created structured escalation notes.
* Followed remote support security and communication guidelines.

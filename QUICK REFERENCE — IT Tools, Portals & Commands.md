# QUICK REFERENCE — IT Tools, Portals & Commands

> **Purpose**
>
> This quick reference provides a centralized list of commonly used IT administration tools, Microsoft portals, support platforms, and essential commands used throughout the labs.

---

# Tools, Portals & Commands Reference

## Administration & Support Tools

| Area                | Key Tool / Portal                   | Purpose                              |
| ------------------- | ----------------------------------- | ------------------------------------ |
| **Dynamics 365**    | `admin.powerplatform.microsoft.com` | D365 Admin Center                    |
| **Dynamics 365**    | Customer Service Hub (in D365)      | Case & Ticket Management             |
| **Azure**           | `portal.azure.com`                  | Azure Resource Management            |
| **Azure**           | Azure Cloud Shell                   | CLI: `az` commands                   |
| **Azure AD**        | `aad.portal.azure.com`              | User, Group, Role Management         |
| **Security**        | `security.microsoft.com`            | M365 Defender Portal                 |
| **Security**        | `compliance.microsoft.com`          | DLP, Audit, Purview                  |
| **ITIL / Tickets**  | `developer.servicenow.com`          | Free ServiceNow Practice Environment |
| **Office 365**      | `outlook.office.com` (OWA)          | Browser-based Outlook                |
| **Office 365**      | `admin.microsoft.com`               | M365 Admin Center                    |
| **Desktop Support** | Quick Assist (Windows built-in)     | Remote Support Tool                  |
| **Desktop Support** | `mstsc.exe`                         | Remote Desktop Protocol              |

---

# Portal Quick Access Guide

## Dynamics 365 Administration

| Portal                              | Usage                                                              |
| ----------------------------------- | ------------------------------------------------------------------ |
| `admin.powerplatform.microsoft.com` | Manage Dynamics 365 environments, users, permissions, and settings |

Common tasks:

* Environment management.
* User administration.
* Security role assignment.
* Power Platform administration.

---

## Azure Administration

| Portal             | Usage                  |
| ------------------ | ---------------------- |
| `portal.azure.com` | Manage Azure resources |

Common tasks:

* Create resource groups.
* Deploy virtual machines.
* Configure monitoring.
* Manage subscriptions.

---

## Azure Cloud Shell

Tool:

```text
Azure Cloud Shell
```

Purpose:

* Execute Azure CLI commands.
* Manage Azure resources from the browser.

Example:

```bash
az group list --output table
```

---

## Azure Active Directory Administration

Portal:

```text
aad.portal.azure.com
```

Purpose:

* User management.
* Group management.
* Role assignment.

Common tasks:

* Create users.
* Manage security groups.
* Assign administrative roles.

---

# Security Administration Portals

## Microsoft Defender Portal

Portal:

```text
security.microsoft.com
```

Purpose:

* Security monitoring.
* Incident investigation.
* Threat response.

---

## Microsoft Purview Compliance Portal

Portal:

```text
compliance.microsoft.com
```

Purpose:

* Data Loss Prevention (DLP).
* Audit logging.
* Compliance management.

---

# IT Service Management Tools

## ServiceNow Developer Environment

Portal:

```text
developer.servicenow.com
```

Purpose:

* Free ServiceNow practice environment.

Common tasks:

* Incident creation.
* Ticket management.
* Workflow testing.

---

# Microsoft 365 Tools

## Outlook Web Access (OWA)

Portal:

```text
outlook.office.com
```

Purpose:

* Browser-based Outlook access.
* Email troubleshooting.
* Client vs server issue isolation.

---

## Microsoft 365 Admin Center

Portal:

```text
admin.microsoft.com
```

Purpose:

* Microsoft 365 administration.

Common tasks:

* User management.
* License assignment.
* Service configuration.

---

# Desktop Support Tools

## Quick Assist

Platform:

```text
Windows Built-in
```

Purpose:

* Remote user assistance.
* Screen sharing.
* Remote troubleshooting.

---

## Remote Desktop Protocol (RDP)

Command:

```cmd
mstsc.exe
```

Purpose:

* Connect to remote Windows systems.

Common usage:

* Server administration.
* Remote workstation support.

---

# Certification Path Recommendation

Recommended learning and certification path:

```text
MD-102 (Endpoint Administrator)
        ↓
MS-900 (M365 Fundamentals)
        ↓
AZ-900 (Azure Fundamentals)
        ↓
MB-230 (Dynamics 365 Customer Service)
        ↓
ITIL 4 Foundation
```

---

# Certification Overview

| Certification                              | Focus Area                                        |
| ------------------------------------------ | ------------------------------------------------- |
| **MD-102 — Endpoint Administrator**        | Windows devices, Intune, endpoint management      |
| **MS-900 — Microsoft 365 Fundamentals**    | Microsoft 365 services and cloud concepts         |
| **AZ-900 — Azure Fundamentals**            | Azure concepts, services, and cloud foundations   |
| **MB-230 — Dynamics 365 Customer Service** | Customer service applications and case management |
| **ITIL 4 Foundation**                      | IT service management principles and practices    |

---

# Quick Command Reference

| Command                                      | Purpose                            |
| -------------------------------------------- | ---------------------------------- |
| `mstsc.exe`                                  | Launch Remote Desktop Connection   |
| `az` commands                                | Manage Azure resources through CLI |
| `gpupdate /force`                            | Refresh Group Policy settings      |
| `gpresult /r`                                | View applied Group Policies        |
| `sfc /scannow`                               | Repair Windows system files        |
| `DISM /Online /Cleanup-Image /RestoreHealth` | Repair Windows image               |
| `outlook /safe`                              | Launch Outlook in Safe Mode        |

---

# Summary

This quick reference provides a central location for:

* Microsoft administration portals.
* IT support tools.
* Cloud management platforms.
* Security portals.
* Remote support utilities.
* Common troubleshooting commands.
* Recommended certification progression.

Use this guide as a daily reference while performing Microsoft 365, Azure, Dynamics 365, Windows administration, and IT service management activities.

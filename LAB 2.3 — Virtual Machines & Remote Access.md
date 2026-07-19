# LAB 2.3 — Virtual Machines & Remote Access

> **Lab Objective**
>
> Deploy a Windows Virtual Machine (VM) in Microsoft Azure and connect to it using Remote Desktop Protocol (RDP).

---

# Learning Objectives

After completing this lab, you will be able to:

* Deploy a Windows Virtual Machine in Azure.
* Configure basic networking for a VM.
* Connect to the VM using Remote Desktop (RDP).
* Configure Azure Bastion for secure remote access.
* Start and stop Azure Virtual Machines using Azure CLI.
* Apply Azure Virtual Machine security best practices.

---

# Prerequisites

Before starting this lab, ensure you have:

* An active Azure subscription.
* A Resource Group (for example, **RG-Dubai-IT**).
* Permission to create Azure Virtual Machines.
* A Remote Desktop (RDP) client installed on your local computer.
* Azure CLI access (optional, for CLI exercises).

---

# Lab Steps

## Step 1 — Create a Windows Virtual Machine

**Objective:** Deploy a Windows Virtual Machine in Azure.

### Procedure

1. In the Azure Portal, navigate to:

   **Virtual Machines** → **+ Create** → **Azure Virtual Machine**

2. Configure the VM with the following settings:

| Setting            | Value                                                |
| ------------------ | ---------------------------------------------------- |
| **Resource Group** | RG-Dubai-IT                                          |
| **VM Name**        | vm-desktop-support-01                                |
| **Image**          | Windows 10 Pro *(or Windows Server 2022 Datacenter)* |
| **Size**           | Standard_B1s (1 vCPU, 1 GB RAM — free tier eligible) |
| **Admin Username** | itadmin                                              |
| **Password**       | Set a strong password (save it!)                     |

3. Review the configuration.

4. Deploy the virtual machine.

> ⚠️ **Important**
>
> Store the administrator password securely. It is required to connect to the virtual machine.

---

## Step 2 — Configure Networking

**Objective:** Configure network connectivity for the Virtual Machine.

### Procedure

1. Configure the following networking settings during deployment:

| Setting                        | Value                 |
| ------------------------------ | --------------------- |
| **Virtual Network**            | Create new            |
| **Virtual Network Name**       | VNet-Dubai            |
| **Subnet**                     | Default               |
| **Public IP**                  | Enabled               |
| **NIC Network Security Group** | Basic                 |
| **Inbound Rule**               | Allow RDP (Port 3389) |

> ⚠️ **Warning**
>
> In production environments, **never expose RDP directly to the internet**. Instead, use **Azure Bastion** to provide secure remote access.

---

## Step 3 — Connect via Remote Desktop (RDP)

**Objective:** Connect to the Azure Virtual Machine.

### Procedure

1. After deployment, open the Virtual Machine.

2. Navigate to:

   **Overview** → **Connect**

3. Select **RDP**.

4. Download the **.rdp** file.

5. Open the downloaded **.rdp** file.

6. Sign in using:

| Credential   | Value                                  |
| ------------ | -------------------------------------- |
| **Username** | itadmin                                |
| **Password** | Your configured administrator password |

7. Accept the certificate warning.

8. Verify that you are successfully connected to the Azure Virtual Machine.

> ✅ **Validation**
>
> You should now be logged into the Windows desktop running inside the Azure Virtual Machine.

---

## Step 4 — Enable Azure Bastion (Secure RDP)

**Objective:** Configure secure browser-based remote access.

### Procedure

1. Open the Virtual Machine.

2. Navigate to:

   **Connect** → **Bastion**

3. Create **Azure Bastion**.

> **Requirement:** Azure Bastion requires a dedicated subnet.

4. After deployment, use Bastion to establish a browser-based RDP or SSH session.

> 💡 **Tip**
>
> Azure Bastion provides secure browser-based RDP and SSH access without requiring a public IP address on the virtual machine.

---

## Azure CLI Commands

Use the following Azure CLI commands to manage the virtual machine.

### Start the Virtual Machine

```bash
az vm start --name vm-desktop-support-01 --resource-group RG-Dubai-IT
```

### Stop the Virtual Machine

```bash
az vm stop --name vm-desktop-support-01 --resource-group RG-Dubai-IT
```

---

# ☁️ Best Practice Tips

> **Important**

✔ Always **stop Virtual Machines** when they are not in use. Azure charges for compute resources even when a VM is idle.

✔ Use **Azure Bastion** instead of exposing **RDP (Port 3389)** directly to the internet.

✔ Enable **Auto-shutdown** for development and test virtual machines.

Navigate to:

**VM** → **Auto-shutdown** → Configure the shutdown time.

✔ For Linux Virtual Machines, use **SSH key pairs** instead of passwords for significantly stronger security.

---

# Validation Checklist

| Task                        | Expected Result                               |
| --------------------------- | --------------------------------------------- |
| Virtual Machine created     | vm-desktop-support-01 deployed successfully   |
| Networking configured       | Public IP assigned and RDP enabled            |
| RDP connection established  | Successfully connected to the Windows desktop |
| Azure Bastion configured    | Secure browser-based remote access available  |
| Azure CLI commands executed | VM starts and stops successfully              |

---

# Summary

In this lab, you completed the following tasks:

* Deployed a Windows Virtual Machine in Azure.
* Configured networking for remote access.
* Connected to the VM using Remote Desktop Protocol (RDP).
* Enabled Azure Bastion for secure remote administration.
* Managed the virtual machine using Azure CLI.
* Reviewed Azure Virtual Machine deployment and security best practices.

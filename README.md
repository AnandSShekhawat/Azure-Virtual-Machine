## Testing the obsidian and git 
# Azure-Virtual-Machine
An **[Azure](https://portal.azure.com/#create/Microsoft.VirtualMachine-ARM) Virtual Machine (VM)** is an **on-demand, scalable computing resource** provided by Microsoft Azure. It allows you to run **Windows or Linux-based servers** in the cloud just like you would on physical hardware—but without the upfront costs or maintenance.

---
## Key Components of Azure VM

|    <mark>**Component**<mark>     |                                      <mark>**Description**<mark>                                       |
| :------------------------------: | :----------------------------------------------------------------------------------------------------: |
|            **Image**             | *A base OS image used to create the VM (e.g., Ubuntu, Windows Server). You can use custom images too.* |
|          **Size (SKU)**          |          *Defines CPU, RAM, storage, and network capacity. Example: `Standard_B2s`, `D2_v3`*.          |
|             **Disk**             |               *OS Disk (required) and Data Disks (optional). You can choose HDD or SSD.*               |
|      **Network Interface**       |                             *Connects the VM to a Virtual Network (VNet).*                             |
|       **Virtual Network**        |           *A logically isolated network in Azure. VMs must be inside a VNet to communicate.*           |
|            **Subnet**            |                      *A subdivision of a VNet to organize and secure resources.*                       |
|     **Public IP (optional)**     |                              *Used to access your VM from the internet*.                               |
| **Network Security Group (NSG)** |                       *Controls inbound/outbound traffic using firewall rules.*                        |
|     **Availability Options**     |                   *Options like Availability Sets and Zones for high availability.*                    |

---
## How to Create VM in Azure

### 1.  **Azure Portal**

- Easiest way: Go to Azure Portal → Virtual Machines → Create.
- Fill in basic settings (name, region, image, size, authentication, etc.)
![Azure VM](https://learn.microsoft.com/en-us/azure/virtual-machines/windows/media/quick-create-portal/instance-details.png#lightbox)
### 2. Azure CLI

- Azure CLI can be used to create VM in azure.
```
az vm create \
  --resource-group myResourceGroup \
  --name myVM \
  --image UbuntuLTS \
  --admin-username azureuser \
  --generate-ssh-keys
```
### 3. Azure Template / Bicep / Terraform

* Use Infrastructure as Code (IaC) to automate VM creation.
- Example: Use ARM template to provision a VM with NSG, VNet, Public IP.

---
## Authentication Method

- **Username & Password**
- **SSH Key (Linux)**
- **Azure AD Login**
- **Managed Identity** (for internal service access)

---
## Security Features

- NSGs for network-level protection
- Azure Defender for threat detection
- Encryption at rest (disks), in transit, and optionally with customer-managed keys
- Just-in-time (JIT) VM access (controlled time-limited access to ports)

---
## Pricing Considerations

>**Pay-as-you-go model**
>>Pricing based on:
>>>    VM size (CPU/RAM)
>>>    Region
>>>    OS (Windows licenses cost more than Linux
>>>    Disk type and size
>>>    Reserved Instances can reduce cost up to 72%

---
## Creating Using the ARM Template 
### **ARM Template Structure**
ARM templates use these key sections:

* $schema – defines the schema used to validate the template

* contentVersion – version for your own tracking

* parameters – user inputs (like VM name, size, credentials)

* variables – internally reused values

* resources – actual Azure resources to deploy

* outputs – values returned after deployment


## **Resources Created:**
### 1. Virtual Network (VNet)
```
"type": "Microsoft.Network/virtualNetworks"
```

* Provides an isolated network in Azure.

* You define a CIDR address space and create subnets inside it.

### 2. Network Security Group (NSG)
```
"type": "Microsoft.Network/networkSecurityGroups"

```
* Allows RDP (port 3389) and HTTP (port 80) inbound

* Public IP Address

* Static IP assigned to the VM

### 3.Network Interface Card (NIC)
```
"type": "Microsoft.Network/networkInterfaces"

```
* Connects the VM to the subnet and public IP

### 4.Windows Virtual Machine
```
"type": "Microsoft.Compute/virtualMachines"

```
|>Defines the VM configuration:

* OS profile (name, admin credentials)

* Hardware profile (VM size)

* Storage (image details: Windows Server 2022)

* Network profile (NIC reference)

### 5.Custom Script Extension
```
"type": "Microsoft.Compute/virtualMachines/extensions"

```
* Downloads and runs a PowerShell script (script2.ps1) from Azure Blob Storage

* Uses specified storage account credentials

---

### **Outputs:**
* Admin username and password (as secure string)

* The public IP address of the VM

 --- 



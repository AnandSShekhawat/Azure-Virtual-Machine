
## **Objective:**  
To create a Linux Virtual Machine in Microsoft Azure using the Azure Portal. This involves selecting the appropriate subscription, resource group, region, VM size, authentication method, and OS image. The goal is to deploy a fully functional VM for development or testing purposes.


# Tasks : 
- Login 
- Creation of VM
- Connection

## Task 1 : Log in to the Azure Portal

- Go to: [https://portal.azure.com](https://portal.azure.com) 
<<<<<<< HEAD
- Enter your **credentials (1)** to log in to azure. Click on **Next (2)** to enter the password.
![Sign in](image.png)
=======
1. Enter your credentials to log in to azure.
2. Click on Next to enter the password.
![Sign in](image.png)
---
## 2. **Search for Virtual Machines**
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

<<<<<<< HEAD
=======
1. In the search bar at the top, type **"Virtual Machines"** and select it.
2. Click on Virtual Machine.
![Search VM](image-1.png)
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

<<<<<<< HEAD
=======
---
## 3. **Create Virtual Machine** 
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

<<<<<<< HEAD
## **Tasks 2 : Creation**  
=======
1. Click on **Create**.
2. Select **Azure Virtual Machine**.
![Azure VM](image-19.png)

---
## 4. **Basics Tab**

We need to fill in the basic configuration details:
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

<<<<<<< HEAD
- On the Azure portal, click on search bar, search for **Vitutual machine (1)**, and select **Vitutual machine (2)**.
![Search VM](image-1.png)
- Click on **Create (1)** and Select **Azure Virtual Machine (2)**.
![Azure VM](image-19.png)
=======
1. In **Subscription** Field you need to Select the Azure Subscription in which you want to create this VM.
2. For **Resource Group** you can create a new one or use the existing one.
3. **Virtual Machine** : Give your VM a unique name.
4. **Region** : Choose the location (e.g., East US, West Europe).
![Basic Tab 1](image-2.png)
5. **Availability Options** : Default is fine for a basic VM.
6. **Security Type** : The **Security Type** option in Azure Virtual Machines determines the level of security features enabled for the VM. You can choose from
	- 1. **Standard Security**
	- 2. **Trusted Launch** 
7. **Image** : Choose OS image (e.g., Windows Server 2022, Ubuntu 22.04).
8.  **Size** : Click "See all sizes" to pick VM specs (e.g., Standard_B1s for low-cost)
![Basic Tab 2](image-3.png)
9. **Username** : Provide an username for the VM user.
10. **Password** :  Give the password to securely access the VM.
11. **Confirm Password** : Right the same password that you have written above.
![Basic Tab 3](image-4.png)
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

<<<<<<< HEAD
=======
12. **Public Inbound ports** :  Open ports like RDP (3389) for Windows or SSH (22) for Linux, or you can also open ports like HTTP(80) and HTTPS(443).
13.  Click on **Next : Disks >**
![Basic Tab 4](image-5.png)
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

<<<<<<< HEAD
- In **Basics Tab** put the value as mentioned in the table.
=======
---
## 5. Disks Tab
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

<<<<<<< HEAD
	We need to fill in the basic configuration details:  
	| Settings | Values |
	|:---: | :---:|
	|Subscription | **Azure (1)**|
	|Resource Group | **RG-01 (2)** |
	| Virtual Machine  | **VM-01 (3)**|
	|Region  | **South India (4)**|
=======
1. **OS Disk Size** : Choose OS disk size based on your requirement.
2. **OS Disk Type** : Choose the OS disk type (Standard HDD, Standard SSD, Premium SSD).
![Disk Tab 1](image-6.png)
3. Click on **Next : Networking >**
![Disk Tab 2](image-7.png)
---
## 6. Networking Tab
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

<<<<<<< HEAD
	![Basic Tab 1](image-2.png)
	| Settings | Values |
	|:---: | :---:|
	|Availability Options | **No infrastructure redundancy required (5)**|
	|Security Type  | **Trusted Launch Virtual Machine (6)**|
	|Image| **Ubuntu Server 22.04 LTS - x64 (7)**|
	|Size | **Standar_B2ms (8)**|
=======
1. **Virtual Network** : Select an existing VNET or Create a new one. VNET. Virtual network are logically isolated from each other in azure.
2. **Public IP** : Public IP should be there (to connect to VM), you can also create a new one.
3. **NIC Network Security Group** : Associate a **Network Security Group (NSG)** — you can allow default rules like SSH or RDP.
![Networking Tab 1](image-8.png)
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

<<<<<<< HEAD
=======
4. **Select inbound ports** : Choose the port you want to keep open.
5. **Load Balancing** : Select None, as we don't require Load Balancer in this lab.
![Networking Tab 2](image-9.png)
6. Click on **Review + create**.
![Networking Tab 3](image-10.png)
---
## 7. Validation + Create
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

<<<<<<< HEAD
=======
1. After validation is complete click on **Create**.
![Validation + Create](image-11.png)
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

<<<<<<< HEAD
	![Basic Tab 2](image-3.png)  
	| Settings | Values |
	|:---: | :---:|
	|Username|**azureadmin (9)**|
	|Password|**Password1234! (10)**|
	|Confirm Password|**Password1234! (11)**|
=======
---
## 8. **Deployment**
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

<<<<<<< HEAD
	![Basic Tab 3](image-4.png)
- Click on **Next : Disks > (13)** after selecting **Public Inbound ports** as **Port 80 (12)**. 
![Basic Tab 4](image-5.png)
=======
1. After deployment is complete click on **Go to resource**.
![Go To resource](image-12.png)
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

<<<<<<< HEAD
=======
---
## 9. Connect to the VM
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

<<<<<<< HEAD
- In Disks Tab use the following value and keep everything else as **default**.
=======
1. In order to connect to VM we need to click on **Connect** drop down.
2. Click on **Connect**.
![Connect 1](image-13.png)
3. Copy the **Public IP** to connect to our Linux VM.
![Connect 2](image-14.png)
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

<<<<<<< HEAD
	| Settings | Values |
	|:---: | :---:|
	|OS Disk Size|**Image Default(30GB) (1)**|
	|OS Disk Type|**Premium Standard SSD (2)**|
	![Disk Tab 1](image-6.png)  
=======
## 10. Connecting Using Putty
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

<<<<<<< HEAD
- Click on **Next : Networking > (3)**
	![Disk Tab 2](image-7.png)
=======
1. Open **Putty**
2. Paste the **Public IP** of your machine.
3. Click on **Connect** to the VM.
![Putty 1](image-15.png)
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

<<<<<<< HEAD
- Networking Tab check the following values and keep everything as **default**  
	| Settings | Values |
	|:---: | :---:|
	|Virtual Network| **Vnet-01 (1)**|
	|Public IP| **PIP (2)**|
	|NIC Network Security Group| **NSG (3)**|
=======
4. Click on **Accept** 
![Putty 2](image-16.png)
5. Enter the **Username** that you have given while creating the VM.
6. Enter **Password** of the VM that you have given.
![Putty 3](image-17.png)
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

<<<<<<< HEAD
	![Networking Tab 1](image-8.png)
	| Settings | Values |
	|:---: | :---:|
	|Select Inbound ports| **SSH (22) (4)**|
	|Load Balancing | **None (5)**|
=======
#### **We are finally connected to our Linux Virtual Machine.**
![Putty 4](image-18.png)
>>>>>>> 43d5d665b315017128bf4baff8df84fdee5a1b0e

	![Networking Tab 2](image-9.png)
- Click on **Review + create (6)**.
	![Networking Tab 3](image-10.png)

- After validation is complete click on **Create**.
![Validation + Create](image-11.png)


- After deployment is complete click on **Go to resource**.
![Go To resource](image-12.png)


## **Task 2 : Connect to the VM**

- In order to connect to VM we need to click on **Connect (1)** drop down, click on **Connect (2)**.
![Connect 1](image-13.png)
- Copy the **Public IP (3)** to connect to our Linux VM.
![Connect 2](image-14.png)

### Connecting Using Putty

- Open **Putty (1)** and Paste the **Public IP (2)** of your machine. Click on **Connect (3)** to the VM.
![Putty 1](image-15.png)

- Click on **Accept (4)** 
![Putty 2](image-16.png)
- Enter the **Username (5)** and 
**Password (6)**.
![Putty 3](image-17.png)

	#### **We are finally connected to our Linux Virtual Machine.**
	![Putty 4](image-18.png)


<img width="573" height="385" alt="Vpn image" src="https://github.com/user-attachments/assets/8cf8f7a5-ea0f-4622-9bbc-3e43907e0600" />


# VPN Lab: Using Azure VM and ProtonVPN to Observe IP and Geolocation Changes

## Technologies Used
- Microsoft Azure (Virtual Machines, Resource Groups)
- Windows 10 (Virtual Machine OS)
- ProtonVPN (VPN service)
- Remote Desktop Protocol (RDP)
- https://whatismyipaddress.com (IP geolocation lookup)
- Web Browsers (Google, Disney, Amazon)

## Prerequisites
- Microsoft Azure account with permission to create resources
- Basic familiarity with Azure Portal and VM setup
- Remote Desktop access (RDP)
- Internet connection
- ProtonVPN free account ([Sign up here](https://account.protonvpn.com/signup?plan=free&language=en))
- Text editor (e.g., Notepad) to log IP addresses

---

## What This Lab Does

This lab demonstrates how VPNs can be used to mask your IP address and simulate browsing from different geographic regions. You will create a Windows 10 virtual machine in Azure, connect to it via Remote Desktop, and test how ProtonVPN can change your visible IP address and location. You'll record and compare IP addresses before and after using the VPN.

---

## Lab Steps

### (Create Virtual Machine in Azure)

1. **Check your current IP address**
   - From your actual machine, go to [https://whatismyipaddress.com](https://whatismyipaddress.com) and save your IP address in a text file.

2. **Create a Resource Group**
   - In Azure Portal, create a new resource group to hold the virtual machine and related resources.

3. **Create a Windows 10 VM in another geographic location**
   - Choose a region different from your own.
   - Log in to the VM using Remote Desktop.
   - On the VM, visit [https://whatismyipaddress.com](https://whatismyipaddress.com) and record the new IP address.

---

### (Sign Up for ProtonVPN and Test VPN Connection)

4. **Create a free ProtonVPN account**
   - Visit [ProtonVPN sign-up](https://account.protonvpn.com/signup?plan=free&language=en) from your actual machine.

5. **Install ProtonVPN inside the VM**
   - Download and install ProtonVPN on the VM.
   - Log into ProtonVPN and connect to a VPN server in a different country (e.g., Japan).
   - Visit [https://whatismyipaddress.com](https://whatismyipaddress.com) again and record the VPN-masked IP address.

6. **Test geographic content differences**
   - Browse websites like Google, Disney, and Amazon.
   - Note any changes in language, currency, or layout due to your VPN location.

---

### (Clean Up Azure Resources)

7. **Delete the Azure resource group you created**
   - Go back to the Azure portal and delete the resource group from step 2.

8. **Confirm deletion**
   - Ensure all associated resources have been removed to avoid unnecessary charges.

---

CONFIGURATION STEPS

<img width="1898" height="878" alt="Active Directory lab, creating resource group" src="https://github.com/user-attachments/assets/9e1f8e90-7de9-437c-a9c3-6e273f8a07c6" />

## Step 1: Create a Resource Group in Azure

![Azure Portal - Create Resource Group](https://user-images.githubusercontent.com/YOUR_IMAGE_LINK.jpg)

This screenshot shows the Azure Portal interface during the process of **creating a Resource Group**, which is the first step in setting up cloud infrastructure for this lab. The form includes the following configuration fields:

- **Subscription:** `Active-Directory-Lab`
- **Resource Group Name:** (input field for defining the name)
- **Region:** `East US 2` *(this will later be changed to a region in **Canada** during VM setup)*

A blue button labeled **"Review + create"** appears at the bottom, allowing the user to proceed after entering all required information.

### Purpose of This Step

This corresponds to **Step 1** of the Lab Checklist:

> `1. Create a Resource Group`

Creating a resource group is essential before provisioning services like virtual machines. It acts as a container for organizing and managing related Azure resources. This step establishes the workspace where all cloud assets for the lab will reside. The choice of region (initially `East US 2`) will be adjusted to **Canada** in a later step to demonstrate geographic diversity for VPN and IP testing.

<img width="1909" height="807" alt="Screenshot 2025-06-30 121523" src="https://github.com/user-attachments/assets/3f90846b-fcae-40dd-9598-74ba45b96620" />

## Step 2: Create a Windows 10 Virtual Machine in Azure

![Azure Portal - Create Virtual Machine](https://user-images.githubusercontent.com/YOUR_IMAGE_LINK.jpg)

This screenshot captures the configuration screen for setting up a Windows 10 Virtual Machine in the Microsoft Azure portal. The VM is being deployed to a different geographic region, specifically **Canada Central**, to support the VPN-related objectives of the lab.

### Configuration Details:
- Subscription: Azure subscription 1
- Resource Group: vpn-test
- Virtual Machine Name: vpn-test-win10
- Region: (Canada) Canada Central
- Availability Option: Availability zone
- Image: Windows 10
- Size: Standard_D2s_v3
- Estimated Monthly Cost: $100.74 (shown on the right)

### Purpose of This Step

This corresponds to **Step 3** in the Lab Checklist:

> 3. Create a Windows 10 Virtual Machine in another geographic location (try a different country)

This step is necessary to simulate geographic variation in internet access. By deploying the VM in Canada and accessing it remotely, users can test how services and websites behave when accessed from another region. This sets the stage for testing VPN behavior in later steps.

<img width="1869" height="780" alt="Screenshot 2025-06-30 124922" src="https://github.com/user-attachments/assets/36916353-3370-4e17-8408-37a402f59505" />

## Step 3: Virtual Machine Deployment in Progress

![Azure Portal - VM Deployment in Progress](https://user-images.githubusercontent.com/YOUR_IMAGE_LINK.jpg)

This screenshot shows the Azure Portal displaying the **deployment progress** of a Windows 10 virtual machine. The deployment process has been initiated successfully and includes multiple resources being provisioned under the selected resource group.

### Deployment Details:
- Deployment Name: CreateVm-MicrosoftWindowsDesktop.Windows-10-win10-20250630120542
- Subscription: Azure subscription 1
- Resource Group: vpn-test
- Start Time: 07/03/2025, 7:41:41 PM

### Resources Being Created:
- vpn-test-win10: Microsoft.Compute/virtualMachines (Status: Created)
- vpn-test-win10-nic: Microsoft.Network/networkInterfaces (Status: OK)
- vpn-test-win10-vnet: Microsoft.Network/virtualNetworks (Status: OK)
- vpn-test-win10-nsg: Microsoft.Network/networkSecurityGroups (Status: OK)
- vpn-test-win10-ip: Microsoft.Network/publicIPAddresses (Status: OK)

### Purpose of This Step

This screenshot confirms successful provisioning of Azure resources that are part of the virtual machine infrastructure. It validates that the virtual machine is being created with supporting network components (NIC, VNet, NSG, Public IP), which are essential for remote access and future VPN testing.

Once the deployment is complete, the VM can be accessed via Remote Desktop Protocol (RDP) for the VPN testing steps outlined later in the lab.

<img width="1897" height="857" alt="using remote desktop after creating our virtual machine, vpn set up   usage lab" src="https://github.com/user-attachments/assets/1131a9ca-fb88-4f47-983f-8a51047f5fe5" />

## Step 4: Access the Virtual Machine via Remote Desktop

![Azure Portal - RDP Access to VM](https://user-images.githubusercontent.com/YOUR_IMAGE_LINK.jpg)

This screenshot shows the user's system accessing the newly created virtual machine using **Remote Desktop Protocol (RDP)**. The Remote Desktop Connection interface displays saved PCs, including the VM labeled `vpn-test-win10rdwin`, confirming the session is ready for connection.

### How to Get Here – Steps to Access the VM via RDP:

1. Navigate to the **Azure Portal**.
2. Go to **Virtual Machines** under the **Compute** section in the sidebar.
3. Select your deployed VM (e.g., `vpn-test-win10`).
4. Click on the **"Connect"** button at the top of the VM Overview page.
5. Choose the **RDP (Remote Desktop)** option.
6. Download the `.rdp` file provided by Azure and open it.
7. When prompted, enter the **username and password** that were configured during the VM creation process.
8. Accept the certificate warning (if shown), and you will be connected to the virtual machine.

### Details Observed in the Screenshot:
- Remote Desktop client shows multiple saved PC entries, including the active test VM
- VM name: `vpn-test-win10rdwin`
- Connection is initiated from a local system to the cloud-hosted Windows 10 VM
- Azure Portal in the background confirms the VM is listed and active

### Purpose of This Step

This fulfills the checklist item:

> Log into the VM with Remote Desktop

Remote access enables users to interact with the VM as if it were a physical machine. This is critical for the next phase of the lab, where VPN software will be installed and geolocation behavior will be tested. Successfully establishing RDP access verifies that the VM is online, reachable, and properly configured for the lab's objectives.

<img width="1905" height="871" alt="deleting or clean up VM  after using Vpn lab" src="https://github.com/user-attachments/assets/f3742fb4-3c1a-44c7-a3c2-a2c15f61d3d2" />















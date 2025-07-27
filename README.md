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


CONFIGURATION STEPS

# 🔧 VPN Setup and Usage Guide

This guide walks through the step-by-step process of setting up, connecting, and verifying a VPN using Proton VPN and Azure Virtual Machines. Follow each step in order and insert your screenshots in the indicated locations.

---

## 1. Log in to Azure and Access Virtual Machines
<img width="1909" height="807" alt="Screenshot 2025-06-30 121523" src="https://github.com/user-attachments/assets/3f90846b-fcae-40dd-9598-74ba45b96620" />
Go to the Azure Portal and access your virtual machines.
---

### 2. Monitor Deployment Progress
<img width="1869" height="780" alt="Screenshot 2025-06-30 124922" src="https://github.com/user-attachments/assets/36916353-3370-4e17-8408-37a402f59505" />
Once the virtual machine deployment begins in Azure, monitor the progress and ensure all listed resources show a "Created" or "OK" status.

---

### 3. Locate Virtual Machines
<img width="1897" height="857" alt="using remote desktop after creating our virtual machine, vpn set up   usage lab" src="https://github.com/user-attachments/assets/1131a9ca-fb88-4f47-983f-8a51047f5fe5" />
Go to the “Virtual machines” section in Azure. Here, confirm your VM is listed and ready. Also, verify the corresponding PC entries in Remote Desktop.

---

### 4. Configure Remote Desktop Connection
![image](https://github.com/user-attachments/assets/d32a697b-3991-48b8-8263-9991df5518ba)
Open Microsoft Remote Desktop and enter the IP address of the VM. Complete the setup by filling in the user name and saving it to your list of saved PCs.

---

### 5. Download Proton VPN Client
![image](https://github.com/user-attachments/assets/4236f54f-2f86-4879-b708-6e2d92585d0b)
Go to the Proton VPN website and click on **Download** for your operating system.

---

### 6. Begin Installation Setup
![image](https://github.com/user-attachments/assets/003071d5-041f-4e54-bd0e-ccae482e3cfa)
After downloading, run the installer. On the **Ready to Install** screen, click **Install** to begin the installation.

---

### 7. Connect to a VPN Server
![image](https://github.com/user-attachments/assets/1237e5a8-ca8f-4f0e-bc76-7a92a115d925)

Launch Proton VPN and choose a server location. Connect to it using the available button.

---

### 8. Verify VPN IP Address
![image](https://github.com/user-attachments/assets/9b2e1567-3865-4583-97f0-2c853fac9837)
Visit [https://whatismyipaddress.com](https://whatismyipaddress.com) and confirm the IP address is different from your original location.


### 9. Delete the Virtual Machine from Azure
<img width="1905" height="871" alt="deleting or clean up VM  after using Vpn lab" src="https://github.com/user-attachments/assets/f3742fb4-3c1a-44c7-a3c2-a2c15f61d3d2" />
Go to **Azure Portal > Virtual Machines**, select your VM, then click **Delete**.  
Ensure the associated resources (OS disk, network interfaces, public IP) are selected as needed.  
Check the acknowledgment box and click **Delete**.






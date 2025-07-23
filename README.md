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

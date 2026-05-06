# VPN Project - Setting Up Connection with ProtonVPN

## Project Summary

In this report, I've installed and configured a Virtual Private Network (VPN) with a connection manager (ProtonVPN). We tried to model an actual IT help case involving connecting to remote infrastructure via VPN. Using a Mac device, a cloud-based virtual machine in Microsoft Azure, and a VPN, this project demonstrates how IP addresses and locations are transferred and altered across environments.

---

## Languages Used

* None

---

## Environments Used

* macOS (Mac Pro 2019)
* Microsoft Azure
* Windows 10 Virtual Machine

---

## Technologies / Services Used

* ProtonVPN
* Microsoft Azure Virtual Machines
* Microsoft Remote Desktop
* WhatIsMyIPAddress.com

---

## VPN Usage in IT Environments

VPNs are widely used in IT environments to ensure security, primarily for connecting to remote networks. They also encrypt traffic and disguise IP addresses, reducing the risk of packet exposure and improving privacy while reducing security risks.

---

## Checking Local IP Address

I went to WhatIsMyIPAddress.com using my Mac Pro (2019) to determine my public IP address and location. This set a baseline prior to accessing any remote system or VPN.

![Local IP Check](images/local-ip.png)

---

## Creating an Azure Virtual Machine

I created a resource group and installed a Windows 10 virtual machine in Microsoft Azure.
Next, I selected Geographic Region and chose Sydney, Australia. After this, I configured login credentials and enabled Remote Desktop Access. As a result, this VM simulates a remote system hosted in a different location.

![Azure VM Setup](images/azure-vm.png)

---

## Connect to the VM

I connected my computer to the virtual machine via Microsoft Remote Desktop. After downloading the RDP file and logging in with the given credentials, I accessed the Windows desktop.

![RDP Connection](images/rdp.png)

---

## Checking VM IP Address

I visited WhatIsMyIPAddress.com in the VM as soon as I got there. The results showed:

* IP address: 20.211.72.199
* Location: Sydney, Australia

This verified the VM was running from the Azure region selected.

![VM IP Check](images/vm-ip.png)

---

## Setting Up and Connecting VPN

Within the VM, I:

* Signed up for ProtonVPN
* Installed the VPN client
* Logged in and connected to a VPN server

![VPN Setup](images/vpn-setup.png)

---

## After Connecting

* New IP address: 37.120.234.195
* Location: Sydney, Australia

![VPN Connected](images/vpn-connected.png)

---

## Testing VPN Connection

To verify the VPN setup:

* Checked IP with WhatIsMyIPAddress.com
* Opened Google to see any regional differences

While the location was unchanged, the IP address changed. This shows that the VPN effectively connected traffic to a different server located in the same area.

---

## Resource Cleanup

After testing, I deleted the resource group in Microsoft Azure to remove all associated resources and avoid unnecessary expense.

---

## Conclusion

This project showcases how a VPN can be used to secure remote services in a cloud system. The application demonstrates how IP addresses change between layers: moving from a local Mac device to an Azure VM and then connecting to a VPN demonstrates how an attack surface can change.

Although the geographic location remained the same, the data confirmed that the VPN was working correctly through encrypted traffic. Relevant IT support activities include remote access, cloud systems, and secure network access.

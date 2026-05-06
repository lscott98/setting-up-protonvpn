# VPN Project - Setting Up Connection with ProtonVPN

## Project Summary

In this report, I've installed and configured a Virtual Private Network (VPN) with a connection manager (ProtonVPN). We tried to model an actual IT help case involving connecting to remote infrastructure via VPN. Using a Mac device, a cloud-based virtual machine in Microsoft Azure, and a VPN, this project demonstrates how IP addresses and locations are transferred and altered across environments.

---

## Languages Used

- None

---

## Environments Used

- macOS (Mac Pro 2019)
- Microsoft Azure
- Windows 11 Virtual Machine

---

## Technologies / Services Used

- ProtonVPN
- Microsoft Azure Virtual Machines
- Microsoft Remote Desktop
- WhatIsMyIPAddress.com

---

## VPN Usage in IT Environments

VPNs are widely used in IT environments to ensure security, primarily for connecting to remote networks. They will also encrypt traffic and disguise IP addresses, thus reducing the risk of packet exposure and improving privacy while reducing security risks.

---

## Checking Local IP Address

I went to WhatIsMyIPAddress.com using my Mac Pro (2019) to determine my public IP address and location. This set a baseline prior to accessing any remote system or VPN.

<p align="center">
  <img src="images/local-ip.png" width="800">
</p>

---

## Creating an Azure Virtual Machine

I created a resource group and installed a Windows virtual machine in Microsoft Azure.

Next, I selected Geographic Region and chose Sydney, Australia. After this, I configured login credentials and enabled Remote Desktop Access. As a result, this VM will simulate a remote system hosted in a different location.

<p align="center">
  <img src="images/azure-vm-creation.png" width="800">
</p>

<p align="center">
  <img src="images/azure-deployment.png" width="800">
</p>

<p align="center">
  <img src="images/vm-public-ip.png" width="500">
</p>

---

## Connect to the VM

I connected my computer to the virtual machine via Microsoft Remote Desktop. After I downloaded the RDP file and logged in with the given credentials. Once that was completed, I accessed the Windows desktop.

<p align="center">
  <img src="images/remote-desktop.png" width="700">
</p>

---

## Checking VM IP Address

I visited WhatIsMyIPAddress.com in the VM as soon as I got there.

The results showed:

- IP address: 20.211.72.199
- Location: Sydney, Australia

This verified the VM was running from the Azure region selected.

<p align="center">
  <img src="images/vm-ip-check.png" width="800">
</p>

---

## Setting Up and Connecting VPN

Within the VM, I:

- Signed up for ProtonVPN
- Installed the VPN client
- Logged in and connected to a VPN server

### ProtonVPN Login

<p align="center">
  <img src="images/proton-login.png" width="700">
</p>

### Download ProtonVPN

<p align="center">
  <img src="images/proton-download.png" width="700">
</p>

### Install ProtonVPN

<p align="center">
  <img src="images/proton-install.png" width="700">
</p>

### VPN Connected

<p align="center">
  <img src="images/vpn-connected.png" width="900">
</p>

---

## After Connecting

- New IP address: 37.120.234.195
- Location: Sydney, Australia

<p align="center">
  <img src="images/vpn-ip-changed.png" width="800">
</p>

---

## Testing VPN Connection

To verify the VPN setup:

- Checked IP with WhatIsMyIPAddress.com
- Opened Google to see any regional differences

While the location was unchanged, the IP address changed. This shows that the VPN effectively connected traffic to a different server located in the same area.

---

## Resource Cleanup

After testing, I deleted the resource group in Microsoft Azure to remove all associated resources and avoid unnecessary expense.

---

## Conclusion

This project showcases how a VPN can be a way to secure a remote service in a cloud system. The application demonstrates how IP addresses change between layers: moving from a local Mac device to an Azure VM and also connecting to a VPN demonstrates how an attack surface will change.

Remotely, although the geographic location was at the same place, this data confirmed that the VPN was working correctly in an encrypted protocol and traffic encryption. Relevant IT support activities include remote access, cloud systems, and secure network access.

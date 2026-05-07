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

<img width="900" height="400" alt="image" src="https://github.com/user-attachments/assets/edec4157-e1e3-4ac1-9e88-f07471c94b88" />

---

## Creating an Azure Virtual Machine

I created a resource group and installed a Windows virtual machine in Microsoft Azure.

Next, I selected Geographic Region and chose Sydney, Australia. After this, I configured login credentials and enabled Remote Desktop Access. As a result, this VM will simulate a remote system hosted in a different location.

<img width="761" height="905" alt="image" src="https://github.com/user-attachments/assets/a7a5974f-9501-4585-9c19-b520aaafdc0d" />

<img width="765" height="521" alt="image" src="https://github.com/user-attachments/assets/3b8b4ffd-920c-4cad-84d6-57d04a5fed73" />


---

## Connect to the VM

I connected my computer to the virtual machine via Microsoft Remote Desktop. After I downloaded the RDP file and logged in with the given credentials. Once that was completed, I accessed the Windows desktop.

<img width="227" height="132" alt="image" src="https://github.com/user-attachments/assets/452c12a6-896c-4858-a513-2627ec9d5372" />


<img width="752" height="735" alt="image" src="https://github.com/user-attachments/assets/f33a0020-b19e-424b-81fd-aa0097883f50" />

---

## Checking VM IP Address

I visited WhatIsMyIPAddress.com in the VM as soon as I got there.

The results showed:

- IP address: 20.211.72.199
- Location: Sydney, Australia

This verified the VM was running from the Azure region selected.

<img width="1751" height="1119" alt="image" src="https://github.com/user-attachments/assets/b5907e3d-5d0a-48a5-bcb1-f7f76d27322b" />


---

## Setting Up and Connecting VPN

Within the VM, I:

- Signed up for ProtonVPN
- Installed the VPN client
- Logged in and connected to a VPN server

### ProtonVPN Login

<img width="1806" height="1108" alt="image" src="https://github.com/user-attachments/assets/e81c34c1-cfbe-4a23-bfd1-807f7534b989" />

### Download ProtonVPN

<img width="1634" height="1270" alt="image" src="https://github.com/user-attachments/assets/a37290a0-765b-4470-9095-7d7451fe3fed" />


### Install ProtonVPN

<img width="1192" height="915" alt="image" src="https://github.com/user-attachments/assets/9fc46250-dd74-4029-9b9c-a1e7ef3b3a45" />


### VPN Connected

<img width="1997" height="1299" alt="image" src="https://github.com/user-attachments/assets/c8e536b1-c1f1-43bd-a2a9-81a2bf3b1361" />


---

## After Connecting

- New IP address: 37.120.234.195
- Location: Sydney, Australia

<img width="2001" height="978" alt="image" src="https://github.com/user-attachments/assets/336465e4-6086-4868-b460-1255d5103a85" />

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

# Cybersecurity Kali Linux Lab Setup
This project involves setting up a Kali Linux virtual machine using Oracle VirtualBox to create a basic cybersecurity lab environment.

The objective id to configure a virtual network, assign Kali Linux a static IPv4 address, and provide internet access. Additional requirements include enabling clipboard sharing, drag-and-drop, and a shared folder between the Windows host and Kali Linux.
#

# 🎯 Objectives
The main objectives of this project are to:
- Install and configure VirtualBox.
- Install/import Kali Linux as a virtual machine.
- Create a private NAT Network for the cybersecurity lab.
- Configure network connectivity for Kali Linux.
- Assign a consistent IP address to the Kali VM.
- Verify network connectivity and DNS resolution.
- Take a clean VM snapshot for recovery.
- Document the complete setup process.
- Prepare the environment for future cybersecurity projects.

# 🛡️ Purpose of the Lab
The purpose of this lab is to create a virtual environment for learning and practicing cybersecurity and networking.

This lab can be used for:
- Learning basic networking concepts.
- Practicing IP address configuration.
- Testing network connectivity.
- Learning cybersecurity tools and techniques.
- Developing troubleshooting skills.

**Important:** All cybersecurity testing must only be performed on systems you own or have explicit permission to test.
#

# 🏗️ Lab Architechture
<img width="1152" height="527" alt="Lab_Architechture" src="https://github.com/user-attachments/assets/ed555e24-7452-43dc-8b4a-c231d1571cf9" />


# ⚙️ Lab Configuration

| Header 1 | Header 2 |
| --- | --- |
| Virtualisation Software | Oracle VirtualBox|
| 🧠 Operating System | Kali Linux |
| 🌐 Network Type | NAT Network |
| 📡 Network Subset | 10.0.0.0/24 |
| 🐧 Kali IP Address | 10.0.0.2 |
| Subnet Mask | 255.255.255.0 |
| 🚪Default Gateway | 10.0.0.1 |
| 🌍 DNS Server | 8.8.8.8 |
| DHCP | Enabled in the VirtualBox NAT Network |
#

# 🪜 Lab Setup Procedure
# Step 1. Prepare the Virtualisation Environment
Oracle VirtualBox was already installed on the host computer. the existing installation was used to manage the virtual machine for this lab.
#
# Step 2. Prepare the Kali Linux Virtual Machine
Kali Linux was already installed in VirtualBox. The virtual machine was used for the lab, so a new installation was not required. the virtual machine was started to begin configuring the network.
#
# Step 3. Configure the NAT NEetwork
A NAT Network was configured in VirtualBox with the IPv4 subnet 10.0.0.0/24. DHCP was initially enabled to allow the virtual machine to obtain an IP address automatically.
#
# Step 4. Check the Initial Network Configuration
The Kali Linux terminal was used to inspect the network interfaces and IP addresses. The following command was executed: 

` ip a `

The output showed that the network interface initially had the IP address 10.0.0.3/24.
#
# Step 5. Configure a Static IP Address
The graphical network connection editor was opened using: 

` nm-connection-editor `

The Wired connection 1 connection was edited. Under IPv4 Settings, the method was changed to Manual, and the following values were entered: 
- Address: 10.0.0.2
- Netmask: 24
- Gateway: 10.0.0.1
- DNS server: 8.8.8.8
The configuration was saved successfully.
#
# Step 6. Reactivate the Network Connection
The saved network connection was restarted using the following commands: 
``` 
nmcli connection down "Wired connection 1" 
nmcli connection up "Wired connection 1"
```
The `ip a` command was then used to check the network interface and confirm that the static IP address had been applied. 
#
# Step 7. Verify Network Connectivity
The gateway connectivity test was inherited using:
` ping -c 4 10.0.0.1 `
The results of this test, along with the internet connectivity test, will be documented after verification.
#
# 🔍 Lab Verification
| Test | Purpose | Result |
| --- | --- | --- |
| `ip a` | Check the assigned IP address | Static IP Configuration applied | 
| `ping -c 4 10.0.0.1` | Test communication with the gateway | Awaiting confirmation of the output
| `ping -c 4 8.8.8.8` | Test external IP connectivity | Not yet verified  |
| `ping -c 4 google.com` | Test DNS resolution and connectivity | Not yet verified |
#
# 🐞 Problems Encountered and Solutions
## Problem 1: Error when changing IPv4 to Manual
When the IPv4 method was changed from Automatic to Manual, the network editor displayed the following error:
`"ipv4.method: method 'manual' requires at least an address or a route" `
Cause: The manual configuration initially did not contain an IP address or a route.
Solution: An address entry was added with the required IP address, netmask, and gateway. The DNS server was also configured , and the connection was saved successfully. 

## Problem 2: The IP address did not change immediately
After saving the manual configuration Kali Linux initially continued to display the previous IP address.
Solution: The network connection was deactivated and reactivated using `nmcli`. The `ip a` command was then used to check the updated configuration.
#
# 💡What I Learnt
Through this lab, I learnt how to configure a virtual network and assign a static IP address to a Kali Linux virtual machine.

I also learnt:

- The difference between DHCP and static IP addressing.
- How IP addresses and subnet masks identify devices and networks.
- The purpose of a default gateway and a DNS server.
- How to inspect network interfaces using "ip a".
- How to manage network connections using "nmcli".
- How to troubleshoot network configuration errors.
- Why connectivity tests are important when verifying a network setup.

The lab also demonstrated the importance of understanding network configuration rather than relying only on default settings.
#
# 🔒 Security and Ethical Use

Kali Linux is used for cybersecurity education, authorised security testing, and learning about network security.

All testing in this lab should be conducted within the controlled virtual environment or on systems for which permission has been granted.

The tools and techniques used in this lab must not be used to access, scan, or attack systems or networks without authorisation.

The purpose of this lab is to develop practical networking and cybersecurity skills responsibly.
#
# 🔗 Tools and Resources

The following tools and resources were used or referenced during the lab:

- Oracle VirtualBox: Virtualisation software used to run the Kali Linux virtual machine.
- Kali Linux: Linux distribution designed for cybersecurity and penetration-testing activities.
- NetworkManager: Used to configure and manage the network connection.
- Terminal: Used to execute network configuration and verification commands.
- "ip a": Used to inspect network interfaces and IP addresses.
- "nmcli": Used to manage the network connection.
- "ping": Used to test network connectivity.
- Google Public DNS: "8.8.8.8".

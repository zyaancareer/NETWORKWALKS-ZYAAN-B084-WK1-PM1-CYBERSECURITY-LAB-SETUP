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
The Kali Linux terminal was used to inspect the network interfaces and IP addresses. The following command was executed: \

` ip a `

The output showed that the network interface initially had the IP address 10.0.0.3/24.
#



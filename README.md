# Cybersecurity Lab Setup
## 1. Project overview
This project focuses on the installation, setup, and network configuration of Kali inside VirtualBox. This is a beginner friendly setup for those who want to learn and switch careers into Cybersecurity.

I have recorded the steps in this README including screenshots for reference.



## 2. Objectives 

- Install VirtualBox.
- Install, import, and configure kali Linux inside VirtualBox.
- Create a private **NATnetwork** inside the Cybersecurity lab.
- Configure the IP address, DNS, Test network connectivity.
- Ensure Kali Linux's internet connection.
- Take a clear snapshot of the VM for recovery.
- Document the findings.

## 3. Lab setup requirement

| Tools            | Configurations            |
| ---------------- | --------------------------|
| Host OS          | Windows 11                |
| RAM Requirement  | 8GB                       |
| Processor        | Intel core i5 and above   |
| Hypervisor       | VirtualBox 7.2.8          |
| Virtual Machine  | Kali Linux 2026.3         |

# 4. Steps taken to setup the lab

## Step 1. Install 7-Zip to extract Kali Linux
I installed 7-zip to extract the Kali Linux virtual-machine package and extract into a new folder so I don't jumble up the files and fill up storage. If you have any issues

## Step 2. Install VirtualBox and import Kali iso.
I installed VirtualBox 7.2.8 and imported the Kali VM using the **New** option.
<img width="1917" height="1015" alt="Virtualbox_installation" src="https://github.com/user-attachments/assets/fe1709b4-559a-4de6-a68d-2621cc3c740f" />
<img width="1917" height="987" alt="image" src="https://github.com/user-attachments/assets/b8d4db04-c59f-4980-afc5-7335d29dc387" />


## Step 3. Configure network settings in VirtualBoc
In VirtualBox, go to the **Network** tab and change the name of the network to `NatNetwork` and input the network subnet in the IPv4 Prefix field `10.0.0.0/24`.
<img width="1917" height="1020" alt="Network_Configuration" src="https://github.com/user-attachments/assets/6f8a8858-bef4-4ff8-a81b-a47e44462551" />

## Step 4. Check for 

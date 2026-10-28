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

## 4. Steps taken to setup the lab

### Step 1. Install 7-Zip to extract Kali Linux.
I installed 7-zip to extract the Kali Linux virtual-machine package and extract into a new folder so I don't jumble up the files and fill up storage. 

### Step 2. Install VirtualBox and import Kali iso.
I installed VirtualBox 7.2.8 and imported the Kali VM you downloaded using the **New** option. If you downloaded the `.vbox` use the **import** option.

<img width="1917" height="1015" alt="Virtualbox_installation" src="https://github.com/user-attachments/assets/fe1709b4-559a-4de6-a68d-2621cc3c740f" />
<img width="1917" height="987" alt="image" src="https://github.com/user-attachments/assets/b8d4db04-c59f-4980-afc5-7335d29dc387" />

RAM allocated for Kali VM: 8192 MB (can be allocated based on your device's specifications).

### Step 3. Configure network settings in VirtualBox.
In VirtualBox, go to the **Network** tab and change the name of the network to `NatNetwork` and input the network subnet in the IPv4 Prefix field `10.0.0.0/24`.

<img width="1917" height="1020" alt="Network_Configuration" src="https://github.com/user-attachments/assets/6f8a8858-bef4-4ff8-a81b-a47e44462551" />

### Step 4. Configure network settings inside Kali Linux.
In Kali Linux, go to network settings. Then go to **IPv4 settings** tab and fill in the required fields as shown in the screenshot below.

<img width="1412" height="862" alt="Network_Configuration inside Kali Linux" src="https://github.com/user-attachments/assets/b337ca4f-1d97-47c7-96ac-42f6ba7179c9" />


#### Network configurations
| Configurations | inputs        |
| -------------- | -------       |
| IP Address     | 10.0.0.2      |
| Subnet mask    | 255.255.255.0 |
| Gateway        | 10.0.0.1      |
| DNS            | 8.8.8.8       |


### Step 5. Verify internet connection inside Kali Linux.
I used the `ping` command to verify the connectivity between the gateway and `google.com`.

<img width="1276" height="755" alt="Internet Connection Verification" src="https://github.com/user-attachments/assets/ecb58855-af3b-4d6c-ab18-f011e87f2e00" />
<img width="655" height="477" alt="image" src="https://github.com/user-attachments/assets/cdafde61-2bab-492b-8a00-0eb4691889c8" />


### Step 6. Take a clear snapshot.
After the whole setup, I took a snapshot of the lab and named it `Cybersecurity Lab Setup - Week 1`.

<img width="1917" height="1021" alt="Snapshot" src="https://github.com/user-attachments/assets/6f234abc-9ced-499a-9de7-09b74f6cf62a" />

## 5. What have I learnt from this project.
### The difference between NAT and NAT networks.
- NAT: NAT assigns each virtual machine its own private subnet behind a separate virtual router, which means VMs are completely isolated from one another and cannot communicate directly; they can only reach the internet through the host's connection, and the host can only reach a VM via port forwarding. This makes it the simplest and most common default for a single VM that just needs outbound internet access.
- NAT Network: It places all VMs on a single subnet so they can communicate with each other without port forwarding while retaining internet access through the host.

## 6. Problems encountered in this project and how I overcame them.
### Problem 1. Error message during installation.
During the installation of Kali Linux, an error message popped up saying **Unexpected token**. I manually scanned my PC to check for any problems and found out that my `C:` Drive (Where I downloaded my Kali Linux ISO) was out of storage. After cleaning the C Drive, showed the same error. Then I found out that after increasing the RAM from 2048 MB to 8192 MB the installation was successful.

### fix 1.
Increased the RAM to 8192 MB for better performance and cleaned up my `C:` Drive.

### Problem 2. Internet connectivity problem.
After manually configuring IPv4 settings, my internet connection failed.

I used the command below to fix the problem: 

``` bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
```
But the connection was still not active. 

### Fix 2
So I reset the network configurations and the connection was successfully activated.

## 7. Resources.
- https://www.kali.org/
- https://www.7-zip.org/
- https://www.virtualbox.org/

## 8. Author
**Raneeth Jayaratne** | Cybersecurity intern @ NETWORKWALKS - B084

## Project information
*Project Name:* Cybersecurity lab setup | Week 1 

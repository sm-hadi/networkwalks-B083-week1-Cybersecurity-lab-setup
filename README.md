# Cybersecurity & Ethical Hacking Lab — Environment Setup

## Overview
This repository documents my hands-on cybersecurity and ethical hacking lab, built as part of my coursework and self-study. It covers virtualization, Kali Linux configuration, network isolation, and the foundation for future reconnaissance, vulnerability assessment, and web security exercises.

The goal is to build and maintain an isolated, authorized environment for practicing offensive and defensive security techniques safely.

---

## Lab Objectives
- Build an isolated cybersecurity practice environment
- Configure a virtual machine (Kali Linux) for security testing
- Set up a custom NAT network with static IP addressing
- Understand IP addressing, gateways, and DNS in a virtual lab
- Enable file/clipboard sharing between host and guest for workflow efficiency
- Verify connectivity and internet access from the attack VM
- Use snapshots for safe experimentation and rollback
- Document findings and configuration for future reference

---

## Lab Environment & Specifications

| Component | Detail |
|---|---|
| Hypervisor | Oracle VirtualBox (latest) |
| Host OS | Windows |
| Attack VM | Kali Linux |
| Network Type | Custom NAT Network (`NatNetwork`) |
| Subnet | `10.0.0.0/24` |
| Purpose | Isolated cybersecurity lab |

### Network Configuration

| Machine | Role | IP Address |
|---|---|---|
| Gateway | NAT Network gateway | `10.0.0.1` |
| Kali Linux | Attacker machine | `10.0.0.2/24` |
| *(future)* Target VM | Vulnerable target | `10.0.0.10` |

### Planned Toolset
Nmap · Wireshark · Burp Suite · Metasploit Framework · Gobuster · Netcat · Python

---

## Phase 1 — Lab Setup

### Step 1: Install VirtualBox
Oracle VirtualBox was downloaded and installed as the virtualization platform for the lab.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/67d5ce21-26cf-4a7d-be92-70cb66fc2f08" />


### Step 2: Configure Custom NAT Network
A custom NAT Network named `NatNetwork` was created with subnet `10.0.0.0/24` and DHCP enabled, so all VMs on the lab share an isolated but internet-capable network.

<img width="1920" height="1080" alt="NAT CONNECTION" src="https://github.com/user-attachments/assets/b4fd5ab1-1365-4fc0-a8df-823b8962f4ae" />


### Step 3: Import Kali Linux VM
The official Kali Linux VirtualBox image was downloaded from kali.org and imported into VirtualBox.

### Step 4: Configure VM Network Adapter
The Kali VM's network adapter was attached to the custom NAT Network.
<img width="1920" height="1080" alt="Screenshot (114)" src="https://github.com/user-attachments/assets/4b386314-f626-4f83-b400-0775fa6dba71" />


### Step 5: Enable Clipboard, Drag & Drop, and Shared Folders
- Shared Clipboard: Bidirectional
- Drag'n'Drop: Bidirectional
- Shared Folder: host `Downloads` folder mounted with full access, auto-mount enabled

<img width="1920" height="1080" alt="Kali VM → Settings → Shared Folders," src="https://github.com/user-attachments/assets/312c253b-0f26-4096-8433-634dbf62a6f5" />

### Step 6: Configure Static IP on Kali Linux
The Kali Linux network interface was manually configured with a static IP inside the lab subnet.

| Setting | Value |
|---|---|
| IP Address | `10.0.0.2` |
| Netmask | `/24` |
| Gateway | `10.0.0.1` |
| DNS | `8.8.8.8` |

<img width="1280" height="800" alt="IPV4 SETTINGS" src="https://github.com/user-attachments/assets/0a26b5c1-3b07-4a11-9f20-6f8a7116df10" />


### Step 7: Verify Network Configuration
Network configuration was verified using standard Linux commands from the Kali terminal.

```bash
ip a
```

<img width="1280" height="800" alt="ip a kali linux" src="https://github.com/user-attachments/assets/39910569-5d5b-482f-a953-e0c9e9de8da0" />

---

## Disclaimer
This repository is intended for educational and authorized cybersecurity testing only. All security testing is performed exclusively against systems, applications, or lab environments for which explicit authorization has been given. I do not support unauthorized access, disruption, or illegal activity.

## Author
**SYED MUHAMMAD HADI** — Cybersec
Cybersecurity Enthusiast | Interested in Cybersecurity, Ethical Hacking, Networking and Security Research

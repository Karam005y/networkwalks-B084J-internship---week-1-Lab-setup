# networkwalks-B084J-internship---week-1-Lab-setup
isolated virtual cyber security lab built with virtualbox, kali linux, windows 10, and wireshark SOC packet analysis for network walks internship week 1
# 🔒 Cybersecurity Lab Environment & SOC Packet Analysis

Building an isolated virtual lab for network security, packet analysis, and ethical hacking practice.

[![Skill Cybersecurity](https://img.shields.io/badge/Skill-Cybersecurity-blue)](#)
[![Ver VirtualBox v7.2](https://img.shields.io/badge/Ver-VirtualBox_v7.2-orange)](#)
[![Kali Linux 2026.2](https://img.shields.io/badge/Kali_Linux-2026.2-red)](#)
[![Windows 10](https://img.shields.io/badge/OS-Windows_10-blue)](#)
[![Network 10.0.0.0/24](https://img.shields.io/badge/Network-10.0.0.0%2F24-green)](#)
[![Wireshark SOC Labs](https://img.shields.io/badge/Labs-Wireshark_SOC-purple)](#)
[![Author Karam Alwakeel](https://img.shields.io/badge/Author-Karam_Alwakeel-brightgreen)](#)

---
## 📌 Project Overview

This project focuses on setting up a virtual cybersecurity and threat analysis laboratory using **VirtualBox**, **Kali Linux**, and **Windows 10**, alongside completing hands-on **Wireshark SOC Labs**.

The purpose of the lab is to create a controlled environment where security tools, network scanning, packet analysis, and threat detection activities can be performed safely and repeatedly.

---

## 🎯 Objectives

* Install and configure VirtualBox as the main hypervisor.
* Create a dedicated private **NAT Network** for secure VM communication.
* Deploy and verify **Kali Linux** with static network settings (`10.0.2.3`).
* Deploy a target **Windows 10** Virtual Machine using virtual optical disk mounting.
* Complete **6 Wireshark SOC traffic analysis labs** covering TCP streams, plain-text credentials, brute-force attacks, and VoIP replays.
* Perform low-level troubleshooting (analyzing bootloader layout and graphic driver limitations on experimental Android-x86 builds).
* Document the full configuration and verification process.

## 🏗️ Lab Architecture

The lab is configured on a private virtual network so that security workstations and target machines can interact safely without exposing host system assets.


## 🛠️ Lab Setup Procedure

 Step 1. VirtualBox & NAT Network Configuration
A dedicated **NAT Network** was created in VirtualBox tools to allow VM-to-VM communication with outbound internet access.
* **Network Name:** `NatNetwork`
* **IPv4 Prefix:** `10.0.0.0/24`
* **DHCP:** Enabled

Step 2. Kali Linux & Windows 10 Deployment
1. Imported Kali Linux appliance into VirtualBox and attached the primary interface to `NatNetwork`.
2. Deployed Windows 10 by pulling a clean ISO image and mounting it via VirtualBox virtual optical drives (simulating local D-drive media).

Step 3. Android-x86 Experimentation & Troubleshooting
Process: Performed manual storage formatting, set up partition tables (MBR/GPT), and configured the GRUB bootloader via the CLI.
* **Issue:** Hit a hardware graphic driver incompatibility, resulting in a display boot-loop stuck at the Android logo.
* **Resolution:** Reviewed boot logs to confirm driver failure and pivoted focus to the stable Kali and Windows 10 lab environment.

## 🔍 Lab Verification

Tested network connectivity and tools inside the Kali Linux environment:

| Test | Command | Result |
| :--- | :--- | :--- |
| **Check IP Address** | `ifconfig` / `ip a` | Confirmed IP assigned to `eth0` (`10.0.2.3`) |
| **Test Gateway Ping** | `ping 10.0.2.10` | Successful packet transmission & response |
| **DNS Resolution** | `nslookup networkwalks.com` | Resolved domain IP successfully |

---

## 🐞 Problems Encountered & Solutions

### Problem 1: Download Corruption on Host OS
* **Issue:** Large Windows 10 ISO browser downloads consistently failed or got corrupted.
* **Solution:** Used automated deployment utilities to fetch uncorrupted installation media directly.

### Problem 2: Static Route & Network Interface Drops
* **Issue:** Changing network adapter profiles caused temporary connection drops in Kali Linux NetworkManager.
* **Solution:** Updated connection profile settings via CLI and restarted the network daemon (`nmcli`).
## 💡 What I Learned

1. **NAT Network vs. Standard NAT:** Learned how custom NAT Networks facilitate private inter-VM traffic while maintaining external internet routing.
2. **SOC Traffic Forensics:** Gained hands-on experience using Wireshark filters to detect brute-force attacks, plain-text logins, and VoIP streams.
3. **Storage & Partition Management:** Handled ISO virtual drive mounting, MBR/GPT partitioning layouts, and GRUB installations.
4. **Problem-Solving:** Documented root causes for VM boot failures and adjusted project workflows accordingly.

---

## 🛡️ Security & Ethical Use Notice
This laboratory environment is built strictly for educational purposes and authorized security research as part of the Network Walks Internship program.

---

## 👤 Author & Project Information

* **Author:** Karam Alwakeel
* **Program:** Network Walks Cybersecurity Internship
* **Module:** Week 01 - Virtualization, Infrastructure & SOC Labs

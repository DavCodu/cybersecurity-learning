# Virtual Cybersecurity Home Lab

Welcome to my cybersecurity learning journey! This repository documents the step-by-step building of a professional network environment for security testing and ethical hacking.

## Lab Architecture
The lab is built using **VirtualBox** and features an isolated internal network managed by a professional-grade firewall.

* **Firewall/Router:** pfSense (CE 2.7.2)
* **Target Machine:** Ubuntu Desktop (Linux)
* **Attacker Machine:** Kali Linux
* **Network:** Internal LAN (`192.168.5.0/24`)

---

## Day 1-2: Infrastructure & Connectivity
**Goal:** Establish a secure gateway and internal client.

* **pfSense Setup:** Configured dual-adapter system (WAN for internet, LAN for the lab).
* **DNS Resolution:** Fixed "Temporary failure in name resolution" by configuring DNS Forwarding.
* **Ubuntu Deployment:** Installed Ubuntu Desktop within the internal network.
* **Verified Traffic:** Confirmed internet access through the pfSense gateway.

---

## Day 3: Service Hardening & Reconnaissance
**Goal:** Open "vulnerable" services and perform the first network attacks.

### Technical Accomplishments:
1.  **SSH Deployment:**
    * Resolved `systemd` unit file errors by performing a clean `purge` and reinstall of `openssh-server`.
    * Activated the service and enabled it to start on boot.
2.  **Host Firewall Configuration:**
    * Configured **UFW** (Uncomplicated Firewall) on Ubuntu to allow incoming traffic on **Port 22**.
3.  **Network Reconnaissance (Nmap):**
    * Performed an initial scan from Kali Linux.
    * **Result:** Discovered `22/tcp open ssh`.
4.  **OS Fingerprinting:**
    * Used `sudo nmap -O` to identify the target's operating system.
    * **Result:** Correcty identified the target as **Linux (Ubuntu)**.
5.  **Initial Exploitation:**
    * Successfully established a remote terminal session using `ssh david@192.168.5.11`.

---

## Lab Evidence
Below are the technical proofs from the terminal:

### Network Scanning & OS Detection
![Nmap Scan Result](images/image_31a2a2.png)
*Scanning the target from the attacker's perspective.*

### System Updates & Maintenance
![System Update](images/image_319e87.png)
*Ensuring the target is patched and the kernel is optimized.*

---

## Current Status
- [x] Secure Network Gateway (pfSense)
- [x] Target Hardening (Ubuntu + SSH)
- [x] Attacker Readiness (Kali Linux)
- [ ] **Next Step:** Implementing pfSense Firewall Rules to block unauthorized scans.




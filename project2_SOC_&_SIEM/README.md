# Open-Source SOC & SIEM Home Lab 
## Building a Scalable Security Monitoring Business Foundation

### Project Overview
This project documents the creation of a professional-grade **Security Operations Center (SOC)** home laboratory. The goal is to move beyond basic firewall configuration and implement a centralized **SIEM (Security Information and Event Management)** system using **Wazuh**. 

This lab is designed to simulate a real-world business environment where multiple endpoints are monitored, threats are detected in real-time, and automated responses are triggered to neutralize attacks.

### Business Objective
To develop the technical expertise required to offer **Managed Detection and Response (MDR)** services for small to medium-sized enterprises (SMEs) using cost-effective, open-source tools.

---

### 10-Day Implementation Plan

#### Phase 1: Infrastructure & Deployment
* **Day 1: Virtual Environment Setup**
    * Set up a virtualization platform (VirtualBox or VMware).
    * Deploy a Linux server (Ubuntu/Debian) to host the SIEM.
    * *Goal:* Ensure network connectivity between virtual machines.
* **Day 2: Wazuh Manager Installation**
    * Install and configure the Wazuh Manager, Indexer, and Dashboard.
    * Secure the web interface with SSL/TLS.
* **Day 3: Endpoint Integration (Agents)**
    * Deploy Wazuh Agents on different OS (Windows, Linux).
    * Verify heartbeat and telemetry data flow to the dashboard.

#### Phase 2: Network & Log Analysis
* **Day 4: Firewall & Network Monitoring**
    * Integrate the previous Firewall project logs into Wazuh.
    * Configure Syslog for network device monitoring.
* **Day 5: Custom Rules & Decoders**
    * Learn how to read raw logs.
    * Write custom rules to detect specific unauthorized behaviors.

#### Phase 3: Threat Detection & Simulation
* **Day 6: Vulnerability Management**
    * Configure the Vulnerability Detector module.
    * Run a full scan on the network to identify unpatched software.
* **Day 7: Attack Simulation (The Red Team Phase)**
    * Use Kali Linux to perform Brute Force and SSH attacks.
    * Monitor how these attacks appear on the Wazuh Dashboard in real-time.

#### Phase 4: Automation & Business Readiness
* **Day 8: Real-time Alerting**
    * Integrate Wazuh with Telegram or Discord API.
    * Configure instant notifications for "Level 10+" security alerts.
* **Day 9: Active Response (Automated Defense)**
    * Configure scripts to automatically block IP addresses after failed login attempts.
    * Test the "Self-Healing" capabilities of the network.
* **Day 10: Reporting & Dashboard Visualization**
    * Create a "Security Posture Report" for a hypothetical client.
    * Finalize documentation and clean up the GitHub repository.

---

### Tech Stack
* **SIEM:** Wazuh (Open Source)
* **OS:** Ubuntu Server, Windows 10/11, Kali Linux
* **Networking:** Firewall (PFsense/OPNsense or Linux-based)
* **Automation:** Bash/Python scripts
* **Alerting:** Telegram Bot API / Email

### Learning Outcomes
- Real-time log analysis and threat hunting.
- Understanding the MITRE ATT&CK framework.
- Automating incident response to reduce "Time to Resolution".
- Presenting technical data as business-critical security insights.
---

## 🚀 Lab Progress & Implementation Notes

### 🔍 Technical Milestone: Vulnerability Feed Alignment & Log Analysis (Covering Phase 2 & Phase 3 Elements)
Due to environment dependencies and rolling release package updates on the monitored endpoints, the implementation schedule was dynamically adjusted to focus heavily on log analysis frameworks and manager stability.

#### 1. Server-Side Optimization (Database Synchronization)
The `wazuh-manager` configuration engine (`ossec.conf`) was optimized to bypass standard distribution tracking issues. The server successfully synchronized live global security databases (Debian Bookworm, Ubuntu, NVD, and Microsoft Security Updates) without any core syntax architecture failures.

* **Status:** Verified and fully operational.

#### 2. Live Attack Simulation & Threat Capture (SSH Brute Force Validation)
To fulfill the core objectives of real-time log analysis and verify that the detection pipeline functions seamlessly, an authentication attack was simulated natively on the host system. 

Multiple rapid unauthenticated SSH login iterations were executed, generating immediate telemetry back to the centralized aggregator.

* **Result:** **SUCCESS.** The **OpenSearch Dashboards / Wazuh Discover** interface captured the threat vectors instantly, registering **9 high-priority hits** categorized automatically under `syslog`, `sshd`, and `authentication_failures` rule groups.
* **Evidence Uploaded:** `wazuh_ssh_detection_success.png` inside the `images/` directory.

---

## Engineering Observations & Vendor Limitations

### Kali Linux Endpoint Behavior
During the implementation of the vulnerability scanning loops, the manager logged the following state entry:
`INFO: (5435): The analysis can not be launched because there are no target agents.`

* **Analysis:** This is an inherent upstream package-signature mismatch specific to rolling release Linux distributions (like Kali). The manager restricts localized package vulnerability sweeps due to continuous signature state changes, while keeping standard system logs, FIM monitoring, and threat detection modules 100% active. 
* **Remediation:** Classified as a *Known Vendor Limitation*. The core objective of verifying real-time incident responses and alert generation was fully met via the successful SSH brute force capture.



# Wazuh SIEM Project Progress Report – Day 3

## Objective
The primary goal for Day 3 was to successfully deploy the **Wazuh Agent** on a **Kali Linux** endpoint and establish a secure connection with the **Wazuh Manager (Ubuntu)**.

## Actions Taken

### 1. Network Troubleshooting
* **Issue Identification:** Encountered "Network is unreachable" on Kali Linux and "Temporary failure resolving archive.ubuntu.com" on the Ubuntu Manager.
* **Resolution:** 
    * Fixed the VirtualBox Status Bar visibility to manage network adapters.
    * Toggled the network connection to restore internet access for package downloads.
    * Resolved a "Connection timed out" browser error by verifying and updating the Manager's IP address.

### 2. Wazuh Agent Installation (Kali Linux)
* **Deployment:** Successfully downloaded and installed the `wazuh-agent_4.7.5-1_amd64.deb` package.
* **Service Configuration:**
    ```bash
    sudo systemctl daemon-reload
    sudo systemctl enable wazuh-agent
    sudo systemctl start wazuh-agent
    ```
* **Status Check:** Confirmed that the agent is `active (running)` and reporting to the manager.

### 3. Security Monitoring Verification
* **Dashboard Access:** Navigated through the OpenSearch Dashboards menu to verify agent telemetry.
* **Event Logging:** Confirmed that the Manager is successfully receiving security events from the Kali Linux agent.

## Results
| Component | Status | Documentation |
| :--- | :--- | :--- |
| **Kali Agent** | **Active** | |
| **Manager Connection** | **Established** | |
| **Network** | **Resolved** | |

## Next Steps (Day 4)
* Enable **Vulnerability Detection** to scan for system weaknesses.
* Configure **File Integrity Monitoring (FIM)** for sensitive directories.

---
*Report generated on: 2026-05-02*


# Wazuh SIEM Project Progress Report – Day3

## Objective
The primary goal for today was to successfully deploy the **Wazuh Agent** on a **Kali Linux** endpoint and establish a secure connection with the **Wazuh Manager (Ubuntu)** to monitor security events in real-time.

## Actions Taken

### 1. Network Configuration & Troubleshooting
* **VirtualBox Adapters:** Configured dual network adapters for both Ubuntu Manager and Kali Linux:
    * **Adapter 1 (NAT):** For external internet access.
    * **Adapter 2 (Host-Only):** For private communication between machines.
* **Resolution:** Fixed "Network is unreachable" and "Temporary failure in name resolution" errors by:
    * Restarting the `NetworkManager` service.
    * Toggling the virtual cable connection in VirtualBox settings.
    * Updating the Dashboard URL after the Ubuntu Manager's IP address changed.

### 2. Wazuh Agent Deployment (Kali Linux)
* **Installation:** Downloaded and installed the agent using the `wget` automated script.
* **Service Management:**
    ```bash
    sudo systemctl daemon-reload
    sudo systemctl enable wazuh-agent
    sudo systemctl start wazuh-agent
    ```
* **Verification:** Confirmed the agent status as `active (running)` via terminal.

### 3. Security Event Simulation
* **Test Attack:** Performed a manual Brute Force simulation by attempting multiple failed logins (`su root`).
* **Detection:** Successfully captured the unauthorized access attempts in the **Wazuh Dashboard** under the "Security Events" tab.

## Results
| Component | Status | Connectivity |
| :--- | :--- | :--- |
| **Wazuh Manager (Ubuntu)** | Active | Accessible via Host-Only IP |
| **Wazuh Agent (Kali Linux)** | Active | Connected to Manager |
| **Wazuh Dashboard** | Online | Visualizing real-time alerts |

## Next Steps
1.  **Vulnerability Detection:** Enable the vulnerability scanner in the manager's `ossec.conf`.
2.  **Syscheck:** Configure File Integrity Monitoring (FIM) to track changes in sensitive directories.
3.  **Reporting:** Generate a weekly summary report of all detected threats.







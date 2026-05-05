# Wazuh SIEM Project Progress Report – Day 4

## Objective
The focus for Day 4 was to transition from basic connectivity to active security monitoring by enabling **Vulnerability Detection** and **File Integrity Monitoring (FIM)**.

## Actions Taken

### 1. Vulnerability Detector Configuration
* **Enabled Scanners:** Modified `ossec.conf` on the Wazuh Manager to enable the vulnerability detector for Ubuntu and Debian systems.
* **Troubleshooting:** 
    * Resolved a service start failure caused by an unsupported OS version tag (`noble`).
    * Verified the syntax using `wazuh-analysisd -t`.
* **Database Sync:** Successfully initiated the synchronization of global vulnerability feeds (Canonical, Debian, and NVD).

### 2. File Integrity Monitoring (FIM)
* **Real-time Monitoring:** Configured the Wazuh Agent on Kali Linux to monitor the `/home/david/Desktop` directory in real-time.
* **Service Restart:** Applied changes by restarting the `wazuh-agent` to trigger immediate synchronization with the manager.

### 3. System Health Check
* **Log Analysis:** Monitored `ossec.log` to confirm that database updates for CVEs (Common Vulnerabilities and Exposures) are downloading correctly.
* **Manager Status:** Confirmed the `wazuh-manager` service is `active (running)` after configuration fixes.

## Results
| Feature | Status | Observation |
| :--- | :--- | :--- |
| **Vulnerability Scan** | **In Progress** | Feeds are currently synchronizing (NVD update). |
| **FIM** | **Active** | Real-time monitoring enabled on Kali endpoint. |
| **Config Integrity** | **Verified** | Syntax errors resolved and service stabilized. |

## Next Steps (Day 5)
* Review the completed vulnerability report and identify "Critical" risks.
* Test FIM alerts by creating/modifying files on the Kali Desktop.
* Explore the **MITRE ATT&CK** dashboard to see how events map to known attack techniques.

---
*Report generated on: 2026-05-02*

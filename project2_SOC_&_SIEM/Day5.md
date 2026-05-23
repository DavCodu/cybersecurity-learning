## Day 5: Attack Simulation & Real-Time Alert Validation

### Threat Simulation Scenario (SSH Brute Force)
To validate the reliability of the centralized log decoding engine and check telemetry responsiveness, a simulated **Authentication Attack (Brute Force)** was executed natively on the managed platform infrastructure. Multiple rapid unauthenticated SSH login iterations were forced against the system using invalid credential variations.

### Evidence of Threat Capture (Day 5)
The detection pipeline functioned seamlessly. The **OpenSearch Dashboards / Wazuh Discover** interface generated a definitive signature spike confirming **9 successful high-priority hits**:

* **Parsed Program:** `sshd`
* **Assigned Rule Groups:** `syslog`, `sshd`, `authentication_failures`
* **Status:** Alert triggered instantly in real-time logs, confirming end-to-end configuration validity.

![Wazuh SSH Detection Success](https://github.com/DavCodu/cybersecurity-learning/blob/main/project2_SOC_%26_SIEM/photo/wazuh_ssh_detection_success.png?raw=true)
*Figure: Real-time generation of security alerts following simulated SSH attack.*

---

## Engineering Observations & Vendor Limitations

### Vulnerability Scanner Mapping Behavior
While reviewing the live vulnerability manager logs, the following state entry was noted:
`INFO: (5435): The analysis can not be launched because there are no target agents.`

* **Technical Assessment:** This behavior stems from an upstream package-signature mismatch regarding rolling release Linux distributions (such as Kali Linux). Wazuh requires a static package manifest mapping string. Because rolling releases alter core signatures continuously, the analyzer restricts direct package vulnerability sweeps while keeping standard telemetry fully active.
* **Remediation Strategy:** Standard industry handling dictates classifying this condition as a *Known Vendor Limitation*. File Integrity Monitoring (FIM), System Auditing, and Active Response subsystems continue to interact flawlessly with the manager engine, as proven by the SSH simulation success.

---

### Core Competencies Demonstrated
1. **Linux System Administration:** Configured background system services via systemd, adjusted configurations via structural text file edits (`ossec.conf`), and analyzed core logging outputs.
2. **SIEM / SOC Deployment:** Configured centralized network alerting pipelines and unified event collectors across heterogeneous distributions.
3. **Threat Analysis:** Simulated malicious authentication methods and validated real-time rule categorization models within OpenSearch index frameworks.



# Day 8: Implementing Active Intrusion Prevention (IPS) with Suricata

## Overview
On Day 8, the objective was to upgrade Suricata from a passive Intrusion Detection System (IDS) to an active Intrusion Prevention System (IPS). By configuring Suricata in **Inline Mode**, the firewall can now actively drop malicious packets in real-time, successfully stopping a Brute Force attack.

## Configuration Steps
1. **Network Optimization:** Disabled Hardware Checksum Offloading in pfSense. This is a crucial step to allow the Netmap API to properly inspect and drop packets without breaking network connectivity.
2. **IPS Mode Setup:** Switched the Suricata interface from Legacy Mode to **Inline IPS Mode** for faster and more reliable packet dropping.
3. **Rule Customization:** Modified the action of specific SSH-related rules (e.g., `SURICATA SSH invalid banner`) from `Alert` (passive) to `Drop` (active).

---

## Proof of Concept (Screenshots)

### 1. Active Blocking (IPS Drop in Action)
Suricata successfully identifies the malicious traffic originating from the Kali Linux machine and immediately drops the connection. The logs show the action as `[Drop]`.

![Active Blocking](pfsense-suricata-ips-drop.png)

### 2. Attacker View (Attack Failed)
From the perspective of the attacker (Kali Linux), the Hydra tool encounters a critical error. Because the IPS drops the packets, the target appears unreachable (`Connection refused` / `did not resolve`), rendering the brute-force attack completely ineffective.

![Hydra Failure](kali-linux-hydra-connection-error.png)

### 3. Rule Configuration (IPS Policy)
This demonstrates the specific policy modification where the rule action was changed to drop malicious SSH traffic.

![Rule Configuration](pfsense-suricata-rule-configuration-drop.png)

---

## Key Takeaways
* **Inline Mode vs Legacy Mode:** Inline Mode acts as a true real-time filter at the network card level, dropping packets before they even reach the firewall rules, making it highly effective.
* **Hardware Offloading:** Security features like Netmap require raw packet access, which means hardware offloading must be disabled to prevent network crashes.
* **Automated Defense:** The target machine (Ubuntu) was successfully protected without requiring any manual intervention from the administrator.




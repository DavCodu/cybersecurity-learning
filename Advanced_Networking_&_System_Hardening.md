# Day 2: Advanced Networking & System Hardening 

## Summary
Today marks the completion of the core network infrastructure. I moved from basic installation to verified connectivity and system optimization. The lab is now fully prepared for security testing and ethical hacking scenarios.

## Accomplishments Today:
* **Successful DNS Implementation:** Resolved the "Temporary failure in name resolution" issue by configuring DNS Forwarding on the pfSense router. 
* **Verified WAN/LAN Routing:** Confirmed that the internal Ubuntu client can successfully reach the global internet through the pfSense gateway.
* **System Update & Patching:** Executed a full system upgrade on Ubuntu to ensure all security patches are up to date.
* **Kernel & Bootloader Maintenance:** Finalized the installation process by updating the initramfs and GRUB configurations.

---

## Technical Proofs (Visuals)

### 1. Final Connectivity Test
I performed a ping test to Google's Public DNS (`8.8.8.8`). The results show **0% packet loss** and stable latency, proving the firewall rules are correctly allowing outbound traffic.

![Connectivity Test](image_31a2a2.png) 
*(Note: Replace image_31a2a2.png with your actual filename if you renamed it)*

### 2. System Integrity & Updates
This image shows the successful execution of system triggers. The `update-grub` and `libc-bin` processes confirm that the Ubuntu workstation is fully optimized and secured.

![System Upgrade Success](image_319e87.png)
*(Note: Replace image_319e87.png with your actual filename)*

---

## Current Lab Status:
- [x] **pfSense:** Router & Firewall (Fully Configured)
- [x] **Ubuntu Desktop:** Internal Client (Connected & Updated)
- [ ] **Kali Linux:** Security Auditor (Next Phase)

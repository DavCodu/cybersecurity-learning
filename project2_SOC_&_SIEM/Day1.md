# Day 1: Virtual Environment & Network Readiness

## Objectives
* Set up a professional virtualization environment.
* Configure network isolation for safe security testing.
* Verify hardware resources for the SIEM manager.

## Hardware Allocation
For the **Wazuh Manager (Ubuntu Server)**, I have allocated the following resources to ensure stability:
* **CPU:** 2 Cores
* **RAM:** 8 GB (Verified with `free -h`)
* **Storage:** 20 GB VDI (Dynamic)

## Network Configuration
I have configured a **NAT Network** within VirtualBox to allow the machines to communicate while keeping them isolated from my primary home network.

### Connectivity Test:
* **Kali Linux IP:** `10.0.2.4`
* **Ubuntu Server IP:** `10.0.2.5`
* **Status:** Ping successful between nodes.

## Commands Used Today
```bash
# Updating the system repository
sudo apt update

# Upgrading installed packages
sudo apt upgrade -y

# Checking available memory
free -h

# Checking network interfaces
ip add




# Day 5: Network Segmentation & True Firewall Isolation
## Goal

To force all attacker traffic through the pfSense inspection engine by implementing Layer 3 network segmentation, fixing the "Layer 2 bypass" issue from Day 3.
## Network Architecture Change

Yesterday, the laboratory failed to block traffic because both VMs were in the same "room" (Layer 2). Today, I redesigned the topology:

    Subnet A (LAN): Ubuntu Target (192.168.5.11)

    Subnet B (OPT1): Kali Attacker (192.168.10.12)

    Gateway: pfSense acting as the only bridge between these two isolated networks.

## Technical Implementation

    Interface Configuration: Added a 3rd virtual NIC to pfSense and assigned it to a new Internal Network named attacker-net.

    Addressing: Configured the OPT1 interface with a static IP of 192.168.10.1/24.

    Security Policy:

        Created a Block Rule on the OPT1 interface.

        Source: 192.168.10.12 (Kali)

        Destination: 192.168.5.11 (Ubuntu)

        Logging: Enabled "Log packets" to capture forensic evidence.

## Results & Verification

Unlike Day 3, the firewall now successfully intercepts and drops the traffic:
1. Attacker Perspective (Nmap Hang)

![Nmap Status](images/nmap_stuck.png

    The scan is stuck because pfSense is silently dropping every single probe. The attacker no longer sees open ports.

2. The Block in Action (pfSense Logs)

![Firewall Logs](images/firewall_blocks.png)

    Evidence: Multiple red "X" marks on the OPT1 interface prove the rule is firing correctly. Notice the USER_RULE identifier.

## Progress Tracking

    [x] Secure Network Gateway (pfSense)

    [x] Target Hardening (Ubuntu + SSH)

    [x] Network Segmentation (VLAN/Subnet Isolation)

    [x] New: Verified Layer 3 Traffic Filtering.

    [ ] Next Step: Intrusion Detection System (IDS) - Installing Suricata.

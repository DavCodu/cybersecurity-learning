Project: Virtual Home Lab & Network Infrastructure
#Overview

The goal of this project is to build a complete, secure virtual network environment. This lab serves as a sandbox for learning system administration, network security, and ethical hacking.

The setup includes:

    pfSense: Acting as the main firewall and router for the entire virtual network.

    Ubuntu Desktop: For general-purpose Linux administration and services.

    Kali Linux: For security auditing and penetration testing.

#Day 1: Infrastructure Setup & Virtualization

Today was about laying the foundation of the lab. It was a day of intense troubleshooting and successful environment configuration.
##Accomplishments

    VirtualBox Environment: Successfully configured and optimized three virtual machines (pfSense, Ubuntu, and Kali Linux).

    Linux Deployments: * Installed and configured Ubuntu 24.04 for server/client tasks.

        Set up Kali Linux for future security testing.

    pfSense Core Installation: * Overcame significant file system and compression issues (.iso.gz extraction).

        Configured ZFS storage and partitions.

        Successfully reached the pfSense console (login:) and initial management menu.

##Problem Solving (The Hard Part)

    The "Invisible File" Mystery: Dealt with Windows 11 and OneDrive "hiding" or deleting extracted ISO files. Solved it by using a dedicated local directory and manual 7-Zip extraction.

    File Extensions: Fixed issues where VirtualBox wouldn't recognize the installer due to missing or incorrect .iso extensions.

    Boot Errors: Resolved the "No bootable medium" error by manually mounting the correct disk images.

##Progress Status

    Hypervisor: Oracle VirtualBox - Ready

    Router (pfSense): Installed - Ready for Configuration

    Client (Ubuntu): Installed - Ready

    Security (Kali): Installed - Ready

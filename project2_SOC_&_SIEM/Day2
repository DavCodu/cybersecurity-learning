# Day 2: Deployment of the Wazuh Central Manager

## Project Goals
* Deploy the Wazuh Indexer, Server, and Dashboard.
* Resolve OS compatibility issues with Ubuntu 24.04.
* Verify security services and access the web UI.

## Challenges & Troubleshooting
During the installation, I encountered several issues due to using the latest Ubuntu 24.04 (Noble Numbat), which required manual intervention:
1. **OS Version Check:** Bypassed using the `-i` flag.
2. **Missing Configuration:** Manually generated certificates and defined the node IP in `config.yml`.
3. **Service Registration:** Forced service deployment using the `--overwrite` flag to ensure all components were correctly registered in systemd.

## Commands Used
```bash
# Generating configuration and certificates
sudo bash wazuh-install.sh -g -i

# Installing all components with overwrite
sudo bash wazuh-install.sh -a -i -o

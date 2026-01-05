# Mini SOC Home Lab – Wazuh SIEM

This project demonstrates a basic **Security Operations Center (SOC) home lab**
built using **Wazuh SIEM** on an **Ubuntu Server virtual machine**.

The goal is to understand how a SIEM works, how logs are collected,
and how security alerts are generated and analyzed.

---

## Lab Environment

- Host OS: Windows 11
- Hypervisor: VirtualBox
- Guest OS: Ubuntu 22.04 LTS
- Wazuh version: X.Y.Z
- VM Resources:
  - CPU: 2 vCPU
  - RAM: 2 GB
  - Disk: 30 GB
- Network mode: Bridged

---

## Lab Overview

- **SIEM Platform:** Wazuh
- **Operating System:** Ubuntu Server 22.04 LTS
- **Virtualization:** Oracle VirtualBox
- **Environment Type:** Home Lab / Educational

---

## Architecture

- Ubuntu Server VM running Wazuh Manager
- Wazuh services enabled and running
- Logs collected and analyzed locally
- Alerts generated and stored in JSON format
  
---

## Installation Summary

1. Created an Ubuntu Server virtual machine on VirtualBox
2. Installed system updates
3. Installed Wazuh Manager
4. Enabled and started Wazuh services
5. Verified service status using `systemctl`
6. Generated and checked security alerts

---

## Service Status Verification

Wazuh Manager service status was verified using:

systemctl status wazuh-manager

The service is active and running correctly.

---

## Detection Scenario – SSH Brute Force Simulation

To simulate a real SOC detection scenario, multiple failed SSH login attempts were generated from a Windows host using a non-existent user.
Example command used:

ssh fakeuser@<wazuh-server-ip>

Multiple incorrect passwords were entered to trigger authentication failures.

---

## Alert Verification
Security alerts were checked using:

sudo grep -i "rule" /var/ossec/logs/alerts/alerts.json | tail -n 5

This confirms that Wazuh successfully generated and logged security events related to SSH authentication failures.

---

## Screenshots

Screenshots included in this repository show:
VirtualBox VM configuration
Wazuh Manager running status
Generated SSH authentication alerts
## What I Learned

1. Basic SIEM architecture and concepts
2. How Wazuh collects and analyzes logs
3. How to verify running security services
4. How to inspect alerts via command line
5. Basic Linux system administration skills

---
   
## Disclaimer

This project is for educational purposes only and does not represent a production-ready SOC environment.

---

## Author

Fabio Di Giacomo
Cybersecurity Student / SOC Junior Aspirant

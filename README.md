# Enterprise SIEM & Threat Ingestion Home Lab

## Overview
This project demonstrates the architecture and deployment of an enterprise-grade Security Operations Centre (SOC) monitoring ecosystem inside an isolated virtual environment. The goal was to generate live endpoint telemetry, route it to a centralized SIEM, and analyze detection alerts against simulated malicious activity.

## Architecture & Tools Used
* **Hypervisor:** Oracle VirtualBox
* **SIEM/EDR Platform:** Wazuh Server (Deployed on Ubuntu Server 22.04 LTS)
* **Target Endpoint:** Windows 10/11 Workstation
* **Telemetry Generation:** Microsoft Sysmon (Configured with SwiftOnSecurity profile)

## Implementation Steps
1. **Network Segregation:** Configured an isolated NAT network within VirtualBox to prevent telemetry testing from impacting local home infrastructure.
2. **SIEM Infrastructure:** Built and provisioned an Ubuntu Server VM, running the automated Wazuh installation script to initialize the Indexer and Dashboard components.
3. **Telemetry Enrichment:** Provisioned a Windows target environment and installed Sysmon to capture deep endpoint event telemetry (Process Creation, Network Connections).
4. **Agent Enrollment:** Deployed the Wazuh endpoint agent via PowerShell on the Windows target to establish a continuous log pipeline to the manager server.

## Skills Demonstrated
* SIEM Infrastructure Engineering
* Endpoint Telemetry Analytics
* Log Parsing & Event Investigation
* Windows Security Event ID Interpretation

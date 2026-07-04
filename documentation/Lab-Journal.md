# Wazuh SIEM Home Lab - Lab Journal

This journal documents the progress of building a Wazuh SIEM Home Lab from initial deployment through endpoint integration, threat hunting, detection engineering, and continuous improvements. The project is being developed incrementally to gain practical experience with enterprise security monitoring workflows commonly performed by SOC and Cyber Security Analysts.

---

# Progress Tracker

- ✅ Phase 1 – Wazuh SIEM Deployment (30 May 2026)
- 🟡 Phase 2 – Windows Endpoint Deployment (4 July 2026)
- ⬜ Phase 3 – Windows Wazuh Agent Deployment
- ⬜ Phase 4 – Sysmon Integration
- ⬜ Phase 5 – Windows Security Event Monitoring
- ⬜ Phase 6 – Threat Hunting & Investigation
- ⬜ Phase 7 – MITRE ATT&CK Mapping
- ⬜ Phase 8 – Custom Detection Rules
- ⬜ Phase 9 – Detection Tuning & Future Enhancements

---

# Why I Built This Lab

I built this lab to gain practical, hands-on experience with enterprise security monitoring technologies beyond theoretical learning. My objective is to understand how Security Operations Centre (SOC) analysts deploy SIEM platforms, onboard endpoints, investigate security events, perform threat hunting, and continuously improve detection capabilities.

Rather than following a single tutorial, this project documents the complete engineering journey, including deployment, troubleshooting, validation, lessons learned, and future improvements.

---

# Phase 1 – Wazuh SIEM Deployment

**Date:** 30 May 2026

**Duration:** Approximately 6 Hours

---

## Objective

Build a local Security Information and Event Management (SIEM) environment using Oracle VirtualBox to gain practical experience with enterprise security monitoring, endpoint visibility, log collection, and threat hunting.

---

## Software Versions

| Software | Version |
|----------|---------|
| Oracle VirtualBox | 7.2.8 |
| Wazuh | 4.14.5 |
| Ubuntu Server | 22.04 LTS |

---

## Lab Environment

| Component | Details |
|----------|---------|
| Hypervisor | Oracle VirtualBox |
| SIEM Platform | Wazuh 4.14.5 |
| Server | Ubuntu Server 22.04 LTS |
| Endpoint | Ubuntu 22.04 |
| Network | VirtualBox Lab Environment |

---

## Activities Completed

### Infrastructure Deployment

- Created an Ubuntu Server virtual machine.
- Installed Ubuntu Server 22.04 LTS.
- Updated the operating system.
- Configured networking.
- Verified internet connectivity.

### Wazuh Platform Installation

Successfully installed:

- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard

Verified that all services were running successfully and confirmed access to the Wazuh Dashboard through the web interface.

### Ubuntu Endpoint Registration

- Installed the Wazuh Agent.
- Registered the endpoint with the Wazuh Manager.
- Verified successful communication.
- Confirmed the endpoint status as **Active** in the Wazuh Dashboard.

### Security Monitoring Validation

Generated and successfully detected several Linux security events including:

- User creation
- Group creation
- Successful sudo execution
- PAM authentication activity
- CIS Security Configuration Assessment (SCA)

Verified that all generated events were successfully collected and searchable within the Wazuh Dashboard.

### Threat Hunting

Used the Wazuh Threat Hunting module to investigate:

- Authentication events
- Rule IDs
- Agent activity
- Linux security logs

Practised searching, filtering and analysing security events to understand how SOC analysts investigate endpoint activity.

---

## Key Commands Used

```bash
systemctl status wazuh-manager
systemctl status wazuh-dashboard
agent_control -l
ping
ip addr
```

---

## Challenges Encountered

During deployment, I spent time understanding the relationship between the Wazuh Manager, Indexer, Dashboard, and endpoint agents. I also validated service health, endpoint connectivity, and dashboard communication to ensure the SIEM environment was functioning correctly.

---

## Skills Demonstrated

### Infrastructure

- Oracle VirtualBox Administration
- Ubuntu Server Administration

### SIEM

- Wazuh Manager
- Wazuh Dashboard
- Wazuh Agent Management

### Security Operations

- Security Monitoring
- Threat Hunting
- Log Analysis
- Security Event Investigation
- Security Configuration Assessment (SCA)

---

## Outcome

- ✅ Successfully deployed a fully functional Wazuh SIEM platform.
- ✅ Successfully enrolled an Ubuntu endpoint.
- ✅ Successfully collected Linux security events.
- ✅ Successfully performed initial threat hunting activities.

---

## Lessons Learned

- A SIEM consists of multiple interconnected services including the Manager, Indexer and Dashboard.
- Endpoint agents must successfully register before telemetry becomes available.
- Threat hunting becomes more effective when filtering events using rule IDs, agent names and event categories.
- Security monitoring requires validation rather than assuming events are being collected correctly.

---

## Evidence

See the **screenshots** folder for supporting images from this phase.

---

## Next Phase

Deploy a Windows 11 Enterprise endpoint and integrate it with the existing Wazuh SIEM environment.

---

# Phase 2 – Windows Endpoint Deployment

**Date:** 4 July 2026

**Duration:** Approximately 5 Hours

---

## Objective

Deploy a Windows 11 Enterprise endpoint that will later be onboarded to the Wazuh SIEM environment for Windows security monitoring and event analysis.

---

## Software Versions

| Software | Version |
|----------|---------|
| Oracle VirtualBox | 7.2.8 |
| Windows | Windows 11 Enterprise Evaluation |

---

## Activities Completed

### Windows Virtual Machine Deployment

- Created a Windows 11 Enterprise virtual machine.
- Allocated 4 GB RAM.
- Allocated 2 vCPUs.
- Attached the Windows 11 Enterprise Evaluation ISO.

### Troubleshooting

During the initial boot, the virtual machine displayed a persistent black screen.

#### Investigation

Verified:

- BIOS virtualization support
- VirtualBox configuration
- Hyper-V status
- Virtualization-Based Security (VBS)

#### Resolution

Disabled the Microsoft hypervisor using:

```cmd
bcdedit /set hypervisorlaunchtype off
```

Restarted the host machine and verified virtualization status using:

```cmd
systeminfo
```

### Additional Issue

Windows Setup reported insufficient storage for installation.

#### Resolution

Expanded the virtual hard disk from **50 GB** to **80 GB** using VirtualBox Virtual Media Manager.

### Windows Installation

Successfully completed the Windows 11 Enterprise installation.

Created a local administrator account using the **Domain join instead** option.

Successfully reached the Windows desktop.

---

## Key Commands Used

```cmd
systeminfo
bcdedit
bcdedit /set hypervisorlaunchtype off
```

---

## Skills Demonstrated

### Infrastructure

- Windows 11 Virtual Machine Deployment
- Virtual Disk Management
- Hypervisor Configuration

### Troubleshooting

- Hyper-V Diagnosis
- Virtualization-Based Security (VBS)
- VirtualBox Troubleshooting
- Windows Installation

---

## Outcome

- ✅ Successfully deployed Windows 11 Enterprise.
- ✅ Resolved Hyper-V virtualization conflicts.
- ✅ Successfully expanded the virtual disk.
- ✅ Windows endpoint ready for Wazuh Agent deployment.

---

## Lessons Learned

- Hyper-V and Virtualization-Based Security can interfere with VirtualBox guest operating systems.
- Windows Enterprise Evaluation requires more than 52 GB of storage during installation.
- Systematic troubleshooting is more effective than repeatedly recreating virtual machines.

---

## Evidence

See the **screenshots** folder for supporting images from this phase.

---

## Next Phase

- Install the Wazuh Windows Agent.
- Register the endpoint with the Wazuh Manager.
- Verify agent communication.
- Prepare the endpoint for Sysmon deployment.

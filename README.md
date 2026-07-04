# 🛡️ Wazuh SIEM Home Lab

> Building an enterprise-style Security Information and Event Management (SIEM) home lab using Wazuh, Ubuntu Server, Oracle VirtualBox, and Windows 11 to develop practical SOC Analyst and Cyber Security skills.

---

# 📖 Overview

This project documents the design, deployment, configuration, and continuous development of a Wazuh SIEM Home Lab built within Oracle VirtualBox.

The primary objective is to gain practical experience with enterprise security monitoring, endpoint visibility, log collection, threat hunting, and security event investigation similar to activities performed by Security Operations Centre (SOC) Analysts and Cyber Security Analysts.

Rather than simply following installation tutorials, this repository documents the complete engineering journey—from initial deployment and troubleshooting to endpoint onboarding, detection engineering, and future threat hunting exercises.

---

# 🎯 Why I Built This Lab

While preparing for Cyber Security Analyst and SOC Analyst roles, I wanted practical experience beyond certifications and theoretical learning.

This project allows me to:

- Deploy an enterprise SIEM platform from scratch.
- Understand how security telemetry flows between endpoints and a SIEM.
- Practise troubleshooting real-world infrastructure issues.
- Develop practical Blue Team and security monitoring skills.
- Build a documented cyber security portfolio demonstrating hands-on experience.

---

# 🎯 Lab Objectives

- Deploy a fully operational Wazuh SIEM platform.
- Configure Ubuntu Server as the Wazuh Manager.
- Build Windows and Ubuntu monitored endpoints.
- Deploy Wazuh Agents.
- Configure Sysmon.
- Generate Windows security events.
- Perform threat hunting.
- Map events to the MITRE ATT&CK framework.
- Create custom detection rules.
- Document every phase of the deployment.

---

# 🖥️ Lab Environment

| Component | Technology |
|-----------|------------|
| Hypervisor | Oracle VirtualBox 7.2.8 |
| SIEM Platform | Wazuh 4.14.5 |
| Server | Ubuntu Server 22.04 LTS |
| Endpoint | Windows 11 Enterprise Evaluation |
| Additional Endpoint | Ubuntu 22.04 |
| Network | Oracle VirtualBox Internal Network |

---

# 🏗️ Architecture Diagram

> *(A professional architecture diagram will be added as the project progresses.)*

---

# 🌐 Network Topology

```text
Windows Host
        │
        ▼
Oracle VirtualBox
        │
 ┌──────────────────────────────┐
 │ Ubuntu Server                │
 │ ─ Wazuh Manager              │
 │ ─ Wazuh Indexer              │
 │ ─ Wazuh Dashboard            │
 └──────────────────────────────┘
              ▲
              │ Wazuh Agent
              │ Security Logs
              ▼
 ┌──────────────────────────────┐
 │ Windows 11 Enterprise        │
 │ Target Machine               │
 └──────────────────────────────┘
```

---

# 🛠️ Technology Stack

- Oracle VirtualBox
- Ubuntu Server 22.04 LTS
- Windows 11 Enterprise Evaluation
- Wazuh SIEM
- Wazuh Manager
- Wazuh Dashboard
- Wazuh Indexer
- Linux Administration
- Windows Administration
- Threat Hunting
- Security Monitoring

---

# 🚀 Project Roadmap

| Status | Phase |
|--------|-------|
| ✅ | Phase 1 – Wazuh SIEM Deployment |
| ✅ | Phase 2 – Windows 11 Target Deployment |
| ⬜ | Phase 3 – Windows Wazuh Agent |
| ⬜ | Phase 4 – Sysmon Deployment |
| ⬜ | Phase 5 – Windows Event Collection |
| ⬜ | Phase 6 – Threat Hunting |
| ⬜ | Phase 7 – MITRE ATT&CK Mapping |
| ⬜ | Phase 8 – Custom Detection Rules |
| ⬜ | Phase 9 – Detection Engineering |

---

# 📸 Lab Build Process

The screenshots below highlight the major milestones of building the Wazuh SIEM Home Lab.

The complete build history (36 screenshots) is available in the **screenshots** folder.

### Lab Architecture

![Lab Architecture](screenshots/01-lab-architecture.png)

---

### Ubuntu Server Deployment

![Ubuntu Server](screenshots/02-ubuntu-server-installed.png)

---

### Hyper-V Troubleshooting

![Hyper-V](screenshots/22-disable-hypervisor-launchtype.png)

---

### Windows Installation

![Windows Installation](screenshots/29-windows-11-installation-progress.png)

---

### Windows Target Machine Ready

![Windows Desktop](screenshots/32-windows-11-target-vm-ready.png)

---

### Wazuh Server Deployment

![Wazuh Installation](screenshots/33-wazuh-server-installation.png)

---

### Wazuh Login

![Login](screenshots/35-wazuh-web-login.png)

---

### Wazuh Dashboard

![Dashboard](screenshots/36-wazuh-dashboard-overview.png)

---

# 🔐 Security Monitoring Completed

### Linux Monitoring

- User creation
- Group creation
- sudo monitoring
- PAM authentication
- Security Configuration Assessment (SCA)

### Threat Hunting

- Agent investigation
- Authentication events
- Rule ID analysis
- Log analysis

---

# 💡 Skills Demonstrated

## Infrastructure

- Oracle VirtualBox
- Ubuntu Server Administration
- Windows 11 Deployment

## SIEM

- Wazuh Deployment
- Wazuh Agent Management
- Dashboard Administration
- Security Monitoring

## Security Operations

- Threat Hunting
- Log Analysis
- Security Event Investigation
- Endpoint Monitoring

## Troubleshooting

- Hyper-V
- Virtualization-Based Security (VBS)
- BCDEdit
- Windows Installation
- Virtual Disk Expansion

---

# 📚 Lessons Learned

During this project I learned that:

- Hyper-V and VBS can prevent Oracle VirtualBox from using hardware virtualization.
- Wazuh consists of multiple interconnected services including the Manager, Dashboard, Indexer and Agents.
- Endpoint onboarding requires successful agent registration before telemetry becomes available.
- Security monitoring should always be validated using generated security events rather than assumptions.
- Documenting troubleshooting significantly improves repeatability and future deployments.

---

# 🔮 Future Improvements

- Deploy Windows Wazuh Agent
- Install Sysmon
- Configure File Integrity Monitoring
- Generate Windows Security Events
- Create Custom Detection Rules
- Perform MITRE ATT&CK Mapping
- Develop Threat Hunting Scenarios
- Add PowerShell Detection
- Simulate Brute Force Attacks
- Build Detection Engineering Playbooks

---

# 📂 Repository Structure

```text
Wazuh-SIEM-Home-Lab
│
├── README.md
├── architecture/
├── detection-rules/
├── documentation/
├── queries/
└── screenshots/
```

---

# 🙏 Acknowledgements

This project is part of my ongoing cyber security learning journey and is continuously updated as I develop additional SOC, Blue Team, and Detection Engineering skills.

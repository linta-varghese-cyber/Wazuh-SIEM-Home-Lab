Documentation Folder

This folder contains installation notes, troubleshooting, lab journals and project documentation.
# Lab Journal

---

## 04 July 2026

### Objective

Deploy a Windows 11 Enterprise endpoint to integrate with the Wazuh SIEM environment.

### Activities

- Created Windows 11 Virtual Machine in Oracle VirtualBox
- Allocated 4 GB RAM
- Allocated 2 vCPUs
- Attached Windows 11 Enterprise Evaluation ISO

### Challenges

VirtualBox displayed a black screen after the initial boot.

### Investigation

Verified:
- Virtualization enabled in BIOS
- VirtualBox configuration
- Hyper-V status

### Resolution

Disabled Hyper-V using:

bcdedit /set hypervisorlaunchtype off


Restarted the host system.

### Additional Issue

Windows Setup required a larger system drive.

### Resolution

Expanded the virtual disk from 50 GB to 80 GB.

### Result

Windows 11 Enterprise installed successfully and reached the desktop.

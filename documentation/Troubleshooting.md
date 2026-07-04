# Troubleshooting

## Black Screen During Windows Installation

### Problem

Virtual machine displayed only a black screen after powering on.

### Cause

Microsoft Hyper-V was still active on the host.

### Resolution

Disabled Hyper-V using

bcdedit /set hypervisorlaunchtype off

Restarted host.

Verified using

systeminfo

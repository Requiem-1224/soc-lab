# Windows Endpoint VM Setup – SOC Lab

## Overview
This document describes the setup and configuration of the Windows endpoint used in the SOC home lab. This system is intended to generate endpoint telemetry for collection and analysis in a SIEM (Security Onion).

---

## System Information

| Category | Details |
|--------|--------|
| Operating System | Windows 10 LTSC |
| VM Platform | VirtualBox |
| Role | Endpoint / Telemetry Source |
| Purpose | Generate endpoint logs for detection experiments |

---

## Virtual Machine Configuration

| Resource | Allocation |
|-------|-----------|
| CPU | 2 vCPUs |
| RAM | 3–4 GB |
| Disk | 50GB (Dynamic) |
| Network Adapter | NAT |
| Snapshots | Enabled |

> A snapshot was taken immediately after OS installation to allow rollback during experimentation.

---

## Operating System Installation

1. Created a new Windows virtual machine.
2. Allocated CPU, RAM, and disk resources as listed above.
3. Installed Windows 10 LTSC using default installer settings.
4. Completed initial setup and user creation.
5. Installed all available security updates.

---

## Post-Installation Hardening & Optimization

- Disabled unnecessary startup applications.
- Reduced visual effects to improve performance:
  - **System → Advanced System Settings → Performance → Adjust for best performance**
- Verified network connectivity.

---

## OSQuery Installation

1. Downloaded OSQuery for Windows from the official OSQuery website.
2. Installed OSQuery using default installation options.
3. Verified installation via PowerShell.

### Validation Command
```powershell
osqueryi

# Linux Endpoint VM Setup – SOC Lab

## Overview
This document describes the setup and configuration of the Linux endpoint used in the SOC home lab. This system is intended to generate endpoint telemetry for collection and analysis in a SIEM (Security Onion).

---

## System Information

| Category             | Details                                    |
|---------------------|--------------------------------------------|
| Operating System     | Ubuntu 24.04 LTS (Server)                  |
| VM Platform          | VirtualBox                                 |
| Role                 | Endpoint / Telemetry Source                |
| Purpose              | Generate endpoint logs for detection experiments |

---

## Virtual Machine Configuration

| Resource          | Allocation                 |
|------------------|----------------------------|
| CPU               | 2 vCPUs                    |
| RAM               | 2–3 GB                     |
| Disk              | 20–30 GB (Dynamic)         |
| Network Adapter   | NAT + Host-Only (for SIEM connectivity) |
| Snapshots         | Enabled                     |



---

## Operating System Installation

1. Created a new Linux virtual machine.
2. Allocated CPU, RAM, and disk resources as listed above.
3. Installed **Ubuntu 24.04 LTS Server** using default installation options.
4. Completed initial setup and created a non-root user.
5. Installed all available updates:
   ```bash
   sudo apt update && sudo apt upgrade -y
- A snapshot was taken immediately after OS installation to allow rollback during experimentation.

## Osquery Installation Troubleshooting (Linux)

During the initial setup of osquery on the Linux VM, I encountered multiple issues related to package installation and repository configuration.

### Issue Encountered

While attempting to install osquery using `apt`, the installation failed due to:

- Repository configuration errors  
- GPG key retrieval failures  
- DNS resolution issues (`curl: could not resolve host`)  
- Incorrect or unreachable repository URLs  

These issues prevented `apt` from locating and installing the osquery package successfully.

### Troubleshooting Steps Taken

To diagnose and resolve the problem, I performed the following actions:

- Verified APT source list files under `/etc/apt/sources.list.d/`  
- Checked for the presence of the osquery GPG key in `/etc/apt/keyrings/`  
- Tested network connectivity and DNS resolution using `ping`  
- Re-attempted repository setup using the official osquery installation steps  
- Reverted to a clean VM snapshot to rule out system misconfiguration

  https://www.starwindsoftware.com/blog/how-to-install-and-use-osquery-on-ubuntu-and-linux-mint/

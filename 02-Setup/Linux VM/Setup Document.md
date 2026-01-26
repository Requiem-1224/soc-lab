# Linux Endpoint VM Setup – SOC Lab

## Overview
This document describes the setup and configuration of the Linux endpoint used in the SOC home lab. This system is intended to generate endpoint telemetry for collection and analysis in a SIEM (Security Onion).

---

## System Information

| Category             | Details                                    |
|---------------------|--------------------------------------------|
| Operating System     | Ubuntu 22.04 LTS (Server)                  |
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

- A snapshot was taken immediately after OS installation to allow rollback during experimentation.

---

## Operating System Installation

1. Created a new Linux virtual machine.
2. Allocated CPU, RAM, and disk resources as listed above.
3. Installed **Ubuntu 22.04 LTS Server** using default installation options.
4. Completed initial setup and created a non-root user.
5. Installed all available updates:
   ```bash
   sudo apt update && sudo apt upgrade -y

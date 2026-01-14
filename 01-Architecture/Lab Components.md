## Core Components

### SIEM – Security Onion
- Acts as the centralized log collection and analysis platform
- Receives endpoint telemetry from OSQuery agents
- Generates alerts for suspicious activity
- Provides dashboards and investigation tooling

### Windows Endpoint
- Windows VM used to simulate a user workstation
- OSQuery installed as an endpoint telemetry agent
- Generates process, user, and system activity logs

### Linux Endpoint
- Linux VM used to simulate a server or workstation
- OSQuery installed as an endpoint telemetry agent
- Generates system, user, and network-related telemetry
  
## Endpoint Telemetry

OSQuery is installed locally on each endpoint virtual machine.
It runs as a background service and collects system telemetry including:

- Process execution
- User account activity
- File system changes
- Network connections

Collected telemetry is forwarded to the Security Onion SIEM for detection
and analysis.

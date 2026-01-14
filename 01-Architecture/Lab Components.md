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

## Data Flow

1. OSQuery collects telemetry on each endpoint
2. Telemetry is forwarded from endpoints to Security Onion
3. Security Onion processes the data and applies detection logic
4. Alerts are generated for analyst review and investigation

   ## Design Decisions

- OSQuery was chosen due to its lightweight footprint and cross-platform support
- Security Onion was selected to provide an enterprise-style SOC platform
- A minimal number of endpoints were used to reduce system resource usage
- VirtualBox was used to allow easy replication of the lab environment

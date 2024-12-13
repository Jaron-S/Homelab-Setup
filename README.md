## **Homelab Setup**

### **Overview**
This project focuses on building a comprehensive homelab environment to enhance skills in cybersecurity, networking, and system administration. The homelab integrates various tools and technologies for monitoring, analysis, and entertainment while providing a platform for learning and experimentation.

---

### **Features**

#### **Linux Server**
- **Guacamole**: Provides remote desktop gateway functionality, enabling secure access to multiple machines from a web-based interface.
- **Wazuh**: A security platform for threat detection, incident response, and compliance monitoring.
- **Snort**: A network intrusion detection and prevention system.
- **T-Pot**: A honeypot platform for detecting and analyzing potential attacks.
- **DNS Server (PiHole)**: A DNS-based ad-blocking system for enhanced privacy and performance.
- **Docker**: Containerization platform to deploy and manage applications.
- **Jellyfin**: Open-source media server for managing and streaming media content.
- **Cockpit**: A web-based graphical interface for managing Linux servers.

#### **Windows Server**
- **Active Directory**: Domain services for centralized management of user accounts and policies.
- **Splunk**: A data analytics and SIEM platform for log aggregation and monitoring.
- **Additional Components**:
  - Splunk Universal Forwarder: Collects and forwards logs to the Splunk server.
  - Sysmon: Captures telemetry data for detailed event logging.
  - Atomic Red Team: Simulates adversarial techniques for testing and validation.

#### **Lab Environment Configuration**
- **Target Machines**:
  - Windows 10: Configured with Splunk Universal Forwarder, Sysmon, and Atomic Red Team.
  - Kali Linux: Attacker machine for penetration testing.
- **Network Infrastructure**:
  - **IP Configuration**:
    - Splunk Server: `192.168.10.10`
    - Active Directory Server: `192.168.10.0`
    - Kali Linux: `192.168.10.250`
    - Windows 10 (DHCP-assigned IP).
  - **Switch**: L2 switch connecting servers and computers.
  - **Router**: Connects the network to the internet.
  - **Cloud**: Represents external internet connectivity.

---

### **Tools & Technologies**

#### **Linux Tools**
- **Guacamole**: Remote desktop gateway for easy management.
- **Wazuh**: Open-source security platform.
- **Snort**: Intrusion detection and prevention.
- **T-Pot**: Multi-honeypot platform.
- **PiHole**: DNS-based ad-blocking system.
- **Docker**: Container orchestration platform.
- **Jellyfin**: Media server for streaming.
- **Cockpit**: Linux server management dashboard.

#### **Windows Tools**
- **Active Directory**: Centralized domain management.
- **Splunk**: Log aggregation and analytics.
- **Sysmon**: Detailed event logging.
- **Atomic Red Team**: Adversarial simulation for testing.

---

### **Installation & Setup**

#### **1. Linux Server Setup**
- Install and configure Docker for application management:
  ```bash
  sudo apt update && sudo apt install docker docker-compose
  ```
- Deploy applications (e.g., Guacamole, Wazuh, T-Pot) using Docker Compose or native installation.
- Configure PiHole as the primary DNS server:
  ```bash
  curl -sSL https://install.pi-hole.net | bash
  ```

#### **2. Windows Server Setup**
- Install Active Directory and configure the domain environment.
- Deploy Splunk with the Universal Forwarder and configure Sysmon:
  - Download and install Sysmon from [Microsoft Sysinternals](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon).
  - Install the Splunk Universal Forwarder and configure log forwarding.
- Install Atomic Red Team for generating test data:
  ```powershell
  git clone https://github.com/redcanaryco/atomic-red-team.git
  ```

#### **3. Network Configuration**
- Connect all machines to the switch and router.
- Set static IPs for servers and dynamic IPs for clients.
- Test connectivity using tools like `ping` and `tracert`.

---

### **Visualization**
- Create a logical network diagram using tools like draw.io to document the topology, IP assignments, and data flow.

---

### **Usage**
- **Guacamole**: Access servers and machines remotely via a web-based interface.
- **Wazuh**: Monitor threats, incidents, and compliance.
- **Splunk**: Analyze logs and security events.
- **T-Pot**: Detect and analyze attack vectors.
- **PiHole**: Block ads and trackers for all network devices.
- **Jellyfin**: Stream media content.
- **Cockpit**: Manage Linux servers from a centralized interface.

---

### **Purpose**
This homelab is designed to provide a practical environment for learning and experimentation, enhancing skills in:
- Cybersecurity (threat detection, incident response, SIEM).
- Networking (Active Directory, domain management, honeypot deployment).
- System administration (server setup, monitoring, troubleshooting).


## Homelab Setup

### Overview

This project focuses on building a secure and comprehensive homelab environment to enhance skills in cybersecurity, networking, and system administration. The homelab integrates various tools and technologies for monitoring, analysis, and entertainment while providing a platform for learning and experimentation.

---

### Features

#### Linux Server (Management Network - VLAN 40)

* **Guacamole**: Provides remote desktop gateway functionality, enabling secure access to multiple machines from a web-based interface.
* **Wazuh**: A security platform for threat detection, incident response, and compliance monitoring.
* **Snort**: A network intrusion detection and prevention system.
* **Docker**: Containerization platform to deploy and manage applications.
* **Jellyfin**: Open-source media server for managing and streaming media content.
* **Cockpit**: A web-based graphical interface for managing Linux servers.

#### Raspberry Pi 4 (8GB) (Security Network - VLAN 50)

* **T-Pot**: A honeypot platform for detecting and analyzing potential attacks.

#### Raspberry Pi 3 (Main Network - VLAN 10)

* **DNS Server (PiHole)**: A DNS-based ad-blocking system for enhanced privacy and performance.

#### Proxmox (Management Network - VLAN 40)

* **Splunk VM (Linux)** (Security Network - VLAN 50): A dedicated Linux virtual machine running Splunk Enterprise for log aggregation and monitoring.
* **Windows Server VM** (Main Network - VLAN 10): 
    * **Active Directory**: Domain services for centralized management of user accounts and policies.
    * **Additional Components**:
        * Splunk Universal Forwarder: Collects and forwards logs to the Splunk server.
        * Sysmon: Captures telemetry data for detailed event logging.
        * Atomic Red Team: Simulates adversarial techniques for testing and validation.

#### Target Machines (Main Network - VLAN 10)

* **Windows 10 Laptop**: Configured with Splunk Universal Forwarder, Sysmon, and Atomic Red Team.
* **Windows 11 Desktop**: Configured with Splunk Universal Forwarder, Sysmon, and Atomic Red Team.
* **Kali Linux**: Attacker machine for penetration testing.


---

### Tools & Technologies

#### Linux Tools

* **Guacamole**: Remote desktop gateway for easy management.
* **Wazuh**: Open-source security platform.
* **Snort**: Intrusion detection and prevention.
* **Docker**: Container orchestration platform.
* **Jellyfin**: Media server for streaming.
* **Cockpit**: Linux server management dashboard.
* **Splunk**: Log aggregation and analytics. 

#### Windows Tools

* **Active Directory**: Centralized domain management.
* **Sysmon**: Detailed event logging.
* **Atomic Red Team**: Adversarial simulation for testing.

#### Virtualization

* **Proxmox**: Bare-metal hypervisor. 

---

### Installation & Setup

**(Refer to the network diagram for specific configurations and IP assignments.)**

#### 1. Linux Server Setup

* Install and configure Docker for application management:
  ```bash
  sudo apt update && sudo apt install docker docker-compose
  ```
* Deploy applications (e.g., Guacamole, Wazuh) using Docker Compose or native installation.

#### 2. Raspberry Pi Setup

* **Pi 4**: Install T-Pot on the Raspberry Pi 4. (Refer to T-Pot documentation for detailed instructions.)
* **Pi 3**: Install Pi-Hole on the Raspberry Pi 3. 
  ```bash
  curl -sSL https://install.pi-hole.net | bash
  ```

#### 3. Proxmox Setup

* Install Proxmox on the bare-metal server.
* **Splunk VM**:
    * Deploy a new Linux VM (e.g., Ubuntu Server) on ESXi.
    * Download the Splunk Enterprise for Linux installer.
    * Upload the installer to the Splunk VM.
    * Install Splunk on the Linux VM using the installer.
* **Windows Server VM**:
    * Create and configure Windows Server virtual machine.
    * Install Active Directory, Splunk Universal Forwarder, Sysmon, and Atomic Red Team within the Windows Server VM.

#### 4. Target Machine Setup

* **Windows 10 Laptop**: Install Splunk Universal Forwarder, Sysmon, and Atomic Red Team.
* **Windows 11 Desktop**: Install Splunk Universal Forwarder, Sysmon, and Atomic Red Team.
* **Kali Linux**: Configure Kali Linux for penetration testing.

---

### Visualization

* **Network Diagram**: A comprehensive network diagram (e.g., created with draw.io) illustrating the lab topology, IP addresses, VLANs, and data flow is provided separately.

---

### Usage

* **Guacamole**: Access servers and machines remotely via a web-based interface.
* **Wazuh**: Monitor threats, incidents, and compliance.
* **Splunk**: Analyze logs and security events.
* **T-Pot**: Detect and analyze attack vectors.
* **PiHole**: Block ads and trackers for all network devices.
* **Jellyfin**: Stream media content.
* **Cockpit**: Manage Linux servers from a centralized interface.

---

### Purpose

This homelab is designed to provide a practical environment for learning and experimentation, enhancing skills in:

* Cybersecurity (threat detection, incident response, SIEM).
* Networking (Active Directory, domain management, honeypot deployment, VLANs).
* System administration (server setup, monitoring, troubleshooting).
* Virtualization (VMware ESXi).

---

### Security Best Practices

* **VLAN Segmentation:** The network is segmented into VLANs (Main, Guest, IoT, Management, Security) to enhance security and isolate different types of traffic.
* **Strong Passwords:**  Use strong, unique passwords for all devices and services.
* **Two-Factor Authentication (2FA):** Enable 2FA wherever possible.
* **Firewall:**  A firewall is used to control traffic flow between VLANs and protect the network from external threats.
* **Intrusion Detection/Prevention:** Snort is used to monitor network traffic for malicious activity.
* **Security Information and Event Management (SIEM):** Splunk is used to collect and analyze security logs.
* **Honeypot:** T-Pot is used to attract and analyze potential attackers.

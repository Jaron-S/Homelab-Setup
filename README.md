## **Home Network Optimization and Monitoring**

### **Overview**
This project focuses on optimizing and securing a home network by integrating a PiHole DNS server for blocking advertisements and trackers and using advanced monitoring tools like Wireshark and Netdata. These efforts aim to enhance network performance, privacy, and security while offering insights into bandwidth usage and potential vulnerabilities.

### **Features**
- **Ad and Tracker Blocking**:
  - Configured PiHole to serve as the primary DNS server for the network, preventing advertisements and trackers from affecting user experience across all devices.
  - Improved overall browsing speeds and reduced exposure to potentially harmful scripts and trackers.
- **Network Traffic Monitoring**:
  - Implemented Wireshark for packet analysis, enabling detailed inspection of network traffic to identify potential threats and optimize data flow.
  - Deployed Netdata for real-time monitoring of bandwidth, CPU, memory usage, and system health metrics, providing a holistic view of network and device performance.
- **Security Insights**:
  - Used monitoring data to identify unusual traffic patterns that may indicate security issues, such as unauthorized access attempts or bandwidth hogging.

### **Tools & Technologies**
- **PiHole**: A DNS-based ad-blocking system designed to reduce internet clutter and enhance privacy.
- **Wireshark**: An open-source tool for network protocol analysis, allowing for in-depth packet inspection.
- **Netdata**: A lightweight monitoring tool providing insights into system performance metrics in real-time.

### **Installation & Setup**
#### **1. Setting Up PiHole**
- Install PiHole on a Raspberry Pi or compatible device:
  ```bash
  curl -sSL https://install.pi-hole.net | bash
  ```
- During setup, configure PiHole as the primary DNS server for your router. This will route all network traffic through PiHole for ad filtering.

#### **2. Installing Wireshark**
- Download and install Wireshark on your computer:
  - Windows/Mac: [Wireshark Downloads](https://www.wireshark.org/download.html)
  - Linux: Install via package manager:
    ```bash
    sudo apt update && sudo apt install wireshark
    ```

#### **3. Installing Netdata**
- Install Netdata using its one-line installer:
  ```bash
  bash <(curl -Ss https://my-netdata.io/kickstart.sh)
  ```
- Access Netdata via your web browser at `http://<server-ip>:19999`.

#### **4. Configuring Router Settings**
- Set PiHole as the network-wide DNS server in your router’s settings.
- Test functionality by visiting a site like [Adblock Tester](https://adblock-tester.com).

### **Usage**
- **PiHole**:
  - Access the PiHole dashboard at `http://<server-ip>/admin` to view blocked domains and manage settings.
- **Wireshark**:
  - Run packet captures on your network interface to analyze live traffic or stored logs for deeper inspection.
- **Netdata**:
  - Monitor real-time system performance by navigating to the Netdata dashboard in your browser.

# Configure Universal Forwarder on Linux and Windows Clients

## Introduction
In this project, we will install and configure **Splunk Universal Forwarder (UF)** on both Linux and Windows systems. The Universal Forwarder sends logs from client machines to the Splunk Enterprise server (SIEM), enabling centralized monitoring and analysis.

## Overview
The Splunk Universal Forwarder is a lightweight version of Splunk Enterprise designed only for **collecting and forwarding data**. It does not have the web interface or dashboards; its sole job is to move logs securely from endpoints to the main Splunk server.  

By configuring UFs on Windows and Linux clients, you ensure that system activities and security events are collected in one place for monitoring.

## What is Splunk Universal Forwarder?
Splunk Universal Forwarder (UF) is:
- A small agent installed on client machines.
- Responsible for collecting logs (like system, security, or application logs).
- Sends the data to the Splunk Enterprise server or indexer.
- Runs quietly in the background with minimal resource usage.  

👉 Think of it like a **data delivery boy** that carries logs from your computer to the Splunk server.

## Purpose
The purpose of configuring Splunk Universal Forwarder is to:
- Enable **log collection** from multiple devices.
- Forward logs in real time to the SIEM server.
- Ensure visibility of activities across Windows and Linux systems.
- Build the foundation for threat detection and incident response.

## Pre-requirements
Before installing the Splunk Universal Forwarder, ensure:
- Splunk Enterprise (SIEM server) is already installed and running.
- You know the **IP address** of the Splunk server.
- Network port **9997** (default Splunk receiving port) is open on the server.
- Admin/root access on the client systems.
- Internet access to download the Universal Forwarder package.

## Steps to Install Splunk Universal Forwarder

### On Windows:
1. Download the Splunk Universal Forwarder (Windows `.msi`) from [Splunk Downloads](https://www.splunk.com/en_us/download/universal-forwarder.html).
2. Run the installer and accept the license agreement.
3. Choose the installation path (default is fine).
4. Enter the **Splunk server IP address** and **port 9997** when prompted.
5. Set the admin username and password for the forwarder service.
6. Complete installation — UF runs as a Windows service automatically.
7. Verify forwarding by checking if logs appear in the Splunk Enterprise server.

### On Linux:
1. Download the Universal Forwarder package for Linux (`.tgz` or `.deb`).
2. Open terminal and install:
   - For `.tgz`:  
     ```bash
     tar -xvf splunkforwarder-*.tgz -C /opt
     ```
   - For `.deb`:  
     ```bash
     sudo dpkg -i splunkforwarder-*.deb
     ```
3. Navigate to UF bin folder:  
   ```bash
   cd /opt/splunkforwarder/bin

4. Start the forwarder and accept license:
```
sudo ./splunk start --accept-license
```

5. Configure the forwarder to send logs to the Splunk server:
```
sudo ./splunk add forward-server <SplunkServerIP>:9997 -auth admin:password
```

6. Add inputs (for example, to forward /var/log/syslog):
```
sudo ./splunk add monitor /var/log/syslog
```

7. Restart the forwarder service:
```
sudo ./splunk restart
```
8. Verify the logs are reaching the Splunk Enterprise server.

## Conclusion

By installing and configuring the Splunk Universal Forwarder on Windows and Linux clients, we enable centralized log forwarding to the SIEM server. This ensures all critical system events are collected in one place, making it easier to detect threats and monitor system health.

This step is crucial for building a reliable and scalable security monitoring setup.

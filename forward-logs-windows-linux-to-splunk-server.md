# Forward Logs from Windows and Linux Systems to the Splunk Server

## Introduction
This guide explains how to forward logs from Windows and Linux clients to a central **Splunk Enterprise** server using the **Splunk Universal Forwarder (UF)**. Forwarding logs is a crucial step in centralizing monitoring and building a SIEM lab.

---

## Overview
Forwarding logs ensures that all system events, security alerts, and application logs from multiple machines are collected in one place. By sending logs to the Splunk server, you can search, analyze, and visualize activities from both Linux and Windows systems in real-time.

---

## How Logs are Forwarded via Splunk UF 
The **Splunk Universal Forwarder (UF)** acts as a **small agent** installed on client machines. Its job is to:
- Read log files or event logs from the system.
- Send them securely to the Splunk Enterprise server over the network.
- Run quietly in the background with minimal resource usage.  

Think of it as a **delivery person** that picks up logs from your computer and delivers them to the Splunk “mailbox” (server).

---

## Purpose
The purpose of this project is to:
- Enable centralized log collection from multiple systems.
- Ensure Windows and Linux logs are accessible in one SIEM server.
- Practice configuring log forwarding using Splunk Universal Forwarder.
- Build the foundation for monitoring and security analysis.

---

## Pre-requirements
Before starting, ensure:
1. **Splunk Enterprise** is installed and running on the server.
2. **Splunk Universal Forwarder** is installed on both Windows and Linux clients.
3. You know the **IP address** of the Splunk server.
4. Network port **9997** (default for forwarding) is open.
5. Admin/root access on all client systems.
6. Internet access to download packages if needed.

---

## Steps to Forward Logs

### On Windows:
1. Open **Splunk Universal Forwarder** folder:  
   `C:\Program Files\SplunkUniversalForwarder\bin`
2. Open **PowerShell as Administrator**.
3. Add the Splunk server as a forwarder:  
   ```powershell
   .\splunk.exe add forward-server <SplunkServerIP>:9997 -auth admin:password
4. Configure which logs to forward (Windows Event Logs) by editing inputs.conf:
```
[WinEventLog://Application]
disabled = 0

[WinEventLog://Security]
disabled = 0

[WinEventLog://System]
disabled = 0
```
* Save the file in:
  ```
  C:\Program Files\SplunkUniversalForwarder\etc\system\local\
  ```
5. Restart the SplunkForwarder service:
```
Restart-Service SplunkForwarder
```
6. Verify that logs appear on the Splunk Enterprise server via Search & Reporting.

## On Linux:

1. Open terminal and go to Splunk UF bin folder:
```
cd /opt/splunkforwarder/bin
```

2. Add the Splunk server as a forwarder:
```
sudo ./splunk add forward-server <SplunkServerIP>:9997 -auth admin:password
```

3. Add log files to monitor (for example /var/log/syslog and /var/log/auth.log):
```
sudo ./splunk add monitor /var/log/syslog
sudo ./splunk add monitor /var/log/auth.log
```

4. Restart the forwarder:
```
sudo ./splunk restart
```
5. Check Splunk Enterprise server to confirm the logs are being received.

## Conclusion

By completing this step, logs from both Windows and Linux systems are successfully forwarded to the Splunk server. This enables **centralized monitoring, analysis, and visualizatio**n of all system activities, which is essential for building a reliable SIEM setup and practicing **blue team cybersecurity skills**.

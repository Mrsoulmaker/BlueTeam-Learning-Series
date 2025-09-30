# Build the Foundation for Centralized Log Monitoring

## Introduction
This guide explains how to set up a foundation for **centralized log monitoring** using Splunk Enterprise and Universal Forwarders. Centralized log monitoring helps collect logs from multiple systems into a single SIEM server for easier analysis and security monitoring.

---

## Overview
- Centralized log monitoring consolidates logs from Linux, Windows, and network devices.  
- It allows security teams to **detect threats faster** and maintain an overview of system activity.  
- By building this foundation, you prepare for advanced security monitoring, dashboards, and alerts.

---

## Purpose
The purpose of this project is to:
- Collect logs from multiple systems in one location.  
- Ensure that all system activities are visible in the Splunk SIEM.  
- Establish a strong base for future blue team projects.  
- Enable monitoring, analysis, and alerting in real-time.

---

## Pre-requirements
Before starting, ensure:
1. Splunk Enterprise is installed and running.  
2. Universal Forwarders are installed and configured on client systems.  
3. Clients (Windows/Linux) are forwarding logs to the Splunk server.  
4. You have access to Splunk Web (`http://<SIEM-IP>:8000`).  
5. Admin/root access on client machines.

---

## Steps to Build the Foundation

1. **Verify Splunk Server and UF**  
   - Make sure Splunk Enterprise is running.  
   - Confirm that Windows and Linux Universal Forwarders are connected.  

2. **Verify Log Collection**  
   - Generate test logs on clients and ensure they appear in Splunk.  
   - Check that logs are correctly indexed and searchable.  

3. **Organize Logs**  
   - Create indexes or folders in Splunk for different log types (Windows, Linux, network).  
   - Assign sourcetypes for proper categorization.  

4. **Optional – Create a Basic Dashboard**  
   - Use Splunk Web to create a simple dashboard showing recent logs from all clients.  

5. **Document the Setup**  
   - Take screenshots of logs appearing in Splunk.  
   - Save configuration files used for UF and Splunk server.  

---

## Expected Results
- Logs from all client systems appear in Splunk.  
- You can search, filter, and categorize logs in real-time.  
- A basic understanding of centralized log monitoring is established.  

---

## Conclusion
By completing this setup, you have **built the foundation for centralized log monitoring**. All logs from Windows and Linux clients are now collected in a single Splunk SIEM server, enabling easier analysis, monitoring, and future blue team projects. This step ensures your lab environment is ready for advanced threat detection and security monitoring.

# Verify Log Collection by Generating and Searching Test Logs in Splunk

## Introduction
This guide explains how to generate test logs on **Windows and Linux clients** and verify that they are successfully collected and indexed by the **Splunk Enterprise** server. Testing ensures that your Splunk setup and Universal Forwarders are working correctly.

---

## Overview
- Test logs are small, artificial log entries created to confirm that forwarding is working.
- By generating logs on both Linux and Windows clients, you can check whether the Splunk server receives them in real-time.
- This step helps validate the **SIEM pipeline** before moving on to real-world log monitoring.

---

## Purpose
The purpose of this project is to:
- Confirm that **Splunk Universal Forwarders** are correctly forwarding logs.
- Ensure that Windows and Linux logs are visible in Splunk.
- Build confidence in the SIEM setup before analyzing real logs.
- Provide a foundation for advanced log monitoring and security analysis.

---

## Pre-requirements
Before starting, make sure you have:
1. **Splunk Enterprise** installed and running on the server.  
2. **Universal Forwarder** installed and configured on both Windows and Linux clients.  
3. Access to Splunk Web (`http://<SIEM-IP>:8000`) to view logs.  
4. Admin/root access on client machines to generate test logs.

---

## Steps to Generate and Verify Logs

### On Linux:
1. Open the terminal on your Linux client.  
2. Generate a test log entry using the `logger` command:  
   ```bash
   logger "SPLUNK-TEST: Hello from Linux $(hostname)"
3. Log in to Splunk Web → Search & Reporting app.
4. In the search bar, type:
```
"SPLUNK-TEST"
```
5. Check if the test log appears with the correct hostname and timestamp.

## On Windows:

1. Open PowerShell as Administrator on your Windows client.

2. Create a test event log source (if it doesn’t exist):
```
New-EventLog -LogName Application -Source "BlueTeamTest" -ErrorAction SilentlyContinue
```
3. Write a test event:
```
Write-EventLog -LogName Application -Source "BlueTeamTest" -EventID 1001 -EntryType Information -Message "SPLUNK-TEST: Hello from Windows"
```
4. Log in to Splunk Web → Search & Reporting.
5. Search for:
```
"SPLUNK-TEST"
```
6. Confirm that the log appears correctly.

## Expected Results

* Both Linux and Windows test logs appear in the Splunk search results.

* Hostname, timestamp, and log message should match the test commands.

* If logs do not appear, troubleshoot UF configuration, firewall, or Splunk receiving port.

## Conclusion

By generating test logs and verifying their presence in Splunk, you confirm that your **Universal Forwarders** are properly forwarding logs to the **Splunk Enterprise server**. This step is essential to ensure that the SIEM is ready for real-world log collection and monitoring in subsequent projects.

## Additional Tips

* Always use unique identifiers in test logs, like ```SPLUNK-TEST```, to easily locate them.

* Take screenshots of the test logs in Splunk for documentation or reporting.

* Regularly test your forwarding setup whenever you make changes to UF or firewall rules.

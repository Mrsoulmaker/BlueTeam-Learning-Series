# SIEM-Log-Collection-with-Splunk-Lab
Blue Team Lab: Collect logs from Linux and Windows using Splunk. Install Splunk Enterprise, configure Universal Forwarders, monitor system logs, and verify test messages in Splunk Web. Beginner-friendly SIEM hands-on project.

## Overview
This project demonstrates the basics of collecting and analyzing system logs from multiple machines using **Splunk**, a popular **Security Information and Event Management (SIEM)** tool. Logs from Linux and Windows machines are forwarded to a central Splunk server for monitoring and analysis.

---

## What is a SIEM?
What is a SIEM? (Simple!)

Think of a SIEM as a big mailbox for many computers.

* Each computer (Windows or Linux) writes little notes (logs) about what it’s doing.

* The SIEM collects all those notes, shows them in one place, and helps you find anything strange.

Two important parts:
* Indexer / SIEM server — the big mailbox (where everything is stored and searched).
* Forwarder (agent) — a little postman you install on each computer so it sends its notes to the mailbox.

---

## What is Splunk?
**Splunk** is a widely-used SIEM platform that can ingest logs from servers, network devices, and applications. It helps visualize, search, and analyze log data, making it easier to identify errors, anomalies, and potential security incidents.

---

## What are Logs?
**Logs** are records of events that happen in a system or application. They provide information such as user activity, system errors, and security events. Monitoring logs is essential for troubleshooting, auditing, and detecting suspicious activity.

---

## Purpose
The goal of this project is to learn how to:
- Install and use Splunk for log collection.
- Forward logs from both Linux and Windows clients to a central SIEM server.
- Understand how logs are organized, indexed, and searchable in Splunk.
- Gain hands-on experience with basic SIEM concepts and log monitoring.

---

## Project list

* [Install Splunk Enterprise as the SIEM server](https://github.com/Mrsoulmaker/BlueTeam-Learning-Series/blob/main/configure-universal-forwarder-linux-windows-clients.md)

* Configure Universal Forwarder on Linux and Windows clients

* Forward logs from both systems to the Splunk server

* Verify log collection by generating and searching test logs

* Build the foundation for centralized log monitoring

---

## **Key Features**

- **Centralized Log Collection:** Collects logs from multiple machines (Linux and Windows) into one Splunk server.
- **Cross-Platform Support:** Works with both Linux and Windows clients.
- **Real-Time Monitoring:** Logs are forwarded and indexed in real-time for quick visibility.
- **Test Log Generation:** Provides scripts to generate test logs for verifying Splunk setup.
- **Beginner-Friendly:** Focused on understanding basic SIEM concepts and log monitoring.
- **Hands-On Lab:** Allows practice with Splunk Universal Forwarder and basic log management.
- **Security Awareness:** Helps understand the importance of logs in detecting anomalies and threats.

--- 

## Conclusion

This project provides a hands-on introduction to **SIEM and log management** using Splunk. By forwarding logs from Linux and Windows clients to a central Splunk server, you learn how to monitor, analyze, and understand system activity in real-time. This foundational lab builds essential skills for **blue team operations** and prepares you for more advanced cybersecurity monitoring and incident response tasks.

---

This project is a beginner-friendly lab to build foundational knowledge in **blue team operations** and **log-based security monitoring**.


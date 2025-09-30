# SIEM-Log-Collection-with-Splunk-Lab
Blue Team Lab: Collect logs from Linux and Windows using Splunk. Install Splunk Enterprise, configure Universal Forwarders, monitor system logs, and verify test messages in Splunk Web. Beginner-friendly SIEM hands-on project.

## Overview
This project demonstrates the basics of collecting and analyzing system logs from multiple machines using **Splunk**, a popular **Security Information and Event Management (SIEM)** tool. Logs from Linux and Windows machines are forwarded to a central Splunk server for monitoring and analysis.

---

## What is a SIEM?
What is a SIEM? (Simple!)

Think of a SIEM as a big mailbox for many computers.

*Each computer (Windows or Linux) writes little notes (logs) about what it’s doing.
*The SIEM collects all those notes, shows them in one place, and helps you find anything strange.

Two important parts:
1. Indexer / SIEM server — the big mailbox (where everything is stored and searched).
2. Forwarder (agent) — a little postman you install on each computer so it sends its notes to the mailbox.

---

## What is Splunk?
**Splunk** is a widely-used SIEM platform that can ingest logs from servers, network devices, and applications. It helps visualize, search, and analyze log data, making it easier to identify errors, anomalies, and potential security incidents.

---

## What are Logs?
**Logs** are records of events that happen in a system or application. They provide information such as user activity, system errors, and security events. Monitoring logs is essential for troubleshooting, auditing, and detecting suspicious activity.

---

## Purpose of the Project
The goal of this project is to learn how to:
- Install and use Splunk for log collection.
- Forward logs from both Linux and Windows clients to a central SIEM server.
- Understand how logs are organized, indexed, and searchable in Splunk.
- Gain hands-on experience with basic SIEM concepts and log monitoring.

---

This project is a beginner-friendly lab to build foundational knowledge in **blue team operations** and **log-based security monitoring**.


# Install Splunk Enterprise as the SIEM Server

## Introduction
This document explains how to install **Splunk Enterprise** and set it up as a Security Information and Event Management (SIEM) server. Splunk Enterprise will act as the central place where logs from different machines (Windows/Linux) are collected, stored, and analyzed.

---

## Overview
- Splunk Enterprise is the **main SIEM server** in our lab setup.  
- It receives logs from clients using the **Splunk Universal Forwarder (UF)**.  
- Once installed, we can use the Splunk Web interface to search, analyze, and visualize logs.  
- This is the **first and most important step** in building a log monitoring and security lab.

---

## What is Splunk Enterprise? (Simple)
Think of **Splunk Enterprise** like a **big smart mailbox**:
- Logs from different computers are like letters.  
- The mailbox (Splunk) collects all the letters in one place.  
- You can then search, organize, and understand what’s happening on your systems.  

---

## Purpose
The purpose of installing Splunk Enterprise is to:
- Create a **central log management system**.  
- Enable **real-time monitoring and searching** of logs.  
- Build a foundation for learning **SIEM concepts and blue team skills**.  
- Prepare the server so Linux and Windows clients can send their logs to it.  

---

## Pre-Requirements
Before starting, make sure you have:
1. A dedicated machine or virtual machine (VM) for Splunk Enterprise.  
   - Minimum: 2 CPUs, 4GB RAM, 20GB storage (more is better).  
2. **Operating System Options**:  
   - Windows 10/11 or Windows Server  
   - Linux (Ubuntu, CentOS, Debian, etc.)  
3. Internet connection to download Splunk Enterprise.  
4. A browser to access Splunk Web (`http://<SIEM-IP>:8000`).  
5. Admin privileges (to install software).  

---

## Steps to Install Splunk Enterprise

### 🔹 On Windows
1. Go to the [Splunk Downloads Page](https://www.splunk.com/en_us/download/splunk-enterprise.html).  
2. Download the **Windows .msi installer**.  
3. Run the `.msi` file and follow the installation wizard:  
   - Accept the license agreement.  
   - Choose installation folder (default: `C:\Program Files\Splunk`).  
   - Set the **admin username and password**.  
4. Once installed, open **Splunk Enterprise** from Start Menu or browser:  
   - URL: `http://localhost:8000`  
   - Login with your admin credentials.  

---

### 🔹 On Linux
1. Download the **Linux package** (`.deb`) from the [Splunk Downloads Page](https://www.splunk.com/en_us/download/splunk-enterprise.html).  
2. Open a terminal and run the following commands:  
3.Go to /tmp or Downloads folder
```bash
cd /Downloads or cd /tmp  
```
4. Example: Download Splunk (replace with actual version link)
```
wget -O splunk.deb 'https://download.splunk.com/products/splunk/releases/x.x.x/linux/splunk.tgz'
```
5. Extract Splunk to /opt directory
```
sudo dpkg -i splunk.deb 
```
6. Navigate to splunk bin directory 
```
cd /opt/splunk/bin
```
7. start splunk and accept user license agreement and give admin usernmae and password
```
sudo ./splunk start --accept-license
```
8. Once installed, open **Splunk Enterprise** from Start Menu or browser:  
   - URL: `http://localhost:8000`  
   - Login with your admin credentials.  

# Start Splunk for the first time
sudo /opt/splunk/bin/splunk start --accept-license

## Conclusion
By completing this step, you have successfully installed Splunk Enterprise and set up your SIEM server. 🎉

This server is now ready to receive logs from client machines (Linux and Windows) using the Splunk Universal Forwarder. With this setup, you’ve built the foundation for centralized log monitoring, an essential skill in cybersecurity and blue team operations.

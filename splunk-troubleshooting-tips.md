## Splunk Troubleshooting and Tips.md


* Ensure no other application is using port 8000 when starting Splunk Enterprise on Windows.

* Allow port 8000 in Windows Firewall if Splunk Web is not accessible.

* Run the Splunk installer and service as Administrator on Windows.

* Check if Splunk is running on Linux using ```sudo /opt/splunk/bin/splunk status.```

* Open firewall for port 8000 on Linux using ```sudo ufw allow 8000.```

* Use the correct server IP in the browser for Splunk Web.

* Accept the license and set admin password correctly during Splunk first start.

* Reset the admin password if login fails using ```sudo /opt/splunk/bin/splunk edit user admin -password <newpassword>.```

* Make sure the Splunk Universal Forwarder service is running on Windows through Services or ```Start-Service SplunkForwarder.```

* Check UF process on Linux using ```ps aux | grep splunk``` and start UF with ```sudo /opt/splunkforwarder/bin/splunk start.```

* Ping the Splunk server from client machines to confirm connectivity.

* Test port 9997 connectivity from Linux (```nc -zv <SplunkServerIP> 9997```) or Windows (```Test-NetConnection -ComputerName <SplunkServerIP> -Port 9997```).

* Open port 9997 in the server firewall if forwarders cannot connect.

* Verify UF configuration files for correct monitored paths and settings.

* Restart UF after making any changes to configuration files.

* Ensure correct index and sourcetype are set in the forwarder.

* Check Splunk internal logs using ```index=_internal sourcetype=splunkd``` for forwarder connection errors.

* Confirm credentials and server IP are correct in the forwarder configuration.

* Ensure monitored log files exist and are accessible on client machines.

* Search Splunk for exact test log keywords like ```"SPLUNK-TEST"``` without typos.

* Verify hostnames and timestamps on logs match the client machines.

* Confirm all clients are forwarding logs to the correct index in Splunk.

* Refresh dashboards and select the correct time range to view recent logs.

* Check server resources (CPU, RAM, Disk) if Splunk Web is slow or unresponsive.

* Avoid indexing unnecessary files to reduce load on the server.

* Document IP addresses, ports, and credentials for troubleshooting.

* Test log forwarding regularly to confirm that the setup works correctly.

* Take screenshots or notes of logs appearing in Splunk for verification.

* Restart UF or Splunk services whenever changes are made to configuration or monitored files.

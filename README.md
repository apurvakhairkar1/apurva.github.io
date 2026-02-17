# apurva.github.io

<h1>Enterprise SOC Homelab – Active Directory Security Monitoring Lab</h1>
📌 Project Overview

This project demonstrates the design and implementation of a simulated enterprise security environment for blue team training and detection engineering.

The lab replicates a corporate Active Directory network with centralized logging, firewall segmentation, intrusion detection, and attack simulation using Kali Linux.

The objective was to:

Build a segmented enterprise network

Deploy endpoint and network monitoring

Simulate real-world attack scenarios

Detect and investigate malicious activity using SIEM

<h1>Lab Architecture</h1>
🔹 Components

 *  pfSense Firewall (NAT + LAN segmentation)

 *  Suricata IDS/IPS (Network intrusion detection)

 *  Windows Server 2019 (Active Directory + DNS)

 *  2 Windows 10 Endpoints

 *  Sysmon (Endpoint telemetry)

 *  Splunk Enterprise SIEM

 *  Kali Linux Attacker Machine

 *  Virtualized using VirtualBox

<h1>Network Design</h1>

                [ Kali Linux ]
                      |
                   (WAN)
                      |
                [ pfSense Firewall ]
                      |
                   (LAN 192.168.1.0/24)
        ------------------------------------------------
        |                     |                      |
 [ Domain Controller ]   [ Windows 10 ]        [ Windows 10 ]
        |                                           |
        |-------------------------------------------|
                          |
                      [ Splunk SIEM ]

<h1>Firewall Configuration (pfSense)</h1>

 *  Configured WAN (NAT) and LAN segmentation

 *  Enabled DHCP for LAN clients

 *  Implemented firewall rules for controlled traffic flow

 *  Enabled logging for allowed and blocked traffic

 * Installed and configured Suricata IDS

<h1>Suricata IDS Configuration</h1>

 *  Installed Suricata package on pfSense

 *  Enabled Emerging Threats ruleset

 *  Configured IDS on LAN interface

 *  Enabled alert logging

 *  Verified detection of:

           *  Nmap scans

           *  Port scanning activity

           *  Suspicious HTTP requests

           *  SMB enumeration attempts

<h1>Endpoint Monitoring (Sysmon)</h1>

 *   Deployed Sysmon using SwiftOnSecurity configuration

 *   Forwarded logs to Splunk

 * Monitored:

           *  Event ID 1 – Process Creation

           *  Event ID 3 – Network Connections

 *   Event ID 4624/4625 – Logon Success/Failure

 *   PowerShell execution

<h1>SIEM Implementation (Splunk)</h1>

 *   Installed Splunk Enterprise

 *   Configured Universal Forwarders on endpoints

 *   Ingested:

           *   Windows Security Logs

           *  Sysmon Logs

           *  Suricata Alerts

           *  Firewall Logs

 *  Built detection queries for:

           *  Brute-force login attempts

           *  Port scanning activity

           *  Suspicious PowerShell execution

           *  Lateral movement indicators

  <h1>Key Outcomes</h1>  

 * Successfully detected simulated reconnaissance and brute-force activity

 *  Correlated endpoint and network telemetry

 *  Reduced false positives through rule tuning

 *  Developed reusable detection queries

<h1>Future Improvements</h1>

 *  Implement Wazuh for comparison with Splunk

 *  Enable IPS blocking mode in Suricata

 *  Add email alerting for high-severity events

 *  Deploy centralized log server for long-term retention

 *  Automate detection alerts

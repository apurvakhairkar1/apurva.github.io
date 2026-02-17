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

pfSense Firewall (NAT + LAN segmentation)

Suricata IDS/IPS (Network intrusion detection)

Windows Server 2019 (Active Directory + DNS)

2 Windows 10 Endpoints

Sysmon (Endpoint telemetry)

Splunk Enterprise SIEM

Kali Linux Attacker Machine

Virtualized using VirtualBox

---
title: "From Endpoints to Networks: Understanding Log Sources in Threat Hunting"
date: 2025-08-28T10:30:30-05:00
categories:
  - blog
tags:
  - Threat Hunting
  - Logs
  - Networking
---
When it comes to threat hunting or identifying intrusions in your systems, the most valuable resource isn’t a sophisticated tool or high-end appliance—it’s **data**. Without data, analysts have nothing to investigate. But where does this data originate, and how can we make sense of it? In this post, we’ll explore how data is collected and how it can be interpreted to protect an organization’s infrastructure.  

---

## Logs as The Primary Data Sources

At the core, **system logs** and **network logs** are the primary sources of information for threat hunters and security analysts. Logs are essentially records of events—who logged in, what process started, what file was changed, or what request was made to a server.  

Each log file is made up of entries, also referred to as **events**, and these entries can contain four main types of information:  

- **Usage information** (how systems or apps are used)  
- **Client requests and server responses** (records of requests entering or leaving your network)  
- **Account activity** (logins, permissions, etc.)  
- **Operational actions** (system changes, updates, etc.)  

There isn’t a “perfect” set of logs or a single correct amount of data. What’s useful depends on the organization’s goals and resources. A critical skill for identifying anomalies within systems is the ability to interpret network architecture and recognize unusual patterns in both endpoint activity and network traffic.  

With this foundation in mind, let’s zoom out and look at the bigger picture—the network itself.  

---

## Understanding the Network: A High-Level Overview

More often than not, bad actors deploy malware on a victim’s system to disrupt services or exfiltrate information. While attackers may disguise malware by running it under legitimate processes, they cannot alter the fundamental behavior of the operating system or the network. This is why a solid understanding of **networking fundamentals** is essential for every threat hunter.  

Here are some basic networking concepts:  

- **Client-server vs. peer-to-peer (P2P):** In client-server setups, a central server provides services to clients. In P2P (like torrents), devices share files directly.  
- **VLANs:** Virtual LANs group devices so they act as if they’re on the same wire. Traffic cannot cross between VLANs without a router or layer 3 switch, which adds segmentation and security.  
- **Gateways and routers:** A gateway connects different networks. Routers sit between your internal network and the internet, translating private addresses into public ones via **NAT (Network Address Translation)**.  
- **Switches and bridges:** Switches use MAC addresses to forward packets efficiently within a network. Bridges connect separate networks as if they were one.  
- **Protocols:** Protocols define how systems communicate. Some common ones include DHCP (assigns IPs to devices), TCP/UDP (transport), DNS (resolves names to IPs), and HTTP/HTTPS (web traffic).  
- **Wi-Fi essentials:** SSID names, encryption, and channels all affect security and performance.  

Understanding these fundamentals is key to seeing how data flows. But networks aren’t the only valuable source of information—operating systems, especially Windows, provide a wealth of logs for deeper analysis.  

---

## Log Sources in Windows Machines

In Windows environments, one of the richest sources of log data is the **Event Viewer**, which stores several categories of logs:  

- **Application logs:** Activities of installed applications.  
- **Security logs:** Logins, audits, and account activity.  
- **Setup logs:** OS updates and upgrades.  
- **Application and service logs:** A deeper dive into Microsoft and third-party applications.  

Advanced tools extend logging even further:  

- **Windows Management Instrumentation (WMI):** Enables local and remote management data collection.  
- **Event Tracing for Windows (ETW):** Captures kernel-level events efficiently.  
- **Sysmon (System Monitor):** Adds detailed process and driver activity logging.  
- **File Integrity Monitoring (FIM):** Watches for changes to critical files.  
- **PowerShell logs:** A critical source of information, since many attackers abuse PowerShell to execute malicious commands.  

While Windows provides a broad view of what’s happening on endpoints, the larger infrastructure—routers, DNS servers, and security tools—adds even more visibility into potential threats.  

---

## Logs from Networking Tools

Beyond endpoints, networking gear and infrastructure also generate crucial logs:  

- **Routers and switches:** Record traffic patterns and connectivity.  
- **DNS servers:** Show which domains are being queried.  
- **Web servers:** Log requests and responses to hosted content.  
- **Active Directory and Kerberos:** Track user authentication and access attempts.  
- **IAM/PAM systems:** Record privileged access and identity events.  

Security software also provides valuable insights. For example, **Windows Defender**, the native antivirus software for Windows, produces logs in Event Viewer that may indicate malware activity. Antivirus alerts, when correlated with threat intelligence, can even reveal links to advanced persistent threat (APT) groups.  

When all of these logs are combined—endpoint, operating system, and infrastructure—they form a holistic view of the environment. That’s where real threat hunting begins.  

---

## Pulling It All Together

Ultimately, threat hunting is about correlating logs collected from **endpoints, networks, and security systems**. A summary of the logs from each of these three categories includes:  

- **Endpoints:** Application, system, PowerShell, and Sysmon logs.  
- **Networks:** Router, switch, DNS, and web server data.  
- **Security systems:** Active Directory, Kerberos, IAM, antivirus, and EDR tools.  

By combining these data sources and layering them on top of a solid understanding of the organization’s system infrastructure, security analysts can move beyond random alerts and begin identifying real threats hiding in plain sight.  

---

Last but not least, there is no “one-size-fits-all” data source in threat hunting. Effective hunting requires a deep understanding of the environment, the ability to interpret logs, and the context to relate them back to an organization’s unique needs.  

The insights presented here are adapted from _Practical Threat Intelligence and Data-Driven Threat Hunting_, **Chapter 3: Where Does the Data Come From**, by Valentina Palacín.  

---
title: "Threat Hunting Through Logs and Networking"
date: 2025-09-03T10:30:30-05:00
categories:
  - blog
tags:
  - Threat Hunting
  - Logs
  - Networking
---

When it comes to threat hunting, the most valuable resource isn’t a fancy tool or a high-end appliance—it’s **data**. Without data, analysts have nothing to investigate. But where exactly does this data come from? And how does the underlying network shape what we see in our logs? Let’s break this down gradually.

---

## The Foundation: Logs as Data Sources

At the core, **system logs** and **network logs** are the main sources of information for threat hunters. Logs are essentially records of events—who logged in, what process started, what file was changed, or what request was made to a server.

Every log file is made up of entries, and those entries can contain four main types of information:

- **Usage information** (how systems or apps are used)  
- **Client requests and server responses**  
- **Account activity** (logins, permissions, etc.)  
- **Operational actions** (system changes, updates, etc.)  

There isn’t a “perfect” set of logs or a single right amount of data. What’s useful depends on the organization’s goals and resources. A key skill is learning how to interpret the network architecture and spot unusual patterns in both endpoint activity and network traffic.

---

## Understanding the Network: Why Basics Matter

Malware may disguise itself by running under legitimate processes, but it can’t change how the operating system or the network itself works. That’s why learning **networking fundamentals** is so important for a threat hunter.

Here are some essentials:

- **Client-server vs. peer-to-peer (P2P):** In client-server setups, a central server provides services to clients. In P2P (like torrents), devices share files directly.  
- **VLANs:** Virtual LANs group devices so they act as if they’re on the same wire. Traffic can’t cross between VLANs without a router or layer 3 switch, which adds segmentation and security.  
- **Gateways and routers:** A gateway connects different networks. Routers sit between your internal network and the internet, translating private addresses into public ones via **NAT (Network Address Translation)**.  
- **Switches and bridges:** Switches use MAC addresses to forward packets efficiently inside a network. Bridges connect separate networks as if they were one.  
- **Protocols:** Common ones include DHCP (hands out IPs to devices), TCP/UDP (transport), DNS (resolves names to IPs), and HTTP/HTTPS (web traffic).  
- **Wi-Fi essentials:** SSID names, encryption, and channels all affect security and performance.  

Together, these basics explain how data moves—and what types of logs we can expect.

---

## Windows as a Log Goldmine

If you’re using Windows, one of the richest sources of log data is the **Event Viewer**. It stores several categories of logs:

- **Application logs:** Activities of installed apps.  
- **Security logs:** Logins, audits, and account activity.  
- **Setup logs:** OS updates and upgrades.  
- **Application and service logs:** A deeper dive into Microsoft and third-party apps.  

Advanced tools extend this further:

- **Windows Management Instrumentation (WMI):** Enables local and remote management data collection.  
- **Event Tracing for Windows (ETW):** Captures kernel-level events efficiently.  
- **Sysmon (System Monitor):** Adds detailed process and driver activity logging.  
- **File Integrity Monitoring (FIM):** Watches for changes to critical files.  
- **PowerShell logs:** Critical because many attackers abuse PowerShell to execute malicious commands.  

---

## Network and Security Data Sources

Outside endpoints, networking gear and infrastructure also generate crucial logs:

- **Routers and switches:** Record traffic patterns and connectivity.  
- **DNS servers:** Show what domains are being queried.  
- **Web servers:** Log requests and responses to hosted content.  
- **Active Directory and Kerberos:** Track user authentication and access attempts.  
- **IAM/PAM systems:** Record privileged access and identity events.  

Security software contributes as well. For instance, **Windows Defender** produces logs inside Event Viewer that may indicate malware activity. Antivirus alerts, when mapped with threat intelligence, can even reveal links to advanced persistent threat (APT) groups.

---

## Pulling It All Together

Ultimately, threat hunting is about connecting the dots between **endpoints, networks, and security systems**. Each of these three categories produces logs that provide clues:

- **Endpoints:** Application, system, PowerShell, and Sysmon logs.  
- **Networks:** Router, switch, DNS, and webserver data.  
- **Security systems:** Active Directory, Kerberos, IAM, antivirus, and EDR tools.  

By combining these data sources and layering them over a solid understanding of how networks function, threat hunters can move beyond random alerts and start identifying real threats hiding in plain sight.

---

### Key Takeaway

There’s no “one-size-fits-all” data source. Effective threat hunting comes from knowing your environment, understanding its logs, and interpreting them through the lens of networking fundamentals.

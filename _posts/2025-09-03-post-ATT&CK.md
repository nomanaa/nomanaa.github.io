---
title: "Understanding Adversary Behavior with the MITRE ATT&CK Framework"
date: 2025-09-05 11:30:00 -0500
categories:
  - blog
tags:
  - MITRE ATT&CK
  - Threat Hunting
  - Cybersecurity
---
*"If you know the enemy and know yourself, you need not fear the result of a hundred battles."* — Sun Tzu, *The Art of War*  

In cybersecurity, this principle holds true: defending effectively requires understanding how attackers think and how they exploit systems. The MITRE ATT&CK framework provides a structured way to do exactly that. This blog post aims to explain how to replicate adversary behavior and how to work with the MITRE ATT&CK framework. We’ll explore what ATT&CK is, the 14 tactics it covers, and how mapping with ATT&CK helps blue and red teams understand adversary techniques.  

---

# What is The ATT&CK Framework? 

According to *Practical Threat Intelligence and Data-Driven Threat Hunting* by Valentina Palacín,  

> *“The ATT&CK Framework is a descriptive model used to label and study the activities that a threat actor is capable of carrying out in order to get a foothold and operate inside an enterprise environment, a cloud environment, smartphones, or even industrial control systems.”*  

Key features of the ATT&CK Framework include:  
- Provides a **common taxonomy** for the cybersecurity community to describe adversary behavior.  
- Serves as a **common language** for both offensive and defensive researchers.  
- Contains **14 main tactics** that represent different stages of an attack.
    
---

## Tactics, Techniques and Procedures 

The MITRE ATT&CK framework is organized into 14 tactics, each representing an attacker’s objective and containing a set of related techniques. In other words, a tactic explains the *“why”* behind an adversary’s behavior.  
The list of tactics are below: 

1. **Reconnaissance:** The objective of this tactic is to gather as much information as possible about the victim.  
2. **Resource Development:** In this stage, the attacker assesses the resources they can use to support the operation. This can range from legitimate tools to stolen software. *(Reconnaissance and Resource Development fall into the pre-breach stage.)*  
3. **Initial Access:** The attacker’s first step into the victim’s environment, where they manage to gain a foothold in the network.  
4. **Execution:** In this tactic, the attacker attempts to run malicious code inside the environment.  
5. **Persistence:** The threat actor uses techniques in this category to remain in the system even after reboots or shutdowns.  
6. **Privilege Escalation:** The threat actor uses techniques to elevate access after entering with a low-privilege account.  
7. **Defense Evasion:** The threat actor avoids detection by altering, disabling, or removing traces of their activity.  
8. **Credential Access:** At times the threat actor steals legitimate credentials to gain further access into the system.  
9. **Discovery:** Techniques involving learning about the victim’s environment, infrastructure, and setup.  
10. **Lateral Movement:** After understanding the victim’s network infrastructure, the attacker pivots from one system to another.  
11. **Collection:** Gathering information and data for later exfiltration.  
12. **Command and Control:** Techniques used by the threat actor to communicate with systems under their control.  
13. **Exfiltration:** Stealing data while remaining undetected, or in some cases encrypting it for ransom.  
14. **Impact:** Techniques aimed at preventing the victim from accessing systems or data, often causing disruption or damage.  

Each tactic includes many **techniques**, which are further broken down into **sub-techniques**. The most specific level is the **procedure**—the exact command or method an adversary uses.  

**Example:** For example, in the ATT&CK framework the **tactic** might be *Credential Access*—the attacker’s goal is to steal usernames and passwords. One **technique** used to achieve this is *Keylogging*, where keystrokes are secretly recorded. The specific **procedure** could be installing and running a malicious program (e.g., `keylogger.exe`) that captures every keystroke and sends it back to the attacker’s server.   

---

# The ATT&CK Matrix

The **ATT&CK Matrix** is the primary tool used to visualize the framework:  
- **Columns = Each column represent a Tactic**  
- **Techniques = Listed under each tactic**  
- **Sub-techniques = Expandable under techniques**  

Each technique page includes:  
- The technique’s name and description.  
- A list of sub-techniques.  
- The platforms it applies to.  
- Data sources for detecting related activity.  
- Mitigation strategies to counter the behavior.  

This consistent structure makes ATT&CK a powerful resource for planning both **Blue Team** and **Red Team** exercises.  

---

# Mapping with ATT&CK

Mapping is the process of linking observed activity to the ATT&CK framework in order to identify an attacker’s behavior. It helps security team answer key questions such as:  
- Which tactic does this activity belong to?  
- Which technique or sub-technique was used?  
- What procedures did the adversary carry out?  

By mapping logs or alerts to ATT&CK, organizations can uncover gaps in their defenses and strengthen their detection strategies.  

---

# The ATT&CK Navigator

The **ATT&CK Navigator** is an interactive way to work with the matrix. It allows users to highlight, score, and layer techniques for analysis.

The online version can be found here : [MITRE ATT&CK Navigator](https://mitre-attack.github.io/attacknavigator/)

---

The **MITRE ATT&CK framework** provides defenders and researchers with a structured way to understand and anticipate adversary behavior. By studying the 14 tactics, exploring the associated techniques, and mapping activity back to ATT&CK, security teams can replicate adversary actions in a controlled environment and strengthen their defenses. Tools like the ATT&CK Navigator make this process more interactive and practical for both Blue and Red Team exercises.  

These insights are drawn from *Practical Threat Intelligence and Data-Driven Threat Hunting*, **Chapter 4: Mapping the Adversary**, by Valentina Palacín.  



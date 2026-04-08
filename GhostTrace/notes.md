# GhostTrace – Notes & Concepts

This file contains brief explanations of key concepts, tools, and techniques observed during the investigation.

---

## Phishing (Initial Access)

Phishing is a social engineering technique used to trick users into executing malicious files or revealing sensitive information.

In this case, the attacker delivered a macro-enabled document (`.docm`) which executed malicious code when opened.

---

## Macros

Macros are embedded scripts in Office documents. While they are intended for automation, they are often abused to execute malicious commands on a system.

---

## Command and Control (C2)

Command and Control refers to communication between a compromised system and an attacker-controlled server.

This allows the attacker to:
- Execute commands remotely
- Upload/download files
- Maintain access to the system

---

## Reverse Shell

A reverse shell is a connection initiated from the victim machine back to the attacker.

This allows the attacker to gain interactive access to the system, often bypassing firewall restrictions.

---

## PowerView

PowerView is a PowerShell-based tool used for Active Directory enumeration.

It can be used to:
- List users and groups
- Identify privileged accounts
- Discover domain relationships

---

## Active Directory Enumeration

This refers to gathering information about the domain environment, such as users, groups, services, and permissions.

Attackers use this information to identify high-value targets.

---

## Kerberos-Based Techniques (Kerberoasting)

Kerberos is an authentication protocol used in Active Directory environments.

Kerberoasting is a technique where an attacker:
1. Requests a service ticket (TGS) for a service account
2. Extracts the ticket
3. Attempts to crack it offline to recover the account’s password

Service accounts are often targeted because they may have weak passwords and elevated privileges.

---

## Credential Dumping

Credential dumping involves extracting usernames and passwords (or hashes) from memory.

Attackers often target the LSASS process to retrieve:
- Cleartext passwords
- NTLM hashes
- Kerberos tickets

---

## Lateral Movement

Lateral movement is the process of moving from one compromised system to another within the network.

This allows the attacker to expand access and reach more critical systems (e.g., the domain controller).

---

## Privilege Escalation

Privilege escalation occurs when an attacker gains higher-level permissions than initially obtained.

In this case, the attacker escalated to Domain Administrator privileges.

---

## Persistence

Persistence refers to techniques used by attackers to maintain access to a system even after reboot or detection.

Common methods include:
- Creating services
- Scheduled tasks
- Registry modifications

---

## Services (Persistence)

Attackers can create malicious services that execute automatically when the system starts.

---

## Scheduled Tasks

Scheduled tasks can be used to execute malicious code at specific times or system events.

---

## Registry Persistence

Attackers can modify Windows Registry keys to ensure malicious programs run automatically.

---

## Sysmon

Sysmon (System Monitor) is a Windows tool that logs detailed system activity, including:

- Process creation
- Network connections
- File changes

It is widely used for threat detection and forensic analysis.

---

## Windows Event Logs

Windows Event Logs record system and security events such as:

- Logins
- Process execution
- Service creation

They are essential for investigating security incidents.

---

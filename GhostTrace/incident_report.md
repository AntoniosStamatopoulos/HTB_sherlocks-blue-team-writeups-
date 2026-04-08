# GhostTrace – Incident Investigation Report

## Case Information

- Case Name: GhostTrace  
- Environment: Main.local  
- Systems Involved: DC01, Client02, Client03  
- Data Sources: Windows Event Logs, Sysmon  
- Analyst: Antonios Stamatopoulos  

---

## Summary

A security incident was identified within the Main.local Active Directory environment following a phishing attack. 

The attacker successfully gained initial access through a malicious document, established command and control, and proceeded with domain enumeration and credential harvesting.

The activity escalated to lateral movement across multiple hosts, credential dumping, and ultimately full domain compromise. Persistence mechanisms were deployed on the domain controller to maintain long-term access.

---

## Initial Access

- Malicious Attachment: `Profits.docm`  
- Source IP: `192.168.204.152`  

A user on Client02 opened a phishing document containing embedded macros. Execution of the macros triggered malicious activity on the host.

---

## Command and Control

- Remote Endpoint: `192.168.204.152:4444`  

Following execution, the compromised system initiated outbound communication to an attacker-controlled IP, establishing the initial command and control channel.

---

## Payload Execution

- Second-stage Payload: `UpdatePolicy.exe`  
- Reverse Shell Port: `1337`  

The attacker deployed a secondary payload, which provided interactive shell access to Client02.

---

## Enumeration

- Tool Used: `PowerView.ps1`  

The attacker performed Active Directory enumeration to identify high-value targets, including service accounts and privileged users.

---

## Credential Access

### Service Account Abuse

- Target Account: `sqlsvc`  
- First Successful Login: `2025-05-25 04:03:47 UTC`  

The attacker leveraged Kerberos-based techniques to obtain and crack credentials for a service account.

---

### Credential Dumping

- Tool Used: `netdiag.exe`  
- Compromised Account: `lucas`  

On Client03, the attacker extracted cleartext credentials directly from memory.

---

### Domain Credential Extraction

- Execution Time: `2025-05-25 04:26:36 UTC`  

Using compromised credentials, the attacker performed a domain-level credential extraction attack, expanding access across the environment.

---

## Privilege Escalation

- Administrator Authentication: `2025-05-25 04:34:01 UTC`  

The attacker successfully authenticated using a domain administrator account, achieving full control of the domain.

---

## Lateral Movement

The attacker moved between Client02 and Client03 to harvest additional credentials and expand access before targeting the domain controller.

---

## Persistence

Persistence mechanisms were established on DC01:

- Service: `WindowsUpdateSvc`  
- Scheduled Task: `WindowsUpdateCheck`  
- Registry Key: `xcvafctr`  

These mechanisms ensured continued access even after potential system reboots or remediation attempts.

---

## Key Observations

- Initial access was achieved through macro-enabled phishing  
- PowerShell-based tools were used for stealthy enumeration  
- Service accounts were targeted for privilege escalation  
- Credential dumping enabled rapid expansion of access  
- Persistence was established using multiple techniques on the domain controller  

---

## Conclusion

The incident demonstrates a complete attack chain from initial phishing access to full Active Directory compromise.

The attacker combined multiple techniques, including command and control, credential harvesting, lateral movement, and persistence, to maintain control over the environment.

Effective detection would require early identification of macro execution, unusual outbound connections, and suspicious authentication activity across domain systems.

---

# GhostTrace – Blue Team Writeup

This writeup analyzes a simulated security breach in an Active Directory environment (Main.local) as part of the Hack The Box Sherlock challenge "GhostTrace".

The investigation is based on Windows Event Logs and Sysmon data collected from multiple hosts, including a Domain Controller and client machines.

---

## Summary

The attack began with a phishing email that led to initial compromise and execution of malicious code. The attacker established command and control, performed Active Directory enumeration, and obtained credentials through multiple techniques.

This access enabled lateral movement, privilege escalation, and ultimately full domain compromise.

---

## Key Areas Covered

- Initial access via phishing
- Command and control activity
- Active Directory enumeration
- Credential access techniques
- Lateral movement and privilege escalation
- Persistence mechanisms

---

## Outcome

The analysis reconstructs the attack chain and identifies the key artifacts, attacker actions, and persistence methods used to maintain access to the domain.

---

# GhostTrace – Active Directory Investigation Lab

This repository contains the analysis of the "GhostTrace" Sherlock challenge from Hack The Box.

The scenario simulates a suspected security breach within an Active Directory environment named `Main.local`, where multiple systems have been compromised following a phishing attack.

---

## Scenario Overview

The environment consists of:

- DC01 – Domain Controller  
- Client02 – Domain-joined workstation  
- Client03 – Domain-joined workstation  

The attack begins when a user interacts with a phishing email, leading to the execution of malicious code. From this initial access point, the attacker progresses through multiple stages, ultimately compromising the domain.

---

## Objective

The goal of this investigation is to analyze Windows Event Logs and Sysmon data in order to:

- Reconstruct the full attack chain  
- Identify attacker actions across hosts  
- Detect credential access techniques  
- Trace lateral movement within the network  
- Identify persistence mechanisms on the domain controller  

---

## Approach

The analysis follows a structured incident response methodology, examining activity across endpoints and correlating events to build a complete timeline of the compromise.

---

## Expected Outcome

By completing this investigation, the analyst will gain a clear understanding of how the attack unfolded, from initial access to full domain compromise, and how different techniques were used to maintain persistence within the environment.

---

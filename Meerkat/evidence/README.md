# Evidence

This directory contains extracted HTTP request logs used during the investigation.

These artifacts were analyzed to identify key stages of the attack, including authentication attempts, exploitation of the application, and post-exploitation activity.

Specifically:

* `login_attempts.txt` was used to analyze login behavior and identify indicators related to exploitation and authorization bypass.
* `exploit_requests.txt` was used to examine attacker actions after successful authentication, including payload delivery, command execution, and persistence mechanisms.

The evidence provided in these files supports multiple investigation tasks and helps reconstruct the attacker’s activity within the compromised system.

# SSH Brute-Force Detection

A SOC lab project: ran a password-guessing attack against my own Ubuntu VM's SSH service, detected it with Wazuh, and wrote up the full investigation.

> All attacks were run only against virtual machines that I own, on an isolated network.

## Lab setup
| Machine | Role |
|---|---|
| Ubuntu VM | Target (SSH server, Wazuh agent) |
| Attacker machine | Source of login attempts |
| Wazuh server | SIEM: collects logs, raises alerts |

## Report
**[Read the full write-up →](writeups/project-01-ssh-bruteforce.md)**

Covers the attack, the raw `auth.log` evidence, the Wazuh alert escalation (rule 5710 → rule 2502), the MITRE ATT&CK mapping (T1110), and the response steps.

## Repo layout
| Folder | What is inside |
|---|---|
| `writeups/` | The incident write-up |
| `detections/` | Detection rules and queries |

## Skills shown
Log analysis, SIEM alerting (Wazuh), SSH brute-force detection, MITRE ATT&CK mapping, incident reporting.

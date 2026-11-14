# Detection: SSH Brute Force (Password Guessing)

MITRE ATT&CK: T1110 (Brute Force), T1110.001 (Password Guessing)
Data source: Linux auth.log via Wazuh agent (sshd logs)

## Wazuh rules used
| Rule ID | Level | Trigger |
|---|---|---|
| 5710 | 5 | Single SSH login attempt for a non-existent user |
| 5503 | 5 | Single PAM login failure |
| 2502 | 10 | Multiple password failures from the same source within Wazuh correlation window |

## Manual log search (if no SIEM is available)
```bash
sudo grep "Failed password" /var/log/auth.log | awk {for(i=1;i<=NF;i++) if($i=="from") print $(i+1)} | sort | uniq -c | sort -nr
```
Flag any IP with 5+ failures inside a 1-2 minute window.

## Suggested threshold for a custom rule
5 or more failed SSH logins from one source IP within 60 seconds = brute-force alert.

# Windows Failed-Login Monitoring

A SOC lab project: generate failed and successful Windows logons on purpose, find them in Event Viewer, and detect them with Wazuh.

> All activity was run only on a VM that I own.

## Lab setup
| Machine | Role |
|---|---|
| Windows VM | Target (Security event log, Wazuh agent) |

## Report
**[Read the full write-up ->](writeups/windows-failed-login-monitoring.md)** (coming soon)

Covers Event IDs 4624 (successful logon), 4625 (failed logon) and 4672 (admin privileges assigned), with Wazuh alert correlation and a MITRE ATT&CK mapping.

## Repo layout
| Folder | What is inside |
|---|---|
| `writeups/` | The incident write-up |
| `detections/` | Detection rules and queries |

## Skills shown
Windows event log analysis, SIEM alerting (Wazuh), account/privilege monitoring, incident reporting.

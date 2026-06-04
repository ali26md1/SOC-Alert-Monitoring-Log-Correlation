Professional README Description
--------------------------------
This project demonstrates a complete Security Operations Center (SOC) investigation workflow using the Wazuh SIEM/XDR platform in a virtual lab environment. The system collects and correlates authentication logs, syslog events, SELinux audit logs, and Windows Event logs to detect suspicious activities and reconstruct attack chains.

The investigation identified a brute-force login attack by correlating PAM authentication failures, SELinux access violations, and successful login sessions. Alerts were analyzed using Threat Hunting techniques and mapped to the MITRE ATT&CK framework (T1078 – Valid Accounts), along with compliance monitoring for PCI-DSS, HIPAA, GDPR, and NIST 800-53.

Features
---------
Real-time SOC alert monitoring
Log correlation across multiple sources
Brute-force attack detection and analysis
Threat hunting with Wazuh SIEM/XDR
MITRE ATT&CK mapping
Compliance monitoring (PCI-DSS, HIPAA, GDPR, NIST)
Linux & Windows agent monitoring
Security event investigation workflow

Tech Stack
-----------
Wazuh SIEM/XDR
Linux (Syslog, PAM, Auditd, SELinux)
Windows Event Logs
Threat Hunting & Log Analysis
MITRE ATT&CK Framework

Architecture Diagram
-----------
```
Attacker (Brute Force Attempt)
   ↓
Linux Target Host
   ↓
Wazuh Agent (Event Collection)
   ├─ PAM Logs
   ├─ Syslog
   ├─ Auditd
   └─ SELinux Logs
   ↓
Wazuh Manager (Log Aggregation & Correlation)
   ↓
Alert Generation & Threshold Detection
   ↓
SOC Analyst Investigation & Threat Hunting
   ↓
MITRE ATT&CK Mapping & Incident Response
```

MITRE ATT&CK Techniques
-----------
| Technique | Technique ID | Tactic | Evidence |
|-----------|-----------|--------|----------|
| Valid Accounts | T1078 | Initial Access, Persistence | Successful login after failed attempts |
| Brute Force | T1110 | Credential Access | Multiple PAM authentication failures |
| Account Discovery | T1087 | Discovery | System reconnaissance via login attempts |
| System Information Discovery | T1082 | Discovery | Potential privilege escalation attempts |

Investigation Timeline
-----------
| Time | Event | Details |
|------|-------|---------|
| 10:00 AM | Initial Alert | Multiple PAM authentication failures detected on Linux host |
| 10:02 AM | Pattern Recognition | Wazuh correlated failed attempts with SELinux violations |
| 10:05 AM | Escalation | SELinux access denial logged during attack phase |
| 10:08 AM | Breach Confirmed | Successful login observed in authentication logs |
| 10:10 AM | Response Initiated | Incident escalated to SOC team for analysis |
| 10:15 AM | Threat Assessment | Cross-referenced with Windows Event Logs for broader context |
| 10:20 AM | Analysis Complete | Attack mapped to MITRE ATT&CK T1078 & T1110 |

Project Structure
-----------
```
SOC-Alert-Monitoring-Log-Correlation/
│
├── README.md
├── screenshots/
│   ├── wazuh-dashboard.png
│   ├── alerts.png
│   └── [other investigation screenshots]
│
├── reports/
│   ├── SOC_Alert_Monitoring_Presentation.pptx
│   └── incident-report.pdf
│
├── logs/
│   └── sample-logs.csv
│
└── findings/
    └── attack-analysis.md
```

Project Files
-----------
📊 **reports/SOC_Alert_Monitoring_Presentation.pptx** - Comprehensive presentation slides covering the SOC investigation workflow, findings, and threat analysis

📄 **reports/incident-report.pdf** - Detailed project report with methodology, investigation steps, and recommendations

📋 **logs/sample-logs.csv** - Raw log data and security events collected during the investigation

📸 **screenshots/** - Directory containing screenshots of Wazuh dashboard, alerts, and investigation findings

📝 **findings/attack-analysis.md** - In-depth attack analysis, MITRE ATT&CK mapping, compliance impact assessment, and recommendations

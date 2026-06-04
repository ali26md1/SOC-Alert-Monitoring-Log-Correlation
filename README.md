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

Project Files
-----------
📊 **SOC_Alert_Monitoring_Presentation.pptx** - Comprehensive presentation slides covering the SOC investigation workflow, findings, and threat analysis

📄 **SOC_Project_Report.pdf** - Detailed project report with methodology, investigation steps, and recommendations

📋 **events-2026-04-08T18_27_59.401Z (1).csv** - Raw log data and security events collected during the investigation

📸 **Screenshots-Capstone_Project/** - Directory containing screenshots of Wazuh dashboard, alerts, and investigation findings

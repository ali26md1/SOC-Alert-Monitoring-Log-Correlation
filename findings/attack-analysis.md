# SOC Alert Monitoring - Attack Analysis

## Executive Summary

This document provides a comprehensive analysis of the brute-force login attack detected and investigated using the Wazuh SIEM/XDR platform.

## Attack Detection Architecture

```
Attacker (Remote Brute Force)
   ↓
Linux Target Host (Vulnerable System)
   ├─ PAM Authentication Module
   ├─ Syslog Facility
   ├─ Auditd Daemon
   └─ SELinux Module
   ↓
Wazuh Agent (Real-time Log Collection)
   ├─ Captures failed login attempts
   ├─ Detects SELinux denials
   └─ Tracks successful authentications
   ↓
Wazuh Manager (Centralized Analysis)
   ├─ Log Aggregation
   ├─ Pattern Matching
   ├─ Correlation Engine
   └─ Alert Generation
   ↓
Alert Threshold Triggered → HIGH SEVERITY
   ↓
SOC Analyst Dashboard & Investigation
   ├─ Threat Hunting
   ├─ Context Analysis
   └─ MITRE ATT&CK Mapping
   ↓
Incident Response & Containment
```

## Attack Timeline

### Detected Indicators
- Multiple failed PAM authentication attempts
- SELinux access violations
- Successful login session establishment
- Log correlation across Linux and Windows systems

## Attack Classification

**MITRE ATT&CK Mapping:** T1078 – Valid Accounts
- **Tactic:** Defense Evasion, Persistence, Privilege Escalation, Initial Access
- **Technique:** Valid Accounts
- **Attack Pattern:** Brute-force credentials

### Related Techniques

| Technique | Technique ID | Tactic | Description |
|-----------|-----------|--------|-------------|
| Valid Accounts | T1078 | Initial Access, Persistence | Attacker used legitimate account credentials |
| Brute Force | T1110 | Credential Access | Attempted password guessing against multiple accounts |
| Account Discovery | T1087 | Discovery | Reconnaissance to identify valid accounts |
| System Information Discovery | T1082 | Discovery | Gathering system information for privilege escalation |
| Privilege Escalation | T1548 | Privilege Escalation | Attempt to escalate privileges post-compromise |

## Investigation Findings

### Attack Timeline

| Time | Event | Component | Details |
|------|-------|-----------|---------|
| 10:00 AM | Initial Alert Triggered | Wazuh Manager | Multiple PAM authentication failures detected on target Linux host |
| 10:02 AM | Pattern Recognition | Log Correlation Engine | Failed attempts correlated with SELinux access violations |
| 10:05 AM | Escalation Alert | Security Rules | SELinux denial audit log generated during attack phase |
| 10:08 AM | Breach Confirmation | Authentication Logs | Successful login session established post-attack attempts |
| 10:10 AM | Incident Response | SOC Team | Attack escalated for immediate investigation and response |
| 10:15 AM | Context Analysis | Windows Integration | Cross-referenced with Windows Event Logs for lateral movement indicators |
| 10:20 AM | Threat Mapping | MITRE ATT&CK | Attack mapped to T1078 (Valid Accounts) and T1110 (Brute Force) |
| 10:30 AM | Containment | Incident Response | Access review initiated, suspicious session isolated |

### Stage 1: Initial Detection
- Alert triggered by multiple authentication failures
- Pattern recognized as potential brute-force attack
- Real-time Wazuh alerts enabled rapid response

### Stage 2: Correlation Analysis
- Cross-referenced PAM logs with SELinux audit logs
- Identified successful session after failed attempts
- Correlated with Windows Event logs for broader threat picture

### Stage 3: Threat Assessment
- Attack severity: High
- Attack complexity: Low
- Attacker sophistication: Medium

## Compliance Impact

### Standards Affected
- **PCI-DSS**: Violation of access controls (Requirement 2.1, 2.2)
- **HIPAA**: Potential unauthorized access to protected health information
- **GDPR**: Data protection concerns with potential unauthorized access
- **NIST 800-53**: Control AC-2 (Account Management) compromised

## Recommendations

1. **Immediate Actions**
   - Force password reset for affected accounts
   - Enable multi-factor authentication (MFA)
   - Review and revoke unnecessary access privileges

2. **Short-term Mitigation**
   - Implement account lockout policies after failed login attempts
   - Deploy intrusion prevention rules
   - Increase monitoring threshold sensitivity

3. **Long-term Strategy**
   - Implement Zero Trust architecture
   - Deploy behavioral analytics for anomaly detection
   - Establish incident response playbooks
   - Conduct security awareness training

## Conclusion

The brute-force attack was successfully detected and contained through real-time log correlation and threat hunting. The Wazuh SIEM/XDR platform proved effective in identifying the attack pattern and enabling rapid response.

---

*Generated: June 4, 2026*
*Classification: Internal Use*

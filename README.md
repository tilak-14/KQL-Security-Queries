# KQL Threat Hunting Query Library
**By Tilak Kalas | Cloud Security Engineer**

A library of 30 production-ready KQL queries for Microsoft Sentinel, 
mapped to MITRE ATT&CK techniques. These queries detect real-world 
attack patterns across identity, endpoint, cloud, and data exfiltration.

## Library Structure

| Folder | Queries | What it detects |
|--------|---------|-----------------|
| Identity | 8 | Brute force, password spray, impossible travel, MFA bypass |
| Endpoint | 7 | Lateral movement, PowerShell abuse, ransomware, LOLBins |
| Cloud | 7 | Resource deletion, role hijacking, cryptomining, firewall tampering |
| DataExfiltration | 5 | Email forwarding, mass download, insider threat |
| Correlation | 3 | Full attack chains spanning multiple tables |

## MITRE ATT&CK Coverage

| Technique ID | Name | Query |
|-------------|------|-------|
| T1110 | Brute Force | brute_force_detection.kql |
| T1110.003 | Password Spraying | password_spray.kql |
| T1078 | Valid Accounts | impossible_travel.kql, new_country_login.kql |
| T1021 | Remote Services | lateral_movement.kql |
| T1059.001 | PowerShell | malicious_powershell.kql |
| T1027 | Obfuscated Files | encoded_command.kql |
| T1218 | System Binary Proxy | suspicious_parent_process.kql |
| T1490 | Inhibit System Recovery | ransomware_shadow_copy.kql |
| T1485 | Data Destruction | resource_deletion.kql |
| T1496 | Resource Hijacking | vm_creation_burst.kql |
| T1562 | Impair Defenses | firewall_tampering.kql, security_policy_deletion.kql |
| T1114.003 | Email Forwarding Rule | email_forwarding_rule.kql |
| T1039 | Data from Network Share | mass_sharepoint_download.kql |
| T1048 | Exfiltration | external_file_sharing.kql |
| T1070 | Indicator Removal | bulk_email_deletion.kql |

## Environment
All queries include two versions:
- **Real Sentinel version** — for Microsoft Sentinel environments
- **Practice version** — tested on Azure Data Explorer StormEvents

## About
Built as part of Cloud Security Engineer career development.
Covers: SigninLogs, SecurityEvent, DeviceProcessEvents, AzureActivity, OfficeActivity
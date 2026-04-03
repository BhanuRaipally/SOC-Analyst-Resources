# SOC Analyst Resources 🔍

A comprehensive collection of SOC analyst study 
materials, references, and notes.

## 📁 Contents
- MITRE ATT&CK Notes
- Windows Event IDs Reference
- Splunk SPL Queries
- Incident Response Checklist
- SOC Analyst Daily Tasks

## 🧠 MITRE ATT&CK Framework

| Tactic | Description | Example |
|--------|-------------|---------|
| Reconnaissance | Gathering target info | Port scanning |
| Initial Access | Getting into system | Phishing |
| Execution | Running malicious code | PowerShell |
| Persistence | Maintaining access | Registry keys |
| Privilege Escalation | Gaining higher access | Token impersonation |
| Defense Evasion | Avoiding detection | Log clearing |
| Lateral Movement | Moving through network | Pass the hash |
| Exfiltration | Stealing data | Data compression |

## 📋 Windows Event IDs Reference

| Event ID | Description | Significance |
|----------|-------------|--------------|
| 4624 | Successful login | Monitor unusual logins |
| 4625 | Failed login | Brute force indicator |
| 4648 | Login with explicit credentials | Pass-the-hash |
| 4688 | New process created | Malicious process |
| 4698 | Scheduled task created | Persistence |
| 4720 | User account created | Unauthorized account |
| 4732 | User added to group | Privilege escalation |
| 7045 | New service installed | Malware installation |

## 🔍 Splunk SPL Queries

### Detect Failed Logins
index=windows EventCode=4625
| stats count by src_ip, user
| where count > 5
| sort -count

### Detect New Process Creation
index=windows EventCode=4688
| table _time, ComputerName, New_Process_Name

## ✅ Incident Response Checklist

### Phase 1 — Preparation
- [ ] Ensure SIEM is configured
- [ ] Maintain asset inventory
- [ ] Define escalation procedures

### Phase 2 — Detection
- [ ] Monitor SIEM alerts
- [ ] Identify indicators of compromise
- [ ] Classify alert as true/false positive

### Phase 3 — Containment
- [ ] Isolate affected systems
- [ ] Block malicious IPs/domains
- [ ] Preserve evidence

### Phase 4 — Eradication
- [ ] Remove malware
- [ ] Patch vulnerabilities
- [ ] Reset compromised credentials

### Phase 5 — Recovery
- [ ] Restore systems from backup
- [ ] Monitor for reinfection
- [ ] Resume normal operations

### Phase 6 — Lessons Learned
- [ ] Document incident timeline
- [ ] Identify gaps in detection
- [ ] Update playbooks

## 📚 References
- [MITRE ATT&CK](https://attack.mitre.org)
- [Azure Sentinel Docs](https://docs.microsoft.com/azure/sentinel)
- [Splunk Docs](https://docs.splunk.com)

# SOC Analyst Portfolio

## Portfolio Overview

This repository contains hands-on SOC analyst labs, detection projects, and investigation writeups focused on log analysis, threat detection, phishing analysis, incident response, and network traffic investigation.

The goal of this portfolio is to demonstrate practical defensive security skills using real-world SOC workflows and controlled lab environments.

## About Me

Aspiring SOC Analyst focused on threat detection, log analysis, and incident response.

I am building hands-on defensive security skills through practical labs, detection projects, and security tool usage in controlled environments such as TryHackMe.

---

## Featured Projects

### Phishing Email Analysis

Performed analysis of a suspicious phishing email, extracted indicators of compromise, inspected URLs, and documented recommended defensive actions.

**Skills:** Email analysis, URL inspection, IOC extraction, phishing investigation  
**Mapped MITRE Technique:** T1566 - Phishing  
**Status:** Completed

---

### Brute Force Detection

Created a basic detection workflow for failed login attempts and suspicious authentication behavior.

**Skills:** Log analysis, failed login detection, alert logic, SIEM fundamentals  
**Mapped MITRE Technique:** T1110 - Brute Force  
**Status:** Completed

---

### Windows Exploitation Awareness - Blue

Analyzed MS17-010/EternalBlue activity in a controlled TryHackMe lab environment and documented defensive lessons learned.

**Skills:** Windows security, vulnerability awareness, incident investigation  
**Mapped MITRE Technique:** T1210 - Exploitation of Remote Services  
**Status:** Completed

---

## Skills

- Log Analysis  
- Threat Detection  
- Incident Response  
- Network Traffic Analysis  
- SIEM Fundamentals  

---

## Repository Structure

```text
soc-analyst-portfolio/
├── labs/
│   ├── tryhackme/
│   │   ├── soc-level-1.md
│   │   └── blue.md
│   ├── brute-force-detection/
│   └── phishing-analysis.md
├── README.md
└── screenshots/
```

---

## Labs & Writeups

| Category | Lab / Project | Skills Demonstrated | Status |
|---|---|---|---|
| TryHackMe | [SOC Level 1](./labs/tryhackme/soc-level-1.md) | SOC fundamentals, alert triage, investigation workflow | Completed |
| TryHackMe | [Blue](./labs/tryhackme/blue.md) | Windows exploitation awareness, MS17-010 analysis, incident investigation | Completed |
| Detection Project | [Brute Force Detection](./labs/brute-force-detection) | Log analysis, failed login detection, basic alert logic | Completed |
| Detection Project | [Phishing Analysis](./labs/phishing-analysis.md) | Email analysis, URL inspection, IOC extraction | Completed |

---

## SOC Investigation Methodology

For each investigation or detection project, I follow a structured SOC workflow:

1. Identify the alert or suspicious activity
2. Collect relevant logs, artifacts, and indicators
3. Analyze suspicious behavior and possible impact
4. Extract indicators of compromise where applicable
5. Map findings to MITRE ATT&CK when possible
6. Document findings, lessons learned, and defensive recommendations

---

## Detection Logic Examples

### Brute Force Detection Logic

Possible indicators:

- Multiple failed login attempts from the same source IP
- Failed logins against multiple user accounts
- High number of authentication failures in a short time window
- Successful login shortly after repeated failures

Example Splunk-style query:

```spl
index=windows EventCode=4625
| stats count by src_ip, user
| where count > 5
```

Recommended response:

- Review source IP reputation
- Check affected user accounts
- Look for successful login events after failed attempts
- Escalate if activity appears suspicious

---

### Phishing Investigation Logic

Key checks:

- Sender domain reputation
- Reply-To mismatch
- Suspicious URLs or shortened links
- Attachment type and behavior
- Urgency or credential-harvesting language
- Extracted indicators of compromise such as sender, domain, URL, IP address, and file hash

Recommended response:

- Do not interact with suspicious links or attachments
- Extract and document IOCs
- Check whether similar emails were received by other users
- Block malicious domains or URLs where applicable
- Report and escalate according to incident response procedures

---

## Investigation Report Format

Each investigation follows this structure:

1. Alert or suspicious activity summary
2. Initial indicators
3. Log/source analysis
4. Timeline of activity
5. MITRE ATT&CK mapping
6. Impact assessment
7. Recommended remediation
8. Lessons learned

---

## MITRE ATT&CK Coverage

This portfolio includes basic mapping to MITRE ATT&CK techniques where applicable:

| Technique | ID | Related Lab / Project |
|---|---|---|
| Phishing | T1566 | Phishing Analysis |
| Brute Force | T1110 | Brute Force Detection |
| Exploitation of Remote Services | T1210 | Blue |
| Command and Scripting Interpreter | T1059 | Blue |
| Account Discovery | T1087 | SOC Level 1 / Windows Investigation |

---

## Windows Event IDs Covered

| Event ID | Description | Related Project |
|---|---|---|
| 4624 | Successful logon | Brute Force Detection |
| 4625 | Failed logon | Brute Force Detection |
| 4688 | Process creation | Windows Investigation |
| 4720 | User account created | Account Discovery / Windows Investigation |
| 7045 | Service installed | Windows Investigation |

---

## Tools

- Splunk  
- Wireshark  
- tcpdump  
- Linux  

---

## Focus Areas

- Brute Force Detection  
- Phishing Analysis  
- Suspicious Network Activity  
- Log Investigation  

---

## Currently Improving

- Splunk search queries and alert logic
- Windows Event Log analysis
- Sysmon-based detection
- Phishing email investigation workflow
- Basic incident response documentation
- MITRE ATT&CK mapping

---

## Planned Projects

| Project | Focus Area | Status |
|---|---|---|
| Malware Traffic Analysis | Wireshark, PCAP analysis, IOC extraction | Planned |
| Suspicious PowerShell Detection | Windows logs, command-line analysis | Planned |
| Sysmon Detection Lab | Sysmon, Windows telemetry, detection logic | Planned |
| Basic Incident Response Playbook | SOC workflow, escalation, containment | Planned |
| Sigma Rule Practice | Detection engineering fundamentals | Planned |

---

## Contact

- [LinkedIn](https://www.linkedin.com/in/marin-jozanovic/)

---

## Disclaimer

All labs, writeups, and detection projects in this repository were completed in legal and controlled environments such as TryHackMe, Hack The Box, or a personal home lab.

This repository is created for educational, defensive, and portfolio purposes only.

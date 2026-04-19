# TryHackMe: Blue Write-up

## Overview
The **Blue** room on TryHackMe is a Windows-focused lab centered on the identification and exploitation of **MS17-010 (EternalBlue)**, a critical SMB vulnerability affecting legacy Windows systems.  

From a SOC perspective, this lab is valuable because it demonstrates how a single unpatched service can lead to full system compromise and highlights the importance of vulnerability management, network visibility, and behavioral detection.

---

## Lab Objectives
This lab focused on the following goals:

- Identify exposed services on the target system
- Confirm whether the host is vulnerable to **MS17-010**
- Validate the impact of the vulnerability in a controlled lab environment
- Observe attacker behavior after initial compromise
- Review defensive considerations, detection opportunities, and mitigations

---

## Environment Summary
- **Platform:** TryHackMe  
- **Room:** Blue  
- **Difficulty:** Easy  
- **Operating System:** Windows  
- **Primary Service of Interest:** SMB  
- **Key Vulnerability:** MS17-010 / EternalBlue  

---

## Methodology

### 1. Service Enumeration
The first step was to identify accessible network services on the target. Enumeration revealed several Windows-related services, with **SMB on port 445** standing out as the primary attack surface.

Observed services included:
- `135/tcp` — MSRPC
- `139/tcp` — NetBIOS-SSN
- `445/tcp` — SMB

The exposure of SMB on a legacy Windows host immediately suggested the need to assess the system for known SMB-related vulnerabilities.

### 2. Vulnerability Validation
Further analysis confirmed that the target was vulnerable to **MS17-010**, a widely known remote code execution flaw in **SMBv1**.  

This vulnerability is especially significant because it has been associated with major real-world incidents, including wormable ransomware outbreaks. In a production environment, confirmation of this weakness would represent a high-priority remediation issue.

### 3. Controlled Exploitation
In the lab environment, the vulnerability was successfully validated using public tooling. This resulted in remote access to the host and demonstrated the real impact of the flaw: an attacker could move from network-level access to **full system compromise**.

### 4. Post-Compromise Validation
After initial access, the compromised system was reviewed to confirm privilege level and assess potential impact. The attack path ultimately resulted in **SYSTEM-level access**, showing that exploitation of this service can lead directly to complete administrative control of the endpoint.

This stage also reinforced the risk of follow-on actions such as:
- credential access
- persistence
- lateral movement
- host-based reconnaissance

---

## Key Findings

### Critical Exposure of SMB
The presence of SMB on a vulnerable Windows host created an immediate high-risk condition. Legacy SMB services remain a frequent target because they are both common and historically associated with severe remote exploitation flaws.

### Unpatched Systems Create Direct Risk
The lab demonstrated how an unpatched Windows system can be compromised using a well-known public exploit. This reinforces the importance of patch management and removal of deprecated protocols such as SMBv1.

### Privilege Escalation Was Not a Major Barrier
Because the vulnerability led directly to high-privilege access, the attacker did not need a complex privilege escalation chain. This significantly increases the severity of the issue from a defender’s perspective.

### Full Compromise Extends Beyond Initial Access
Once administrative-level access is achieved, the attacker may attempt credential dumping, discovery, persistence, and movement to other systems. For SOC teams, this means alerts should not stop at exploitation attempts alone; downstream activity must also be investigated.

---

## Detection Opportunities

From a SOC monitoring standpoint, this attack presents multiple opportunities for detection.

### Network-Level Indicators
Security teams should pay attention to:
- unusual inbound SMB traffic on port `445`
- scanning activity targeting SMB services
- repeated connection attempts against internal or externally exposed Windows hosts
- abnormal SMBv1 usage in environments where it should be disabled

### Host-Level Indicators
Potential host-based signals may include:
- suspicious processes spawned after SMB exploitation
- privilege escalation to `NT AUTHORITY\SYSTEM`
- unexpected remote shell behavior
- attempts to access sensitive registry hives or SAM data
- credential dumping-related activity
- rapid service instability or abnormal crashes associated with exploit attempts

### Investigative Context
In a real incident, analysts should correlate:
- endpoint alerts
- Windows event logs
- network telemetry
- EDR process trees
- authentication patterns
- lateral movement attempts following initial compromise

---

## Indicators of Compromise (IOCs)

Examples of suspicious behaviors relevant to this lab include:

- unexpected SMB connections to a vulnerable host
- exploit activity targeting **MS17-010**
- SYSTEM-level shell creation shortly after SMB interaction
- suspicious memory-resident tooling
- credential access behavior following initial execution
- unusual access to administrative shares or sensitive Windows directories

These are behavioral indicators rather than static indicators, which is often more useful in modern detection engineering.

---

## Defensive Recommendations

### 1. Disable SMBv1
If SMBv1 is still enabled, it should be removed or disabled immediately unless there is a documented and unavoidable legacy dependency.

### 2. Apply Security Updates
Patch all systems vulnerable to **MS17-010** and verify remediation through asset and vulnerability management processes.

### 3. Restrict SMB Exposure
SMB should not be unnecessarily exposed across network boundaries. Limit access through:
- internal segmentation
- firewall policy
- administrative access controls

### 4. Improve Detection Coverage
Ensure visibility exists for:
- SMB traffic patterns
- process creation
- privilege escalation events
- credential dumping behavior
- suspicious remote execution chains

### 5. Strengthen Endpoint Monitoring
Deploy and tune EDR or SIEM detections to identify:
- exploit-related SMB activity
- shell spawning from unusual parent processes
- abnormal high-privilege actions on user workstations or servers

---

## Lessons Learned
This lab reinforced several important defensive concepts:

- exposed legacy services can create severe compromise paths
- vulnerability management is a core part of SOC effectiveness
- detection should cover both exploitation attempts and post-compromise behavior
- administrative-level access drastically increases attacker capability
- network and endpoint telemetry must be correlated for accurate incident triage

---

## Conclusion
The **Blue** room is a strong introductory lab for understanding the security impact of legacy Windows vulnerabilities. While the technical exploitation path is straightforward, the real value from a SOC perspective lies in recognizing how this type of weakness would appear in monitoring data and how quickly it could escalate into a major incident.

This exercise strengthened my understanding of:
- Windows service enumeration
- SMB-related risk analysis
- vulnerability impact assessment
- post-compromise detection opportunities
- defensive mitigation planning

---

## Disclaimer
This write-up is intended strictly for **educational use in authorized lab environments such as TryHackMe**. It is provided from a defensive learning perspective and should not be used against systems without explicit permission.

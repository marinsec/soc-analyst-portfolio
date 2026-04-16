# TryHackMe – SOC Level 1 Writeup

## Overview
- Platform: TryHackMe  
- Room: SOC Level 1  
- Difficulty: Easy  
- Category: Security Operations / Blue Team  
- Focus: Log analysis, threat detection, incident investigation  

---

## Objective
Understand the fundamentals of Security Operations Center (SOC) workflows, including monitoring, detecting, and analyzing security events using logs and basic SIEM concepts.

---

## Scenario

The lab simulates a SOC environment where analysts are responsible for monitoring systems, reviewing alerts, and identifying potential security incidents.

The goal is to analyze logs, identify suspicious activity, and understand how security events are handled in a SOC environment.

---

## Key Concepts Covered

- Security monitoring  
- Log analysis  
- Threat detection  
- Incident response basics  
- SIEM fundamentals  

---

## Log Analysis

Reviewed system and authentication logs to identify unusual or suspicious patterns such as:

- Multiple failed login attempts  
- Unusual login times  
- Suspicious IP addresses  

Example:

```bash
Failed password for invalid user admin from 192.168.1.10 port 22 ssh2
```

This log entry indicates potential brute force activity.

---

## Investigation Process

1. Identify suspicious activity  
   - Look for repeated failed login attempts  
   - Detect anomalies in user behavior  

2. Analyze source of activity  
   - Extract IP addresses from logs  
   - Identify patterns or repeated attempts  

3. Determine impact  
   - Check if any login attempts were successful  
   - Identify compromised accounts or systems  

4. Escalate if necessary  
   - Report findings  
   - Recommend mitigation steps  

---

## Findings

- Detected repeated failed login attempts  
- Identified suspicious IP address performing multiple login attempts  
- Activity consistent with brute force attack behavior  

---

## Indicators of Compromise (IoC)

- Repeated failed login attempts  
- Suspicious IP address  
- Multiple targeted usernames  

---

## Mitigation & Response

- Block malicious IP addresses  
- Implement account lockout policies  
- Enable multi-factor authentication (MFA)  
- Monitor logs continuously  
- Use SIEM tools for real-time alerting  

---

## Lessons Learned

- Log analysis is essential for detecting attacks  
- Early detection helps prevent system compromise  
- Understanding normal vs abnormal behavior is key in SOC operations  
- SIEM tools improve detection and response efficiency  

---

## Summary

This lab provides a foundational understanding of SOC operations, focusing on monitoring, detecting, and analyzing security events.

By analyzing logs and identifying suspicious patterns, it is possible to detect potential attacks and respond effectively in a real-world SOC environment.

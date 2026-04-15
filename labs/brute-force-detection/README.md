# Brute Force Attack Detection

## Overview
- Type: Security Monitoring / Incident Detection  
- Scenario: SSH brute force attack  
- Focus: Log analysis, attack detection, incident response  

---

## Objective
Detect and analyze a brute force attack using system logs and identify malicious activity.

---

## Scenario

A server is suspected of being targeted by repeated login attempts.  
The goal is to analyze logs and determine whether a brute force attack occurred.

---

## Log Analysis

Example of suspicious log entries:

```
Failed password for invalid user admin from 192.168.1.10 port 22 ssh2
Failed password for invalid user root from 192.168.1.10 port 22 ssh2
Failed password for invalid user test from 192.168.1.10 port 22 ssh2
```

---

## Investigation Steps
1. Identify Failed Login Attempts
```bash
grep "Failed password" auth.log
```
Detected multiple failed login attempts.

2. Identify Attacker IP
```
grep "Failed password" auth.log | awk '{print $11}' | sort | uniq -c | sort -nr
```
Result shows repeated attempts from a single IP:
```
192.168.1.10
```

3. Check Successful Logins
```
grep "Accepted password" auth.log
```
Verify if attacker gained access.

---

## Findings
- Multiple failed login attempts detected
- Same IP address performing repeated attempts
- Pattern consistent with brute force attack

---

## Indicators of Compromise (IoC)
- Attacker IP: 192.168.1.10
- High number of failed login attempts
- Targeted usernames: admin, root, test

---

## Mitigation & Response
- Block malicious IP using firewall
- Enable account lockout policies
- Implement fail2ban
- Use SSH key authentication instead of passwords
- Monitor logs continuously

---

## Lessons Learned
- Log analysis is critical for detecting attacks
- Repeated failed logins are a key indicator of brute force attacks
- Early detection prevents unauthorized access

---

## Summary

This project demonstrates how to detect a brute force attack using log analysis.
By identifying repeated failed login attempts from a single IP address, we can quickly detect and respond to malicious activity.

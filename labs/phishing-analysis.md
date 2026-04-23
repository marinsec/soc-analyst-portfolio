# Phishing Analysis

## Overview
This project focuses on phishing analysis from a SOC analyst perspective. The goal was to review common phishing indicators, assess message risk, and document how suspicious emails can be triaged, investigated, and escalated in a defensive security workflow.

Phishing remains one of the most common initial access vectors, which makes email analysis, link inspection, and sender validation important skills for SOC operations.

---

## Objective
The objective of this project was to practice a structured phishing triage process by identifying suspicious characteristics in email content, sender identity, links, and attachments.

Key goals:
- identify phishing indicators
- assess sender and domain anomalies
- review suspicious links and attachments
- document detection opportunities
- outline response actions from a SOC perspective

---

## Analysis Areas

### Sender Validation
A key part of phishing triage is verifying whether the sender matches the organization they claim to represent.

Suspicious indicators may include:
- spoofed display names
- mismatched sender and reply-to addresses
- lookalike or misspelled domains
- impersonation of trusted services such as banks, couriers, or internal IT support

### Link Analysis
Phishing emails often rely on deceptive links to steal credentials or deliver malware.

Common red flags:
- mismatched hyperlink destination
- shortened URLs
- typosquatting domains
- fake login pages
- excessive subdomains hiding the real destination

### Attachment Risk
Unexpected attachments increase risk, especially when combined with urgency or impersonation.

Examples of suspicious attachments:
- macro-enabled documents
- archives
- executable files disguised as documents
- invoice or account-themed attachments

### Social Engineering Indicators
Phishing attempts frequently use urgency, fear, or trust to pressure the recipient.

Examples:
- account suspension warnings
- fake payment issues
- delivery failures
- requests for password reset or MFA approval
- urgent action language

---

## Key Findings
This project reinforced that phishing analysis depends on both technical review and context.

Main observations:
- sender validation is one of the fastest ways to identify suspicious emails
- link mismatch is a strong phishing indicator
- urgency and impersonation significantly increase risk
- suspicious attachments should always be reviewed in context
- phishing triage often requires follow-up investigation beyond the email itself

---

## Detection Opportunities
From a SOC perspective, phishing-related detections can focus on:

- sender domain anomalies
- reply-to mismatch
- impersonation of trusted brands or internal staff
- newly observed external domains
- suspicious login-themed messages
- high-risk attachment types
- suspicious links delivered through email

Useful telemetry sources include:
- email security gateway logs
- email headers
- Microsoft 365 or mail platform telemetry
- DNS and proxy logs
- endpoint telemetry
- user-reported phishing submissions

---

## Analyst Triage Workflow
A practical phishing triage workflow may include:

1. review the sender identity
2. inspect subject line and message context
3. compare visible links with actual destinations
4. assess attachments and file types
5. review SPF, DKIM, and DMARC results if available
6. determine whether the email was delivered, clicked, or reported
7. assess user exposure and business impact
8. escalate or contain as needed

---

## Response Actions
If an email is confirmed or strongly suspected to be phishing, recommended actions include:

- remove or quarantine the email
- block malicious sender domains and URLs
- review whether other users received the same message
- reset credentials if compromise is suspected
- review MFA activity and suspicious sign-ins
- investigate endpoint activity if a link was clicked or attachment opened
- notify affected users
- update detections based on findings

---

## Mitigation Recommendations
Recommended defensive measures include:

- enforce SPF, DKIM, and DMARC
- improve email filtering and attachment scanning
- monitor suspicious domains and links
- provide phishing awareness training
- tune detections for impersonation and malicious delivery patterns
- correlate email alerts with identity, endpoint, and network telemetry

---

## Lessons Learned
This project strengthened my understanding of:

- phishing triage methodology
- sender and domain validation
- suspicious link assessment
- attachment-related risk analysis
- defensive response planning in a SOC workflow

---

## Conclusion
Phishing analysis is a core SOC skill because phishing emails are frequently used for credential theft, malware delivery, and initial access. This project helped me practice a structured approach to identifying suspicious email characteristics and thinking through the next investigative and defensive steps as an analyst.

---

## Disclaimer
This project is intended for educational and defensive purposes only.

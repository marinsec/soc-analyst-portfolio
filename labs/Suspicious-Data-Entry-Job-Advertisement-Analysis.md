# Case Study: Suspicious Data Entry Job Advertisement Analysis

## Overview

This case study documents the analysis of a suspicious Facebook job advertisement for a data entry position.

The advertisement appeared in a local Facebook group and offered a data entry / administrative role with no previous experience required. The public post contained limited information about the employer, job responsibilities, salary, contract type, and hiring process.

After direct contact with the advertiser, additional red flags were observed, including avoidance of basic employer verification questions and a request for personal information before providing legitimate job details.

Based on the available indicators, the case was assessed as a likely job-related social engineering attempt and possible personal data harvesting scheme.

---

## Case Summary

| Field | Details |
|---|---|
| Case Type | Social Engineering / Job Advertisement Analysis |
| Platform | Facebook |
| Initial Vector | Public job advertisement in a local Facebook group |
| Claimed Role | Data Entry Clerk |
| Primary Concern | Personal data harvesting |
| Assessment | Suspicious / Likely fraudulent |
| Status | Completed |
| Outcome | Interaction stopped, profile blocked, no personal data shared |

---

## Initial Advertisement

The suspicious job advertisement was posted in a local Facebook group. The post was written in Croatian and claimed that the advertiser was looking for a data entry clerk for part-time or full-time work.

The poster's name and profile image were blurred to protect personal identity and keep the focus on the suspicious indicators rather than the individual account.

![Suspicious Facebook Data Entry Job Post](../screenshots/fake-data-entry-job-post.png)

---

## English Translation of the Advertisement

> Hello everyone,
>
> I am looking for a data entry clerk, either part-time or full-time, who will help me update records and perform basic administrative tasks.
>
> Previous experience is not required, but basic computer skills are important.
>
> If you are interested or would like more details, feel free to send me a direct message. Thank you!

---

## Initial Advertisement Indicators

The public advertisement alone was not enough to confirm fraud. However, it contained several weak trust signals that justified further verification:

- No company or business name was provided.
- No OIB / business registration number was listed.
- No salary or hourly rate was mentioned.
- No contract type was explained.
- No official company email, website, or contact channel was provided.
- The job description was vague and generic.
- Interested users were directed to private messages instead of an official hiring process.
- The phrase “no previous experience required” was used together with a low-detail job description.

These indicators made the post suspicious enough to continue with basic validation questions.

---

## Verification Questions Asked

To assess whether the job offer was legitimate, the following questions were asked:

- What is the name of the company or business?
- What is the company OIB / registration number?
- What exactly does the job involve?
- What is the salary or hourly rate?
- What type of contract is offered?
- What are the working hours?
- Is the job remote or on-site?
- Why are personal details required before receiving basic employer information?

These questions are standard validation steps when reviewing an unclear job offer, especially when the communication happens through a social media platform.

---

## Observed Behavior During Contact

After the verification questions were asked, the advertiser did not provide clear answers to the most important questions.

The most suspicious behavior included:

- Avoiding the question about the company or business name.
- Avoiding the question about the OIB / registration number.
- Not providing a clear job description.
- Not providing salary information.
- Not explaining the contract type.
- Becoming defensive when basic verification questions were asked.
- Requesting personal information before proving that a real employer or hiring process existed.
- Claiming that personal details were needed so that an “HR department” could contact the applicant.

This behavior significantly increased the likelihood that the advertisement was not part of a legitimate hiring process.

---

## Red Flags Identified

| Red Flag | Why It Matters |
|---|---|
| No company name | A legitimate employer should clearly identify itself before requesting applicant data. |
| No OIB or business registration details | The business could not be verified through official information. |
| Vague job description | Scam posts often use generic job titles to attract a wide range of victims. |
| No salary information | Legitimate job offers usually provide at least basic compensation details. |
| No contract information | The legal employment arrangement was unclear. |
| Early request for personal data | Personal data should not be requested before employer verification. |
| Defensive response to questions | Scammers often pressure or challenge users when questioned. |
| “HR department” mentioned without proof | This can be used to create false legitimacy. |
| Private-message-only process | Moving the conversation away from public visibility reduces transparency. |

---

## Analysis

The advertisement and follow-up interaction matched several patterns commonly seen in job-related scams and social engineering attempts.

A legitimate employer should be able to provide basic information before requesting any personal data. This includes the company name, business registration number, job responsibilities, salary or hourly rate, contract type, working hours, and official contact information.

In this case, the advertiser avoided the most important verification questions and requested personal details before proving that a real company or hiring process existed.

The most likely risk was personal data collection. Even basic information such as full name, phone number, email address, address, or date of birth can be used for further phishing, spam, identity fraud attempts, or follow-up scams.

Based on the available indicators, the case was assessed as a likely personal data harvesting attempt disguised as a simple data entry job offer.

---

## Assessment Confidence

**Confidence: Medium to High**

The public advertisement alone was not sufficient to confirm fraud. However, the follow-up interaction increased confidence due to the advertiser avoiding basic verification questions and requesting personal information before providing employer details.

The strongest indicators were:

- lack of employer transparency
- avoidance of company identification
- avoidance of OIB / registration details
- request for personal data before verification
- defensive behavior when questioned
- vague explanation of the hiring process

---

## Potential Risk to Victims

If a victim provided personal information, the information could potentially be used for:

- identity theft attempts
- further phishing messages
- spam and scam targeting
- fake job onboarding scams
- financial fraud attempts
- social engineering against the victim or their contacts
- requests for additional sensitive documents later in the process

The risk would be significantly higher if a victim shared:

- ID card photos
- bank account details
- payment card information
- login credentials
- one-time passwords
- tax or employment documents

---

## Actions Taken

The following actions were taken after suspicious behavior was confirmed:

1. The conversation was stopped.
2. No personal data, documents, banking details, or credentials were shared.
3. The profile was blocked.
4. The advertisement was treated as a likely scam attempt.
5. The advertisement was reported to Facebook for suspected scam activity.
6. The advertisement was later removed by Facebook.
7. The case was documented as an awareness and social engineering analysis exercise.

---

## Outcome

After the suspicious job advertisement was reported to Facebook for suspected scam activity, the advertisement was later removed by the platform.

This outcome further supported the decision to treat the advertisement as unsafe and document the case as a social engineering awareness example.

---

## Evidence Handling

The original conversation was not retained. This case study is based on observed behavior during the interaction.

Only the original job advertisement screenshot is included. Identifying details related to the individual poster were removed.

The purpose of this case study is not to identify or accuse a specific person, but to document suspicious job-advertisement patterns, social engineering indicators, and safe verification practices.

---

## Privacy and Ethics Note

This case study has been anonymized.

The poster’s name and profile image were blurred. The analysis focuses on the behavior, communication pattern, and risk indicators rather than personal identification.

No private personal data, profile links, private messages, phone numbers, or sensitive information are included.

---

## Lessons Learned

This case highlights the importance of verifying job offers before sharing personal information.

Key takeaways:

- Always verify the company name before continuing with a job offer.
- Ask for the business registration number or official company details.
- Do not share personal documents before confirming the employer.
- Be cautious of vague job offers that promise easy work with no experience.
- A legitimate employer should not avoid questions about salary, contract type, or job responsibilities.
- Defensive or aggressive behavior after basic questions is a strong warning sign.
- Job scams often use the same psychological pressure techniques as phishing campaigns.
- Private messages can be used to move victims away from public visibility and group moderation.

---

## SOC Analyst Relevance

Although this was not a traditional SIEM alert or malware investigation, the analysis followed a similar process used in SOC environments:

- identifying suspicious activity
- collecting initial indicators
- asking validation questions
- analyzing behavior and inconsistencies
- assessing victim risk
- recognizing social engineering patterns
- stopping interaction before compromise
- documenting findings clearly

This case demonstrates practical awareness of phishing, social engineering, fraud indicators, user protection, and incident-style documentation.

---

## Conclusion

Based on the available indicators, the Facebook job advertisement was assessed as suspicious and likely fraudulent.

The strongest indicators were the lack of employer transparency, avoidance of verification questions, vague job details, and a request for personal information before providing basic employer information.

The safest response was to stop communication, avoid sharing any sensitive information, block the profile, report the advertisement to Facebook, and document the indicators for awareness and learning purposes.

After the report was submitted, the advertisement was later removed by Facebook.

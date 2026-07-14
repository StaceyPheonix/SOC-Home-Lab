# Greenholt Phish Investigation

## Overview

This repository documents the analysis of a suspected phishing email using standard Security Operations Center (SOC) investigation techniques. The investigation focuses on email header analysis, sender authentication validation (SPF, DKIM, and DMARC), indicator of compromise (IOC) extraction, attachment analysis, and threat intelligence research to determine whether the email represents a phishing attempt.

---

## Disclaimer

This investigation was completed using a simulated phishing sample provided in a controlled cybersecurity training environment. The scenario is based on a TryHackMe lab, while the analysis, documentation, screenshots, and reporting included in this repository reflect my own investigation process and demonstrate SOC analyst methodologies rather than a real-world incident.

---

## Scenario

A Greenholt PLC employee reported a suspicious email that appeared to originate from a known customer. The message contained an unexpected financial transfer request, a generic greeting, and an unsolicited attachment. Due to multiple phishing indicators, the email was escalated to the Security Operations Center (SOC) for investigation.

---

## Investigation Objectives

- Analyze email metadata and message headers
- Validate sender authenticity using SPF, DKIM, and DMARC
- Extract and document Indicators of Compromise (IOCs)
- Analyze the suspicious attachment
- Perform threat intelligence research
- Determine the likely attack type
- Document findings and recommended SOC response actions

---

## Investigation Methodology

The investigation followed a standard SOC phishing analysis workflow:

1. Initial email triage
2. Email header analysis
3. Sender authentication validation
4. IOC extraction
5. Threat intelligence research
6. Attachment analysis
7. Attack classification
8. Documentation of findings

---

## Tools and Technologies

- Email Header Analysis
- VirusTotal
- SPF Record Lookup
- DKIM Analysis
- DMARC Analysis
- SHA256 Hashing
- Threat Intelligence Research
- MITRE ATT&CK Framework

---

## Investigation Outcome

The investigation identified multiple indicators consistent with a phishing campaign, including:

- Suspicious financial transfer request
- Reply-To address inconsistency
- Suspicious compressed attachment disguised as a PDF
- IOC extraction and reputation analysis
- Attachment hash verification using VirusTotal

Based on the collected evidence, the email was assessed as a suspected phishing attempt involving social engineering and potential malicious attachment delivery.

---

## MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1566 | Phishing |
| T1204 | User Execution |

---

## Repository Contents

```
Greenholt-Phish-Analysis/
│
├── README.md
├── Investigation-Report.md
├── IOC-List.md
└── screenshots/
    ├── MIME-attachment-header.png
    ├── dkim-analysis.png
    ├── spf-analysis.png
    ├── dmarc-analysis.png
    └── virustotal-results.png
```

---

## Screenshots

The screenshots included in this repository document key stages of the investigation process:

- **MIME Attachment Header** – Examination of the email attachment metadata and filename.
- **SPF Analysis** – Validation of the sender's SPF record.
- **DKIM Analysis** – Verification of DKIM configuration.
- **DMARC Analysis** – Review of the sender domain's DMARC policy.
- **VirusTotal Results** – Reputation analysis of the attachment hash.

---

## Skills Demonstrated

- Phishing Email Analysis
- Email Header Analysis
- MIME Header Analysis
- SPF, DKIM, and DMARC Validation
- IOC Identification and Documentation
- Threat Intelligence Research
- Attachment Analysis
- SHA256 Hash Verification
- Security Documentation
- SOC Investigation Workflow
- MITRE ATT&CK Mapping

---

## Author

**Stacey Menley**

Bachelor of Applied Science – Information Technology (Cybersecurity)

CompTIA Security+ | Network+ | ISC² Certified in Cybersecurity (CC)

GitHub Portfolio: SOC Home Lab

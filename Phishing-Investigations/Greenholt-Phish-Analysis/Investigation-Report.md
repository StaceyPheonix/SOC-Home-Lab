# Phishing Investigation Report

## Initial Triage

A suspicious email was escalated to the SOC after a user reported:

- Unexpected financial transfer request
- Generic greeting
- Unusual communication pattern
- Unsolicited attachment


## Email Header Analysis

### Sender Information

Display Name:
Mr. James Jackson

Sender Address:
info@mutawamarine[.]com

Reply-To:
info.mutawamarine@mail[.]com


### Findings

The Reply-To address did not match the sender domain, which is a common phishing indicator.


## Authentication Analysis

### SPF

Result:
SPF record identified:

`v=spf1 include:spf.protection.outlook.com -all`

### DMARC

Result:

`v=DMARC1; p=quarantine; fo=1`

Analysis:
Authentication records were reviewed to determine whether sender identity could be trusted.


## Attachment Analysis

Filename:

SWT_#09674321_PDF_.CAB

SHA256:

[defanged hash here]

Analysis:

The attachment used a PDF-themed filename but was identified as a RAR archive, increasing suspicion.


## Threat Classification

Potential Attack Type:

- Phishing
- Business Email Compromise (BEC)
- Malicious attachment delivery


## MITRE ATT&CK Mapping

| Technique | Description |
|---|---|
| T1566 | Phishing |
| T1204 | User Execution |

# SOC Threat Detection Playbook
## Behavioral Investigation Approach from Alert to Understanding

**Author:** Stacey Menley  
**Focus:** SOC Analysis | Threat Detection | Defensive Security

---

## Overview

My approach to security investigations has been shaped by monitoring real network activity through PISCES, building the HELM Network Observability Platform, completing KC7 investigations, and developing practical SOC skills through BBR Academy's SOC Analyst Boot Camp.

The foundation of my investigation process is understanding behavior.

Every alert represents a piece of a larger story. The analyst’s role is connecting the evidence across users, devices, IP addresses, domains, authentication events, and network activity to determine what happened, identify risk, and support response.

The process I follow:

**Identify the behavior → Find the evidence → Validate the activity → Understand the impact → Improve detection**

---

## Starting With the Signal

When reviewing an alert, the first step is identifying what is being targeted and where that activity will appear.

| Target | Common Attack Activity | Evidence Sources |
|---|---|---|
| Email | Phishing, malicious links, attachments | Message source, headers, sender information, URLs |
| Login | Brute force, password spray, credential abuse | Authentication logs, MFA events, user activity |
| Network | Malware, command and control, suspicious communication | NetFlow, DNS, firewall logs, endpoint telemetry |
| Files/Data | Data access and exfiltration | File activity, cloud activity, outbound traffic |

The entity involved helps guide the investigation:

| Entity | Investigation Path |
|---|---|
| User | Account behavior, authentication history, access patterns |
| IP Address | Reputation, communication history, location, threat intelligence |
| Domain | Reputation, age, DNS activity, malicious infrastructure |
| Device | Processes, connections, endpoint activity |

---

## Investigation Thinking

The first questions I ask when analyzing activity:

| Question | Investigation Purpose |
|---|---|
| What happened? | Establish the event and timeline |
| How many? | Determine scope and affected systems |
| Which user, device, IP, or domain is involved? | Identify the entities connected to the activity |
| Does the behavior match normal activity? | Separate expected behavior from potential threats |

The investigation is about finding the pattern behind the event.

---

## Phishing Investigation

Phishing investigations start by understanding the initial access attempt and determining whether the activity continued beyond delivery.

Evidence reviewed:

- Message source
- Email headers
- Sender domain
- Return path
- URLs
- Attachments
- User interaction

Important indicators:

- Suspicious sender domains
- New or uncommon external senders
- External users impersonating internal identities
- Malicious links
- Suspicious attachments
- Bulk email delivery patterns

Investigation questions:

- Does the sender match who they claim to be?
- Does the infrastructure match the organization being represented?
- Has the domain or URL been associated with malicious activity?
- Did the user click the link or open the attachment?
- Did additional authentication or endpoint activity occur afterward?

Tools and data sources:

- Email security logs
- SIEM
- VirusTotal
- Sandbox analysis
- Threat intelligence

Phishing prevention relies on multiple layers:

- SPF/DKIM/DMARC
- Email filtering
- DNS filtering
- User awareness
- Endpoint protection

---

## Credential Abuse and Brute Force Investigation

Credential attacks often appear through authentication patterns.

Common indicators:

- Multiple failed logins from one IP address
- One account receiving repeated attempts
- One IP attempting access across many users
- Password spraying behavior
- Successful authentication following repeated failures

Investigation focuses on:

- Authentication logs
- Source IP addresses
- User activity
- MFA events
- Login history

Questions:

- Was access successful?
- Was MFA triggered?
- Is this normal behavior for the user?
- Are additional accounts affected?

Detection patterns often reveal whether activity is user error, compromised credentials, or an active attack.

Prevention:

- MFA
- Account lockout policies
- Conditional access
- Strong authentication controls

---

## Command and Control (C2) and Malware Beaconing Investigation

Building HELM strengthened my understanding of network visibility and the importance of context.

A device communicating with an external destination requires investigation before determining whether it is malicious.

The activity may represent:

- Malware command and control
- Legitimate cloud services
- CDN infrastructure
- Normal application behavior

Evidence reviewed:

- Source device
- Destination IP/domain
- DNS activity
- Connection frequency
- Traffic patterns
- Threat intelligence

Common indicators:

- Repeated communication with the same destination
- Regular communication intervals
- Small consistent traffic bursts
- Unknown external connections

Investigation questions:

- Who initiated the communication?
- Is the destination expected?
- What application or process created the connection?
- Is the infrastructure associated with known threats?
- Are additional devices communicating with the same destination?

Tools:

- NetFlow
- DNS logs
- Firewall logs
- Endpoint telemetry
- SIEM
- Threat intelligence

Prevention:

- DNS filtering
- Endpoint Detection and Response
- Network monitoring
- Threat intelligence feeds

---

## Lateral Movement Investigation

After initial access, attackers often attempt to expand control within an environment.

Common indicators:

- One compromised device accessing multiple systems
- Unexpected internal connections
- Remote service usage
- Privileged account activity

Evidence reviewed:

- Authentication events
- Internal network activity
- Endpoint logs
- Privilege changes

Investigation questions:

- Where did the initial compromise occur?
- Which account was used?
- What systems were accessed?
- Did privileges increase?
- How far did the attacker move?

Prevention:

- Least privilege
- Network segmentation
- Endpoint monitoring
- Administrative controls

---

## Data Exfiltration Investigation

Data theft often appears as activity outside normal user or system behavior.

Indicators:

- Large outbound transfers
- Unexpected cloud uploads
- Sensitive file access
- Unusual access patterns

Evidence reviewed:

- Network traffic
- File activity
- Cloud activity
- User behavior

Investigation questions:

- What data was accessed?
- Who accessed it?
- Where was the data sent?
- Was the activity authorized?

Prevention:

- Data Loss Prevention
- Access controls
- Outbound monitoring
- Cloud security controls

---

## DNS Tunneling Investigation

DNS activity can provide visibility into hidden attacker communication.

Indicators:

- Long randomized domains
- High-frequency DNS requests
- Random character patterns
- Suspicious subdomains


Investigation focuses on:

- DNS history
- Domain reputation
- Request frequency
- Source device

Questions:

- Is the domain legitimate?
- Does the request pattern match normal behavior?
- Is one device generating unusual DNS activity?

Prevention:

- DNS filtering
- Threat intelligence
- Blocking malicious domains
- Monitoring abnormal DNS behavior

DNS filtering provides an additional defensive layer by evaluating destinations against security intelligence before communication is established.

---

## KQL Investigation Approach

KQL became valuable during KC7 and SOC training because it translates investigative questions into searchable evidence.

The approach starts with the behavior and then identifies the data needed.

Examples:

| Investigation Question | KQL Concept |
|---|---|
| How many events occurred? | Count activity |
| Which users, devices, or domains are involved? | Identify unique entities |
| Show relevant activity | Project useful fields |
| What failed? | Filter failed results |
| What domains were visited? | Review URL and DNS activity |

Examples of detection patterns:

| Attack Behavior | Evidence Pattern |
|---|---|
| Phishing | Suspicious sender, URL, attachment activity |
| Brute Force | Repeated authentication failures |
| C2 Malware | Periodic external communication |
| Lateral Movement | Internal spread between systems |
| DNS Tunneling | Long, unusual DNS requests |

---

## Frameworks Supporting Analysis

MITRE ATT&CK, Cyber Kill Chain, Unified Kill Chain, and the Pyramid of Pain provide different perspectives for understanding adversary behavior.

The Cyber Kill Chain helps map attacker progression:

| Phase | Activity |
|---|---|
| Reconnaissance | Target discovery |
| Weaponization | Creating malicious capability |
| Delivery | Sending the attack |
| Exploitation | Gaining access |
| Installation | Establishing persistence |
| Command and Control | Maintaining communication |
| Actions on Objectives | Achieving attacker goals |

The Pyramid of Pain reinforces the importance of behavioral detection.

Attackers can quickly change:

- Hashes
- IP addresses
- Domains

More difficult areas to change:

- Tools
- Techniques
- Procedures

Understanding attacker behavior creates stronger detection opportunities.

---

## Final Perspective



Technology continues advancing at a pace where automation, AI, IoT, and connected systems are becoming part of everyday life. At the same time, the need for security professionals who can understand, investigate, and defend those environments continues growing.



Through PISCES, HELM, KC7, and BBR Academy's SOC Analyst Boot Camp, I have continued developing the ability to recognize patterns, investigate activity, and connect technical evidence to real-world impact.



One of the biggest lessons I have learned is that an alert is only the beginning of the investigation. The real value comes from understanding the behavior behind the activity, asking the right questions, finding the evidence, and helping organizations make informed security decisions.



We are building a more connected future, and protecting that future requires people who are willing to keep learning, adapt with technology, and understand the threats that come with innovation.



This is the mindset I bring into security operations.




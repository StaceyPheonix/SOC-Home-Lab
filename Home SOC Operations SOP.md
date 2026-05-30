# Home Security Operations Center (SOC) Standard Operating Procedure

**Owner:** Stacey Menley  
**Version:** 1.0  
**Last Updated:** May 2026  
**Classification:** Public Portfolio Version  

---

## 1. Purpose

This Standard Operating Procedure (SOP) defines the operational processes used to monitor, maintain, investigate, and improve my Home Security Operations Center (SOC) environment.

The lab leverages a combination of open-source and commercial security technologies to provide centralized logging, network visibility, security monitoring, alerting, and investigation capabilities. The environment is used to develop and apply practical cybersecurity skills through continuous monitoring, threat hunting, incident response, and security operations activities.

This SOP provides a repeatable workflow for maintaining visibility, responding to alerts, investigating suspicious activity, and documenting findings.

---

## 2. Scope

This SOP applies to all monitoring, investigation, and incident response activities performed within the Home SOC environment.

### Covered Activities
- Security monitoring  
- Log analysis  
- Alert triage  
- Threat hunting  
- Incident investigation  
- Network visibility monitoring  
- Platform maintenance  
- Documentation of findings  
- Continuous improvement activities  

---

## 3. Environment Overview

### Infrastructure
- Raspberry Pi 5 Security Monitoring Server  
- OpenWRT One Router  
- Arris Surfboard Cable Modem  
- Netgear 8-Port Managed Switch  
- Power over Ethernet (PoE) devices  
- Windows workstation  
- Linux ARM64 workstation  

### Security Tooling
- ELK Stack (Elasticsearch, Logstash, Kibana)  
- Syslog collection and analysis  
- NetFlow/IPFIX telemetry  
- Wireshark packet analysis  
- Splunk (learning environment)  
- MITRE ATT&CK mapping  
- Custom dashboards  
- Alerting and automation workflows  

### Monitored Assets
- Endpoints  
- Network infrastructure devices  
- IoT devices  
- Security cameras  
- Smart home devices  

---

## 4. Security Operations Workflow

Security operations follow a continuous cycle:

- Collect telemetry  
- Review alerts  
- Investigate activity  
- Validate findings  
- Document results  
- Improve detections  

Each cycle improves visibility, detection quality, and response readiness.

---

## 5. Daily Monitoring Procedure

### Step 1: Verify Monitoring Health

At the start of each session:

- Confirm monitoring services are operational  
- Verify dashboards are receiving data  
- Review ingestion status  
- Confirm asset visibility  
- Check for telemetry gaps or outages  

If visibility is degraded, restoration of monitoring takes priority.

---

### Step 2: Review Security Alerts

All new alerts are reviewed and categorized:

- **Informational:** Expected activity, no action required  
- **Investigative:** Requires further analysis  
- **Actionable:** Requires response or containment  

For each alert:
- Identify source and target  
- Determine affected asset  
- Review severity and timing  
- Assess potential impact  

---

### Step 3: Validate Asset Visibility

Ensure expected assets are present and monitored:

- Identify new devices  
- Identify missing devices  
- Detect abnormal behavior changes  
- Validate communications between systems  

Maintaining accurate asset visibility is a core security control.

---

## 6. Alert Investigation Procedure

When suspicious activity is identified:

### Step 1: Establish Context
- Source system  
- Destination system  
- Time of event  
- User or device activity  
- Related alert history  

---

### Step 2: Review Evidence

Available sources may include:

- Syslog data  
- Network telemetry  
- Dashboards  
- Packet captures (Wireshark)  
- Historical logs  
- Asset inventory data  

---

### Step 3: Analyze Activity

Look for:

- Authentication anomalies  
- Unusual network connections  
- Unexpected outbound traffic  
- Service disruptions  
- Behavioral deviations from baseline  

Where applicable, map activity to MITRE ATT&CK techniques.

---

### Step 4: Document Findings

Record:

- Timeline of events  
- Systems involved  
- Evidence reviewed  
- Final findings  
- Analyst actions  
- Recommendations  

---

## 7. Threat Hunting Procedure

Threat hunting is performed regularly, regardless of alerts.

### Endpoint Review
- Login activity  
- Process and service changes  
- System event anomalies  

### Network Review
- Unusual connections  
- Long-lived sessions  
- New or unknown destinations  
- Traffic spikes or deviations  

### Device Review
- IoT communication behavior  
- Camera activity  
- Infrastructure device anomalies  

Goal: Identify threats before automated alerts trigger.

---

## 8. Incident Response Procedure

When malicious or high-risk activity is identified:

### Step 1: Identification
- Scope of activity  
- Affected systems  
- Severity level  
- Potential impact  

---

### Step 2: Containment

Actions may include:
- Isolating affected systems  
- Blocking suspicious communications  
- Disabling services  
- Removing unauthorized devices  

---

### Step 3: Analysis
- Root cause  
- Timeline  
- Attack method  
- Additional affected assets  

---

### Step 4: Recovery
- Restore normal operations  
- Confirm monitoring visibility is restored  
- Validate system integrity  

---

### Step 5: Lessons Learned
- What occurred  
- How it was detected  
- What worked well  
- What needs improvement  

---

## 9. Monitoring Platform Recovery

If monitoring systems fail:

### Infrastructure Checks
- Power status  
- Network connectivity  
- Storage availability  
- Service health  

### Recovery Actions
- Restore log ingestion  
- Validate dashboards  
- Confirm alerting functionality  

### Validation
- Ensure new data is flowing  
- Confirm asset visibility  
- Verify system stability  

---

## 10. Documentation Requirements

All significant events are documented:

- Security alerts  
- Incident investigations  
- System outages  
- Configuration changes  
- Detection improvements  
- Lessons learned  

Documentation supports repeatability and operational maturity.

---

## 11. Continuous Improvement

This environment is continuously improved through:

- Detection tuning  
- Dashboard refinement  
- Alert quality improvements  
- Threat hunting expansion  
- Incident response updates  
- Logging and visibility enhancements  

Each investigation contributes to improving overall security posture.

---

## 12. Security Operations Principles

- Maintain visibility across all systems  
- Investigate anomalies before dismissing them  
- Validate conclusions with evidence  
- Document all findings  
- Continuously improve detection and response  
- Prioritize resilience and recoverability  
- Apply defense-in-depth thinking  

---

## 13. References

- NIST Cybersecurity Framework (CSF)  
- NIST SP 800-61 (Incident Response)  
- NIST SP 800-92 (Log Management)  
- CIS Critical Security Controls  
- MITRE ATT&CK Framework  

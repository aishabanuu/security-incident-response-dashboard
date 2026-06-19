# Incident Scenarios

## Overview

This document describes the security incidents simulated during the Security Incident Response Dashboard project. Each scenario demonstrates a different stage of the Security Operations Center (SOC) workflow, including monitoring, detection, investigation, incident response, and threat intelligence.

---

# Scenario 1: Authentication Failure Detection

## Objective

Demonstrate Wazuh's ability to detect unauthorized login attempts.

## Actions Performed

On the Kali Linux endpoint:

```bash
su root
```

Incorrect passwords were entered multiple times.

## Detection

Wazuh generated authentication-related alerts:

- Rule ID 5503 – PAM: User login failed
- Rule ID 5557 – Password check failed

## Investigation

The alerts were reviewed using the Wazuh Threat Hunting module.

Information analyzed:

- Timestamp
- Agent name
- Rule ID
- Severity level
- Event details

## Outcome

The SIEM successfully detected failed authentication attempts and generated alerts for analyst review.

---

# Scenario 2: File Integrity Monitoring (FIM)

## Objective

Demonstrate detection of unauthorized file modifications.

## Actions Performed

On the Kali Linux endpoint:

```bash
sudo touch /etc/project_test_file
echo "test" | sudo tee -a /etc/project_test_file
```

## Detection

Wazuh File Integrity Monitoring detected the modification.

Generated alert:

- Rule ID 550 – Integrity checksum changed

## Investigation

The event was reviewed in Threat Hunting.

Analysts verified:

- Modified file
- Timestamp
- Agent responsible
- Alert severity

## Outcome

Wazuh successfully detected file changes in monitored directories.

---

# Scenario 3: Privilege Escalation Monitoring

## Objective

Demonstrate monitoring of privileged operations.

## Actions Performed

The following command was executed:

```bash
sudo su
```

## Detection

Wazuh generated privileged activity alerts:

- Rule ID 5402 – Successful sudo to ROOT executed

## Investigation

Security analysts reviewed:

- User account
- Command execution
- Time of execution
- Severity level

## Outcome

Administrative actions were successfully monitored and logged.

---

# Scenario 4: Host-Based Intrusion Detection

## Objective

Demonstrate host integrity monitoring through Rootcheck.

## Actions Performed

Rootcheck scans were executed automatically by Wazuh.

## Detection

Generated alert:

- Rule ID 510 – Host-based anomaly detection event

## Investigation

The analyst reviewed:

- Rootcheck findings
- Affected host
- Security recommendations

## Outcome

The system successfully detected host-level security anomalies.

---

# Scenario 5: Incident Response

## Objective

Demonstrate automated response capabilities.

## Configuration

Active Response was configured in Wazuh:

```xml
<active-response>
  <disabled>no</disabled>
  <command>firewall-drop</command>
  <location>local</location>
  <rules_id>5710</rules_id>
  <timeout>600</timeout>
</active-response>
```

## Response Workflow
```bash
Attack Attempt
    ↓
Detection
    ↓
Alert Generation
    ↓
Active Response
    ↓
IP Blocking
```

## Outcome

The platform demonstrated the capability to automatically respond to security incidents.

---

# Scenario 6: Threat Intelligence Enrichment

## Objective

Demonstrate integration of external threat intelligence.

## Actions Performed

A threat intelligence lookup script was developed using VirusTotal/AbuseIPDB concepts.

Example workflow:
```bash
Alert Generated
      ↓
Extract Suspicious IP
      ↓
Threat Intelligence Lookup
      ↓
Reputation Analysis
      ↓
Investigation
```

## Information Retrieved

- IP Reputation
- Country Information
- Abuse Score
- Threat Classification

## Outcome

Threat intelligence enrichment provided additional context for security investigations.

---

# Conclusion

The project successfully demonstrated:

- Security Monitoring
- Threat Detection
- Alert Investigation
- File Integrity Monitoring
- Incident Response
- Threat Intelligence

using Ubuntu Server, Kali Linux, VMware Fusion, and the Wazuh SIEM platform.

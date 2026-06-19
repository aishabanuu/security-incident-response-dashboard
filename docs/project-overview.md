# Project Overview

## Introduction

This project demonstrates the implementation of a Security Incident Response Dashboard using Wazuh SIEM.

The environment consists of two virtual machines running in VMware Fusion:

- Ubuntu Server (Wazuh Manager, Indexer, Dashboard, and Filebeat)
- Kali Linux (Wazuh Agent)

The purpose of this project is to monitor security events, detect suspicious activities, investigate incidents, and provide centralized visibility across systems.


## Objectives

The primary objectives of this project are:

- Collect logs from monitored endpoints
- Detect suspicious activities
- Generate security alerts
- Investigate incidents
- Support threat hunting activities
- Map events to MITRE ATT&CK techniques


## Scope

This project focuses on:

- Endpoint monitoring
- Log collection
- Alert generation
- Threat detection
- Security investigations
- Incident response workflows


## Expected Outcome

The platform should successfully:

- Monitor endpoint activity
- Generate alerts
- Display security events in the dashboard
- Support threat hunting investigations
- Demonstrate incident response capabilities


## Environment

### Ubuntu Server

- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard
- Filebeat

### Kali Linux

- Wazuh Agent


## Project Workflow

1. Security events occur on Kali Linux.
2. Wazuh Agent collects the logs.
3. Logs are forwarded to the Wazuh Manager.
4. Wazuh Manager analyzes the events.
5. Filebeat sends alerts to OpenSearch.
6. Wazuh Dashboard displays the alerts.
7. Analysts investigate and respond to incidents.


## Technologies Used

- Wazuh SIEM
- Ubuntu Server
- Kali Linux
- OpenSearch
- Filebeat
- VMware Fusion


## Outcome

The project successfully demonstrated centralized security monitoring, threat detection, incident investigation, and response capabilities using Wazuh SIEM.

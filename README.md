# Security Incident Response Dashboard

## Overview

This project demonstrates the implementation of a Security Incident Response Dashboard using the Wazuh SIEM platform. The environment was built using VMware Fusion on an Apple MacBook Air M1 with Ubuntu Server and Kali Linux virtual machines.

The project covers the complete security operations workflow:

- Monitoring
- Detection
- Investigation
- Incident Response
- Threat Intelligence

## Architecture

Kali Linux acts as the monitored endpoint and attack simulation machine.

Ubuntu Server hosts:

- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard

Security events generated on Kali Linux are collected by the Wazuh Agent and forwarded to the Wazuh Manager for analysis.

## Technologies Used

- Ubuntu Server
- Kali Linux
- VMware Fusion
- Wazuh
- Elasticsearch/OpenSearch
- AbuseIPDB API
- VirusTotal API
- Python

## Features

### Monitoring

Real-time collection and visualization of security logs.

### Detection

Detection of:

- Failed SSH logins
- Brute-force attempts
- File integrity violations
- Suspicious system activity

### Investigation

Event analysis through:

- Log correlation
- Alert review
- Security event timelines

### Incident Response

Automated response actions including:

- IP blocking
- Alert generation
- Event escalation

### Threat Intelligence

Integration with external intelligence feeds:

- AbuseIPDB
- VirusTotal

## Virtual Machine Setup

### VM 1

Ubuntu Server

Role:

- Wazuh Manager
- Wazuh Dashboard
- Wazuh Indexer

### VM 2

Kali Linux

Role:

- Wazuh Agent
- Attack Simulation

## Demonstrations

- File Integrity Monitoring
- Brute Force Detection
- Automated Incident Response
- Threat Intelligence Enrichment
- Security Reporting

## Screenshots

Screenshots are available in the screenshots directory.

## Author

Aisha

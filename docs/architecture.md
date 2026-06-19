# Architecture

## Components

### Ubuntu Server

Hosts:

- Wazuh Manager
- Wazuh Dashboard
- Wazuh Indexer

### Kali Linux

Hosts:

- Wazuh Agent

Generates:

- Security logs
- Attack simulations
- File integrity events

## Data Flow
```bash
Kali Linux
↓
Wazuh Agent
↓
Wazuh Manager
↓
Indexer
↓
Dashboard
↓
Security Analyst Investigation
```

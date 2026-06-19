# System Architecture

## Architecture Overview

The project consists of two virtual machines connected over a local network.

### Ubuntu Server

Acts as the centralized monitoring server and hosts:

- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard
- Filebeat

### Kali Linux

Acts as the monitored endpoint and hosts:

- Wazuh Agent

---

## Architecture Diagram

```text
Kali Linux Agent
       |
       v
Wazuh Manager
       |
       v
Filebeat
       |
       v
Wazuh Indexer
       |
       v
Wazuh Dashboard
```

---

## Data Flow

1. Security activity occurs on Kali Linux.
2. Wazuh Agent collects logs.
3. Logs are sent to Wazuh Manager.
4. Wazuh Manager analyzes the events.
5. Alerts are indexed in OpenSearch.
6. Dashboard visualizes the alerts.

---

## Network Configuration

Ubuntu Server: 172.16.61.130

Kali Linux: 172.16.61.133

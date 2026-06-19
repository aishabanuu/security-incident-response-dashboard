# Setup Guide

## Ubuntu Server Setup

### Install Wazuh

```bash
curl -sO https://packages.wazuh.com/4.13/wazuh-install.sh
sudo bash wazuh-install.sh -a
```

### Verify Services

```bash
sudo systemctl status wazuh-manager
sudo systemctl status wazuh-indexer
sudo systemctl status wazuh-dashboard
sudo systemctl status filebeat
```
---

## Kali Linux Setup

### Add Wazuh Repository

```bash
curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | sudo gpg --dearmor -o /usr/share/keyrings/wazuh.gpg

echo "deb [signed-by=/usr/share/keyrings/wazuh.gpg] https://packages.wazuh.com/4.x/apt stable main" | sudo tee /etc/apt/sources.list.d/wazuh.list

sudo apt update
```

### Install Agent

```bash
sudo apt install wazuh-agent=4.13.1-1
```

### Configure Manager IP

Edit:

```text
/var/ossec/etc/ossec.conf
```

Replace:

```xml
<address>MANAGER_IP</address>
```

With:

```xml
<address>172.16.61.130</address>
```

### Register Agent

```bash
sudo /var/ossec/bin/agent-auth -m 172.16.61.130
```

### Start Agent

```bash
sudo systemctl enable wazuh-agent
sudo systemctl start wazuh-agent
```

### Verify Agent Status

```bash
sudo systemctl status wazuh-agent
```

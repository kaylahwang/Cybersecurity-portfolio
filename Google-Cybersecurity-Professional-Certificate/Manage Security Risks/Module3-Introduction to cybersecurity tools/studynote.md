# SIEM Study Notes

## 1. What is SIEM?

SIEM (Security Information and Event Management)
is a platform that collects, analyzes, and correlates log data
to monitor security events.

Main functions:
- Log collection
- Event correlation
- Threat detection
- Security monitoring


## 2. Log Sources

### Server Logs
Records:
- Website activity
- Email activity
- File sharing
- Login requests


### Firewall Logs
Records:
- Incoming connections
- Outgoing internet requests


### Network Logs
Records:
- Devices entering/leaving networks


## 3. SIEM Types

### Self-hosted
Organization manages infrastructure.

Example:
Splunk Enterprise


### Cloud-hosted
Vendor manages infrastructure.

Example:
Splunk Cloud


### Cloud-native
Built specifically for cloud environments.

Example:
Google Chronicle


### Hybrid
Combination of self-hosted + cloud.


## 4. SIEM Dashboards

### Splunk

Security Posture Dashboard:
- Monitor security events
- Detect suspicious activity


Incident Review Dashboard:
- Investigate incident timeline


Risk Analysis Dashboard:
- Analyze risky users, devices, IPs


### Chronicle

Enterprise Insights:
- Alerts and IOC detection


IOC Matches:
- Track suspicious domains/IPs


User Sign-in Overview:
- Detect abnormal login behavior


## 5. SIEM Future Trends

- Cloud migration
- AI/ML integration
- Automation
- SOAR
- IoT security monitoring
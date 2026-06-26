# Module 4 – Security Analyst Tools

## Overview

Security analysts use a variety of tools and operational procedures to monitor systems, detect threats, investigate incidents, and protect organizational assets.

Understanding how these tools work is essential for responding to cybersecurity incidents efficiently and preserving digital evidence during investigations.

---

# Security Information and Event Management (SIEM)

## What is SIEM?

A Security Information and Event Management (SIEM) system collects, aggregates, and analyzes log data from multiple devices and applications across an organization.

Rather than manually reviewing thousands of logs, analysts can use SIEM platforms to identify suspicious activities and receive automated alerts.

### Primary Functions

* Collect log data from multiple sources
* Correlate security events
* Detect threats and suspicious activities
* Generate real-time alerts
* Support incident investigations

### Common Features

* Centralized log management
* Dashboards and visualizations
* Search and filtering
* Alerting
* Reporting

### Hosting Options

**On-Premises**

* Greater control
* Requires more maintenance
* Managed internally

**Cloud-Based**

* Easier deployment
* Lower maintenance
* Scalable infrastructure

---

# Network Protocol Analyzer (Packet Sniffer)

## What is a Packet Sniffer?

A network protocol analyzer captures and analyzes network traffic traveling across a network.

It enables security analysts to examine packets, troubleshoot network problems, and investigate suspicious communications.

### Common Uses

* Network troubleshooting
* Traffic analysis
* Detecting malicious activity
* Incident investigations
* Protocol analysis

### Example Tool

* Wireshark

---

# Security Playbooks

## What is a Playbook?

A playbook is a documented set of procedures that guides security analysts through specific operational or incident response tasks.

Playbooks help ensure that security incidents are handled consistently, efficiently, and according to organizational policies.

### Benefits

* Standardized response procedures
* Faster incident handling
* Reduced human error
* Improved collaboration
* Compliance with organizational policies

---

# Chain of Custody

## Definition

Chain of custody is the documented process of tracking the possession, handling, and transfer of digital evidence throughout an investigation.

Maintaining a complete chain of custody helps ensure that evidence remains trustworthy and legally admissible.

### Documentation Typically Includes

* Who collected the evidence
* When it was collected
* Where it was stored
* Why it was accessed
* Every transfer of possession

---

# Protecting and Preserving Evidence

Digital evidence can be fragile and easily altered if handled improperly.

Security analysts should preserve evidence before beginning an investigation.

### Best Practices

* Create forensic copies before analysis
* Avoid modifying original evidence
* Maintain proper documentation
* Follow organizational procedures

---

# Order of Volatility

## Definition

The Order of Volatility is the recommended sequence for collecting digital evidence, beginning with data that is most likely to disappear first.

Volatile data should always be preserved before shutting down or rebooting a system.

### Examples of Volatile Data

* RAM (Memory)
* Running processes
* Network connections
* System cache

Less volatile data includes:

* Hard drives
* Backup media
* Archived logs

---

# Key Takeaways

* SIEM platforms centralize log collection and automate threat detection.
* Packet sniffers capture and analyze network traffic for troubleshooting and investigations.
* Playbooks provide standardized procedures for responding to security incidents.
* Chain of custody protects the integrity and admissibility of digital evidence.
* Digital evidence should always be preserved before analysis.
* Following the Order of Volatility helps prevent the loss of critical forensic evidence.

---

# Personal Reflection

This module introduced the operational tools and procedures commonly used by security analysts. I learned that cybersecurity involves more than identifying threats—it also requires structured investigation processes, proper evidence handling, and consistent incident response. Concepts such as SIEM, playbooks, chain of custody, and the Order of Volatility highlighted the importance of disciplined procedures in digital forensics and security operations.

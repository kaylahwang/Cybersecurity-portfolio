# Module 4 - Security Hardening

## Overview

This module focused on strengthening authentication systems, operating systems, and network infrastructure through security hardening techniques. The module covered brute force attack prevention, secure testing environments, defense-in-depth architecture, network monitoring, and security risk assessment.

---

# Authentication Security

## Brute Force Attacks

A brute force attack is a trial-and-error method used to gain unauthorized access by repeatedly guessing usernames and passwords.

### Types of Brute Force Attacks

#### Simple Brute Force Attack

Attempts random combinations of usernames and passwords until successful.

#### Dictionary Attack

Uses predefined wordlists containing:

- Common passwords
- Previously leaked credentials
- Frequently reused passwords

### Risks

- Account compromise
- Unauthorized access
- Privilege escalation
- Data breaches

---

## Authentication Hardening

### Hashing

Hashing converts a password into a fixed, irreversible value.

Benefits:

- Protects password storage
- Prevents plaintext exposure

### Salting

Random data is added before hashing.

Benefits:

- Defends against rainbow table attacks
- Produces unique hashes

### Multi-Factor Authentication (MFA)

Requires users to verify their identity using multiple factors.

Examples:

- Password + OTP
- Password + Fingerprint

Benefits:

- Reduces account takeover risks
- Mitigates brute force attacks

### CAPTCHA and reCAPTCHA

Used to distinguish human users from bots.

Benefits:

- Prevents automated attacks
- Reduces credential stuffing attempts

### Password Policies

Examples:

- Minimum password length
- Password complexity requirements
- Account lockout policies
- Password reuse restrictions

---

# Operating System Hardening

OS Hardening is the process of strengthening systems by reducing vulnerabilities and minimizing attack surfaces.

## Common Hardening Tasks

- Patch Updates
- Baseline Configurations
- Configuration Reviews
- Password Enforcement
- MFA Implementation
- Disable Unused Ports
- Remove Unused Applications
- Access Control Reviews
- Hardware and Software Disposal

### Physical Security Hardening

Examples:

- Security Cameras
- Security Guards
- Controlled Facility Access

---

# Secure Testing Environments

## Virtual Machines (VMs)

Virtualized environments used to safely execute software.

Common Uses:

- Malware Analysis
- Vulnerability Testing
- Security Tool Testing

Advantages:

- Isolation
- Snapshot Recovery
- Safe Experimentation

---

## Sandboxes

Controlled environments used to safely execute suspicious software.

Common Uses:

- Malware Analysis
- Patch Testing
- Attack Simulations

Advantages:

- Reduced risk to production systems
- Safe testing environment

---

# Defense in Depth

Defense in Depth uses multiple security controls to protect organizational resources.

Example Architecture:

Firewall
↓
IDS
↓
IPS
↓
SIEM

Benefits:

- Layered protection
- Reduced single points of failure
- Improved detection and response

---

# Network Security Technologies

## Firewall

Filters network traffic according to predefined rules.

Functions:

- Traffic Filtering
- Port Filtering
- Network Boundary Protection

---

## Intrusion Detection System (IDS)

Detects and alerts on suspicious activity.

Characteristics:

- Signature Detection
- Anomaly Detection
- Alert Generation

Limitations:

- Does not block attacks

---

## Intrusion Prevention System (IPS)

Detects and actively blocks malicious activity.

Features:

- Real-Time Prevention
- Traffic Blocking
- Automated Response

Risks:

- False Positives
- Potential Connectivity Disruption

---

## Security Information and Event Management (SIEM)

Centralized platform that aggregates security logs and events.

Examples:

- Google Chronicle
- Splunk

Benefits:

- Log Correlation
- Threat Detection
- Centralized Monitoring
- Incident Investigation

---

# Network Hardening Techniques

## Port Filtering

Allow only necessary ports.

Benefits:

- Reduced attack surface
- Improved traffic control

---

## Network Segmentation

Separates systems into isolated subnetworks.

Benefits:

- Limits lateral movement
- Reduces breach impact
- Supports least privilege access

---

## Network Access Privileges

Controls who can access specific resources.

Benefits:

- Restricts unauthorized access
- Reduces insider threats

---

# Activity 1 - Security Incident Investigation

## Objective

Analyze suspicious website activity and investigate malicious network traffic.

## Tasks Performed

- Reviewed tcpdump traffic logs
- Analyzed DNS requests
- Investigated HTTP traffic
- Identified suspicious redirects
- Documented incident findings

## Skills Developed

- Packet Analysis
- Log Analysis
- DNS Investigation
- HTTP Investigation
- Incident Reporting
- Root Cause Analysis

---

# Activity 2 - Security Risk Assessment

## Scenario

A social media organization experienced a major data breach.

Identified vulnerabilities:

- Shared employee passwords
- Default administrator password
- Weak firewall configuration
- No MFA implementation

## Tasks Performed

- Vulnerability Identification
- Risk Assessment
- Security Control Selection
- Mitigation Planning
- Security Report Writing

## Recommended Controls

- MFA
- Password Policies
- Firewall Maintenance
- Port Filtering
- Network Access Privileges
- Log Monitoring

## Skills Developed

- Risk Assessment
- Security Documentation
- Security Recommendations
- Security Policy Thinking

---

# Key Skills Demonstrated

## Technical Skills

- Authentication Security
- Security Hardening
- Firewall Management
- IDS / IPS Concepts
- SIEM Monitoring
- Log Analysis
- Vulnerability Assessment
- Network Security

## Analytical Skills

- Incident Investigation
- Root Cause Analysis
- Security Risk Assessment
- Threat Evaluation

## Professional Skills

- Security Documentation
- Technical Communication
- Risk-Based Thinking
- Security Reporting

---

# Reflection

Security is not a single technology but a layered process of prevention, detection, response, and continuous improvement.

This module strengthened my understanding of how organizations harden systems, monitor networks, investigate incidents, assess risks, and implement security controls to reduce the likelihood and impact of cyber attacks.

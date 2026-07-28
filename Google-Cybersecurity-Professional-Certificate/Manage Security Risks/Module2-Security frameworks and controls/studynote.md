# Module 2 Study Notes - Security Frameworks, Controls, CIA Triad, and Risk Management

---

# 1. Security Frameworks and Controls

## Security Frameworks

A security framework is a structured set of guidelines, standards, and best practices that organizations use to manage cybersecurity risks.

Frameworks help organizations:

- Identify security risks
- Establish security policies
- Define security goals
- Support regulatory compliance
- Improve overall security posture

A framework provides direction about **what an organization should achieve**.

Example:

An organization wants to protect healthcare information.

Framework:
- HIPAA security requirements
- NIST CSF guidance

↓

Controls:
- Multi-factor authentication (MFA)
- Access control
- Encryption

---

# Framework vs Security Control

| Framework | Security Control |
|---|---|
| Provides security guidelines | Provides specific protection measures |
| Defines security objectives | Reduces specific risks |
| Focuses on strategy and governance | Focuses on implementation |
| "What should we do?" | "How do we protect it?" |

Example:

NIST CSF = Framework

Firewall = Security Control

---

# Security Controls

Security controls are safeguards designed to reduce specific security risks.

Controls can:

- Prevent attacks
- Detect threats
- Correct security issues

## Types of Security Controls

---

## 1. Physical Controls

Physical controls protect physical assets and locations.

Examples:

- Security guards
- Gates and fences
- Locks
- CCTV cameras
- Access cards

Purpose:

Prevent unauthorized physical access.

---

## 2. Technical Controls

Technical controls use technology to protect systems and data.

Examples:

- Firewall
- Multi-factor authentication (MFA)
- Antivirus software
- Encryption

Purpose:

Protect networks, systems, and information.

---

## 3. Administrative Controls

Administrative controls focus on policies, procedures, and processes.

Examples:

- Separation of duties
- Authorization
- Asset classification
- Security policies
- Employee training

Purpose:

Guide organizational behavior and reduce human-related risks.

---

# 2. CIA Triad

The CIA Triad is a foundational security model used to establish security policies and systems.

CIA represents:

- Confidentiality
- Integrity
- Availability

Organizations use the CIA Triad to evaluate risk and protect critical assets.

---

# Confidentiality

## Definition

Confidentiality ensures that only authorized users can access specific information.

Goal:

Prevent unauthorized disclosure of data.

Examples:

- Access control
- Authentication
- Least privilege

## Principle of Least Privilege

Users should receive only the minimum access required to perform their tasks.

Example:

An accounting employee needs financial systems access but does not need access to software development files.

Key question:

"Who is allowed to access this information?"

---

# Integrity

## Definition

Integrity ensures that data is:

- Correct
- Authentic
- Reliable

Goal:

Prevent unauthorized modification or corruption.

Examples:

- Cryptography
- Encryption
- Hash verification
- Digital signatures

Key question:

"Can we trust this data?"

---

# Availability

## Definition

Availability ensures authorized users can access data and systems when needed.

Goal:

Keep services operational and accessible.

Examples:

- Backup systems
- Disaster recovery
- System maintenance
- High availability architecture

Key question:

"Can authorized users access resources when needed?"

---

# CIA Triad Example

Scenario:

A company protects customer records.

Confidentiality:
- Only authorized employees can view records

Integrity:
- Customer information cannot be changed without authorization

Availability:
- Employees can access records when needed

---

# 3. NIST Cybersecurity Framework (CSF)

## Overview

The National Institute of Standards and Technology (NIST) Cybersecurity Framework is a voluntary framework consisting of:

- Standards
- Guidelines
- Best practices

Purpose:

Manage cybersecurity risk and improve organizational security.

---

# NIST CSF Six Core Functions

## 1. Govern

Purpose:

Establish and improve cybersecurity strategy, policies, roles, and risk management processes.

Focus:

- Governance
- Policies
- Risk management
- Business alignment

---

## 2. Identify

Purpose:

Understand organizational assets, risks, and policies.

Activities:

- Asset management
- Risk assessment
- Business environment analysis

Key idea:

"Know what you have and what risks exist."

---

## 3. Protect

Purpose:

Implement safeguards to protect assets.

Examples:

- Access controls
- Security training
- Authentication
- Data protection

---

## 4. Detect

Purpose:

Identify cybersecurity events quickly.

Examples:

- Monitoring systems
- Log analysis
- SIEM alerts

---

## 5. Respond

Purpose:

Take action during security incidents.

Activities:

- Containment
- Incident analysis
- Communication
- Security improvement

---

## 6. Recover

Purpose:

Restore affected systems to normal operation.

Activities:

- System restoration
- Recovery planning
- Lessons learned

---

# NIST CSF Memory Tip

G I P D R R

Govern  
Identify  
Protect  
Detect  
Respond  
Recover

---

# 4. OWASP Security Principles

OWASP provides security principles to help organizations build safer applications.

---

# Minimize Attack Surface Area

Definition:

Reduce the number of possible entry points attackers can exploit.

Examples:

- Disable unnecessary services
- Remove unused features
- Reduce exposed systems

Goal:

Fewer vulnerabilities = smaller attack surface

---

# Principle of Least Privilege

Users receive only necessary permissions.

Benefits:

- Limits damage from compromised accounts
- Reduces unauthorized access

---

# Defense in Depth

Use multiple layers of security controls.

Example:

Firewall
+
MFA
+
Endpoint protection
+
Monitoring

If one control fails, others provide protection.

---

# Separation of Duties

Critical tasks should require multiple people or approvals.

Example:

One employee requests a payment.

Another employee approves it.

Purpose:

Prevent fraud and abuse.

---

# Keep Security Simple

Avoid unnecessary complexity.

Reason:

Complex systems are harder to secure and maintain.

---

# Fix Security Issues Correctly

Security issues should be fixed by:

1. Finding root cause
2. Containing impact
3. Identifying vulnerabilities
4. Testing remediation

---

# Establish Secure Defaults

The default configuration should already be secure.

Example:

A new application should start with:

- Strong security settings
- Disabled unnecessary features

---

# Fail Securely

When a security control fails, it should fail into a secure state.

Example:

Firewall failure:

Secure failure:
- Block connections

Unsafe failure:
- Allow all traffic

---

# Don't Trust Services

Third-party services should not automatically be trusted.

Organizations must:

- Validate vendors
- Review security controls
- Monitor third-party risk

---

# Avoid Security by Obscurity

Security should not rely only on hiding information.

Example:

Bad practice:
- Keeping source code secret as the only protection

Good practice:
- Encryption
- Strong authentication
- Defense in depth

---

# 5. Security Audits

## Definition

A security audit reviews:

- Security controls
- Policies
- Procedures

against expected standards.

---

# Purpose of Security Audits

Security audits help organizations:

- Identify risks
- Evaluate control effectiveness
- Improve security posture
- Meet compliance requirements

---

# Internal Security Audit Process

## Planning

Includes:

- Establishing scope
- Establishing goals
- Conducting risk assessment

---

## Assessment

Review:

- Existing controls
- Security processes
- Potential risks

Example:

Controls assessment:
Review assets and evaluate whether controls are effective.

---

## Reporting

Communicate:

1. Audit scope and goals
2. Identified risks and compliance requirements
3. Recommendations to improve security posture

---

# 6. GRC Perspective

## Governance

Frameworks define:

- Security direction
- Policies
- Responsibilities

Examples:

- NIST CSF
- ISO 27001

---

## Risk Management

Risk is anything that can impact:

- Confidentiality
- Integrity
- Availability

Risk management involves:

- Identifying threats
- Evaluating impact
- Applying controls

---

## Compliance

Frameworks and audits support compliance with:

- Regulations
- Industry standards
- Organizational requirements

---

# Important Exam Concepts

## Framework vs Control

Framework:
"Provides guidance"

Control:
"Reduces specific risk"

---

## CIA Questions

Confidentiality:
Who can access?

Integrity:
Is the data trustworthy?

Availability:
Can users access it?

---

## NIST CSF

Identify:
Understand assets and risks

Protect:
Implement safeguards

Respond:
Contain and analyze incidents

Recover:
Restore systems

---

## Security Audit

Audit = Review controls against expectations

Goal:
Improve security posture
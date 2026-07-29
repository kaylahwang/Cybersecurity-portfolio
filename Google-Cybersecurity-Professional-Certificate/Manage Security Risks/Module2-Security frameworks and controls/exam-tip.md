# Module 2 Exam Tips - Security Frameworks, Controls, CIA Triad, and Risk Management

---

# 1. Framework vs Control (Important Concept)

## Security Framework

Framework = Security direction and guidance

Purpose:

- Define security objectives
- Provide security guidelines
- Support compliance requirements
- Manage organizational risk

Examples:

- NIST Cybersecurity Framework (CSF)
- ISO/IEC 27001

Common exam phrase:

"Guidelines used for building security plans"

Answer:

Security Framework

---

## Security Control

Control = Specific security measure

Purpose:

- Reduce specific security risks
- Protect organizational assets
- Prevent, detect, or correct security issues

Examples:

### Technical Controls

- Firewall
- Multi-factor authentication (MFA)
- Encryption


### Physical Controls

- CCTV
- Locks
- Security guards


### Administrative Controls

- Security policies
- Employee training
- Separation of duties


Common exam phrase:

"Safeguards designed to reduce specific security risks"

Answer:

Security Control

---

# 2. CIA Triad Quick Memory

## Confidentiality

Keyword:

Authorized access

Main question:

"Who can access the data?"

Examples:

- Authentication
- Authorization
- Least privilege
- Access control


---

## Integrity

Keyword:

Trustworthy data

Main question:

"Is the data correct and reliable?"

Examples:

- Cryptography
- Encryption
- Hashing
- Digital signatures


---

## Availability

Keyword:

Access when needed

Main question:

"Can authorized users access the system?"

Examples:

- Backup
- Disaster recovery
- System maintenance

---

# CIA Scenario Recognition

## Scenario:

"Only authorized employees can view customer records."

Answer:

Confidentiality


---

## Scenario:

"The organization verifies that financial data has not been modified."

Answer:

Integrity


---

## Scenario:

"Employees cannot access an application and security teams restore service."

Answer:

Availability

---

# 3. NIST CSF Six Core Functions

Memory:

G I P D R R

- Govern
- Identify
- Protect
- Detect
- Respond
- Recover


---

# Govern

Focus:

Security strategy and governance

Includes:

- Policies
- Roles and responsibilities
- Risk management
- Business alignment


---

# Identify

Focus:

Understanding the environment

Includes:

- Assets
- Risks
- Policies
- Business environment


---

# Protect

Focus:

Prevent security incidents

Includes:

- Access control
- Security awareness training
- Security tools
- Data protection


---

# Detect

Focus:

Identify security events

Includes:

- Monitoring
- SIEM
- Alerts
- Threat detection


---

# Respond

Focus:

Managing security incidents

Includes:

- Containment
- Incident analysis
- Communication
- Security improvements


---

# Recover

Focus:

Restore normal operations

Includes:

- System recovery
- Service restoration
- Recovery planning

---

# 4. OWASP Security Principles

## Minimize Attack Surface Area

Keyword:

Reduce vulnerabilities

Examples:

- Disable unnecessary features
- Remove unused services
- Limit exposed systems


---

## Principle of Least Privilege

Keyword:

Minimum required access

Example:

Users receive only permissions required for their tasks.


---

## Defense in Depth

Keyword:

Multiple security layers

Example:

Firewall + MFA + Monitoring + Endpoint Protection


---

## Separation of Duties

Keyword:

Multiple approvals

Example:

One employee requests a transaction.

Another employee approves it.


---

## Fix Security Issues Correctly

Process:

1. Identify root cause
2. Contain impact
3. Identify vulnerabilities
4. Test remediation


---

## Establish Secure Defaults

The default configuration should already provide strong security.

Example:

MFA enabled by default.


---

## Fail Securely

When a security control fails, the system should fail into a secure state.

Example:

Firewall failure → Block traffic


---

## Don't Trust Services

Third-party services should be verified before trust is established.

Consider:

- Vendor security controls
- Third-party risk
- Data protection requirements


---

## Avoid Security by Obscurity

Security should not rely only on hiding information.

Weak approach:

- Keeping source code secret

Strong approach:

- Encryption
- Authentication
- Defense in depth

---

# 5. Security Audit

## Definition

A security audit is a review of:

- Security controls
- Policies
- Procedures

against defined expectations.

---

# Audit Objectives

## Identify Risk

Find vulnerabilities and security gaps.


## Evaluate Controls

Determine whether existing controls are effective.


## Improve Security Posture

Recommend improvements to strengthen security.


## Support Compliance

Ensure alignment with regulations and standards.

---

# Audit Planning Process

Steps:

1. Establish scope
2. Establish goals
3. Conduct risk assessment

---

# Audit Reporting

Reports should include:

1. Audit scope and goals

2. Identified risks and compliance requirements

3. Recommendations to improve security posture

---

# 6. Controls Assessment vs Security Audit

## Controls Assessment

Focus:

"Are security controls effective?"

Example:

Review firewall rules, access permissions, and authentication controls.


---

## Security Audit

Focus:

"Are security practices aligned with expectations?"

Example:

Review policies, procedures, and security controls.

---

# 7. Common Exam Traps

## Framework vs Control

Incorrect:

"MFA is a framework"

Correct:

"MFA is a technical control"


---

## Integrity vs Confidentiality

Confidentiality:

Prevents unauthorized access.


Integrity:

Ensures data accuracy and reliability.


---

## Protect vs Recover

Protect:

Implement safeguards before incidents occur.


Recover:

Restore systems after incidents.


---

## Respond vs Recover

Respond:

Contain and analyze incidents.


Recover:

Restore normal operations.

---

# 8. GRC Interview Connections

## How do frameworks support governance?

Frameworks provide structured guidance for developing security policies, managing risks, and aligning cybersecurity objectives with business goals.


---

## Why are controls important?

Controls translate security requirements into practical actions that reduce organizational risk.


---

## Why are audits important?

Audits evaluate control effectiveness and identify opportunities to improve security posture.


---

# Final Summary

Framework:

Defines security direction and best practices.


Control:

Implements specific security protections.


CIA Triad:

Protects information through confidentiality, integrity, and availability.


NIST CSF:

Provides a structured approach for managing cybersecurity risk.


Security Audit:

Evaluates whether security controls are effective.


GRC:

Aligns security practices with business objectives, risk management, and compliance requirements.
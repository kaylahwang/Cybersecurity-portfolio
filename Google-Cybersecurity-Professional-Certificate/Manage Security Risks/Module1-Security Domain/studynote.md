# Study Note: Security Domains & Risk Management

## 🌐 More about the CISSP security domains

### Reading: Security domains cybersecurity analysts need to know
Understanding security domains is essential to navigate specialized areas of cybersecurity. This section covers the **CISSP’s eight security domains** and how they apply to a security analyst's daily tasks.

### 📂 CISSP 8 Security Domains Matrix
| Domain | Focus Area | Core Responsibilities & Tools | Real-World Example for Analysts |
| :--- | :--- | :--- | :--- |
| **Domain 1** | **Security & Risk Management** | Governance, Compliance, Legal, Ethics, BCP, InfoSec design | • Defining organization security goals<br>• Following legal regulations<br>• Maintaining business continuity |
| **Domain 2** | **Asset Security** | Data lifecycle (Storage, Maintenance, Retention, Destruction) | Creating backups to ensure environment restoration during an incident. |
| **Domain 3** | **Security Architecture & Engineering** | Data security management, Design principles, Shared responsibility | Monitoring `SIEM` tools for unusual login or user activity. |
| **Domain 4** | **Communication & Network Security** | Securing physical, wireless, remote, and cloud communications | Designing network security controls (e.g., restricted network access). |
| **Domain 5** | **Identity & Access Management (IAM)** | Trust, Authentication, Authorization, Principle of Least Privilege | Researching ways to improve access and authorization with the primary goal of keeping data secure. |
| **Domain 6** | **Security Assessment & Testing** | Identifying/mitigating risks, Vulnerability scans, Penetration testing | Conducting a security audit or control testing to identify hidden weaknesses. |
| **Domain 7** | **Security Operations** | Incident investigation, Post-breach forensics, Playbook execution | Handling active off-hours attacks and reflecting on lessons learned. |
| **Domain 8** | **Software Development Security** | Secure programming practices, SDLC security, QA testing | • Initiating a secure design review<br>• Conducting secure code reviews<br>• Performing penetration testing |

---

## 🌪️ Navigate threats, risks, and vulnerabilities

### 1. Core Cybersecurity Concepts
* **Vulnerability:** A weakness within an internal system or asset that can be exploited by a threat actor.
* **Risk:** Anything that can impact the confidentiality, integrity, or availability of an asset. 
  * *Formula:* $\text{Risk} = \text{Likelihood of a threat occurring}$
* **Security Posture:** An organization’s ability to manage its defense of **data** and critical assets, and react to change.
* **Business Continuity:** An organization's ability to maintain their **everyday productivity** by establishing risk disaster recovery plans.
* **Shared Responsibility:** The concept that **all individuals** within an organization take an active role in lowering risk and maintaining both physical and virtual security.

### 🔍 Risk & Asset Classification Matrix (Exam Focus)
Risks and impacts vary strictly depending on the asset classification level:
* 🔴 **High-Risk Asset:** Any information protected by regulations or laws (e.g., `SPII`, `PII`). If compromised, it results in severe negative impacts on finances, operations, or reputation.
* 🟡 **Medium-Risk Asset:** If compromised, it may cause *some* damage to an organization's ongoing operations.
* 🟢 **Low-Risk Asset:** Assets that do *not* contain sensitive data. (Note: A low-risk asset compromise does *not* cause severe reputational damage).

### 2. Key Impacts of Security Incidents
When defense systems fail, organizations suffer critical consequences:
* 💰 **Financial damage:** Costs related to recovery and penalties.
* 👤 **Identity theft:** Occurs when sensitive personally identifiable information (`SPII`) is leaked (e.g., through the dark web).
* 📉 **Damage to reputation:** Loss of customer trust and market standing.

### 3. NIST Risk Management Framework (RMF) Steps
The NIST RMF provides a structured, 7-step process to develop risk-management processes and safeguard assets:
```text
[Prepare] ➔ [Categorize] ➔ [Select] ➔ [Implement] ➔ [Assess] ➔ [Authorize] ➔ [Monitor]

Prepare: Related to activities that are necessary to manage security and privacy risks before a breach occurs.

Categorize: Used to develop risk management processes and tasks based on an impact analysis.

Select: Choose, customize, and capture documentation of the controls that protect an organization.

Implement: Implement security and privacy plans for an organization.

Assess: (5th Step) Determine if established controls are implemented correctly and producing desired outcomes.

Authorize: (6th Step) Officially approving a system to operate and being accountable for the security and privacy risks that may exist in an organization.

Monitor: (7th Step) Continuous awareness of how systems are operating and managing ongoing organizational risks.

🛠️ Managing Common Threats, Risks, and Vulnerabilities
1. Risk Management Strategies
Organizations protect assets using four distinct approaches to risk:

Acceptance: Accepting a risk to avoid disrupting business continuity.

Avoidance: Creating a plan to avoid the risk altogether.

Transference: Transferring risk to a third party to manage (e.g., insurance).

Mitigation / Risk Mitigation: The process of having the right procedures and rules in place to quickly reduce the impact of a risk like a breach.

2. Today's Threat & Risk Landscape
Internal Threat: A current or former employee, external vendor, or trusted partner who poses a security risk.

External Threat: Anything outside the organization that has the potential to harm organizational assets.

Advanced Persistent Threats (APTs): A threat actor maintains unauthorized access to a system for an extended period.

Legacy Systems: Old, outdated systems or workstations that can still impact assets.

🛑 Common Attack Tactics
Ransomware: A malicious attack where threat actors encrypt an organization’s data and demand payment to restore access.

Social Engineering: A manipulation technique that exploits human error to gain private information, access, or valuables.

3. Critical Real-World Vulnerabilities
ProxyLogon: Pre-authenticated vulnerability affecting Microsoft Exchange servers.

ZeroLogon: Vulnerability in Microsoft’s Netlogon authentication protocol.

Log4Shell: Enables remote attackers to take control of internet-connected devices and run malicious Java code.

PetitPotam: Affects Windows NTLM, allowing LAN-based attackers to initiate authentication requests.

Security logging and monitoring failures: Insufficient logging capabilities that let attackers exploit vulnerabilities undetected.

Server-side request forgery (SSRF): Manipulating a server-side application into accessing and updating backend resources.
# Module 1 - Foundations of Cybersecurity

## Key Concepts

### What is Cybersecurity?
Protection of networks, devices, people, and data from **criminal exploitation** or unauthorized access.

---

### Core Threats & Risks

**Identity Theft**
- Personal information stolen and used to impersonate a victim
- Used to commit fraud or other criminal activities

**Internal Threats**
- Can come from employees, vendors, or trusted partners
- Not just external attackers

---

### Key Tools & Processes

**SIEM (Security Information and Event Management)**
- Used to identify and analyze security threats, risks, and vulnerabilities
- Core tool for SOC analysts

**Security Audit**
- Review of an organization's security records, activities, and related documents

---

### Key Terminology

| Term | Definition |
|------|------|
| PII | Personally Identifiable Information (e.g., date of birth) |
| SPII | Sensitive PII (e.g., financial information) |
| Regulatory Compliance | Laws and guidelines requiring implementation of security standards |
| Transferable Skills | Skills from past experience applied to a new role |

---

## Lab – Phishing Email Analysis

### Phishing Tactics (Social Engineering)
Psychological tricks used to manipulate victims:
- **Urgency** – "Act now or your account will be closed!"
- **Fear** – "Your account has been locked!"
- **Authority** – Impersonating a manager or executive

### Phishing Indicators (Red Flags)

**Technical Indicators** ← Most definitive
- Incorrect sender email domain (e.g., `yourbank-support.co` instead of `yourbank.com`)
- Mismatched URLs (visible text shows legitimate site, but link points elsewhere)

**Content Indicators** ← Supportive evidence
- Poor grammar and spelling errors
- Generic greetings (e.g., "Dear Customer")
- Unusual requests (e.g., buying gift cards)

---

### Scenario 1 – Fake Bank Security Alert
**Key Red Flag**: Sender email domain  
`security@yourbank-support.co` → Not the official bank domain  
**Type**: ✅ Technical Indicator

**Lesson**: Legitimate banks always use their official domain. A lookalike domain is a definitive sign of phishing.

---

### Scenario 2 – Free Phone Upgrade
**Key Red Flag**: Spelling and grammar errors  
Examples: `Upgradde`, `Phhone`, `Congradulations`, `cutomer`  
**Type**: ✅ Content Indicator

**Lesson**: Professional companies don't make these mistakes. Multiple errors strongly suggest the email is not from a legitimate source.

---

### Scenario 3 – Manager Impersonation (BEC)
**Key Red Flag**: Unusual payment request via gift cards  
Sent from `manager.name@gmail.com` (not a company domain)  
**Type**: ✅ Phishing Tactic – Authority + Urgency

**Lesson**: This is a classic Business Email Compromise (BEC) attack. Legitimate managers never request gift card payments via email.

---

### Scenario 4 – Fake Social Media Security Alert
**Key Red Flag**: Mismatched URL  
- Display text: `Verify Your Account`  
- Actual link: `http://login-security.net/socialmedia/verify`  
**Type**: ✅ Technical Indicator

**Lesson**: Always hover over links before clicking. If the domain doesn't match the company's official domain, it's phishing.

---

### Key Takeaway
> When identifying phishing, always prioritize **technical indicators** (domain name, URL) over content indicators.  
> Technical indicators are verifiable and cannot be faked, making them the most reliable proof of a phishing attempt.

---

*Course 1/9: Foundations of Cybersecurity*  
*Google Cybersecurity Professional Certificate*

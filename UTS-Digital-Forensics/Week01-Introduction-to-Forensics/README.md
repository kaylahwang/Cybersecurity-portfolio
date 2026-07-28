# Week 01 - Introduction to Digital Forensics

## Overview

Week 1 introduced the foundations of Digital Forensics, including digital evidence handling, forensic standards, evidence collection principles, and commonly used forensic tools.

---

## Learning Objectives

- Understand Digital Forensics
- Understand Digital Evidence
- Learn ISO/IEC 27037
- Learn RFC 3227
- Understand Chain of Custody
- Understand Order of Volatility

---

## Digital Forensics

Digital Forensics is the process of identifying, collecting, preserving, acquiring, and analysing digital evidence for investigative purposes.

Digital evidence may originate from:

- Computers
- Mobile phones
- Tablets
- Network devices
- CCTV systems
- Cloud environments
- IoT devices

---

## Digital Evidence

Digital evidence refers to information stored or transmitted in digital form that can support or refute an investigation.

Examples include:

- System logs
- Browser history
- Emails
- Registry entries
- Memory dumps
- Disk images

---

## ISO/IEC 27037

ISO 27037 provides international guidance for the handling of digital evidence.

Core processes:

1. Identification
2. Collection
3. Acquisition
4. Preservation

The goal is to preserve the integrity and authenticity of evidence.

---

## Digital Evidence Roles

### Digital Evidence First Responder (DEFR)

Responsible for:

- Identifying evidence
- Collecting evidence
- Preserving evidence
- Securing incident scenes

### Digital Evidence Specialist (DES)

Responsible for:

- Advanced acquisition
- Forensic analysis
- Specialist investigations

---

## RFC 3227

RFC 3227 provides best-practice guidance for evidence collection and archiving.

Key principles:

- Collect evidence before analysis
- Minimise data alteration
- Document every action
- Maintain detailed notes
- Follow chain of custody procedures

---

## Order of Volatility

Evidence should be collected from most volatile to least volatile.

Typical order:

1. CPU Registers
2. Cache
3. Memory (RAM)
4. Running Processes
5. Temporary File Systems
6. Storage Media
7. Remote Logs
8. Physical Configuration
9. Archive Media

---

## Chain of Custody

Chain of custody documents:

- Who collected evidence
- When evidence was collected
- How evidence was stored
- Evidence transfers
- Evidence access records

Maintaining chain of custody helps ensure legal admissibility.

---

## Common Forensic Tools

### Open Source

- Autopsy
- Sleuth Kit
- Volatility
- SIFT Workstation

### Commercial

- EnCase
- FTK Imager
- Cellebrite
- Magnet Forensics

---

## Reflection

Week 1 provided a strong foundation for understanding how digital evidence should be handled during investigations. Standards such as ISO 27037 and RFC 3227 emphasise the importance of evidence integrity, proper documentation, and reproducible forensic processes.

---

## References

- ISO/IEC 27037
- RFC 3227

# Week 01 - Introduction to Digital Forensics

## Overview

Week 1 introduced the fundamental concepts of Digital Forensics, including the handling of digital evidence, international forensic standards, evidence preservation, and practical evidence discovery using OSForensics.

Digital forensics focuses on identifying, collecting, preserving, acquiring, and analysing digital evidence in a manner that maintains its integrity and admissibility.

---

## Learning Objectives

By the end of Week 1, I was able to:

- Understand the purpose of Digital Forensics
- Define Digital Evidence
- Explain the ISO/IEC 27037 standard
- Explain the RFC 3227 standard
- Understand Chain of Custody requirements
- Understand the Order of Volatility
- Create a forensic case using OSForensics
- Identify digital evidence on a Windows system

---

# Core Concepts

## What is Digital Forensics?

Digital Forensics is the process of identifying, collecting, preserving, acquiring, and analysing digital evidence to support investigations.

Digital forensics is commonly used in:

- Incident Response
- Cybersecurity Investigations
- Criminal Investigations
- Civil Litigation
- Internal Corporate Investigations

---

## Digital Evidence

Digital evidence is any information stored or transmitted in digital form that may be used to support or refute an investigation.

Examples include:

- Browser history
- Emails
- File metadata
- Registry entries
- Memory contents
- Network logs
- Disk images

---

# ISO/IEC 27037

ISO/IEC 27037 provides international guidelines for handling digital evidence.

The four primary processes are:

1. Identification
2. Collection
3. Acquisition
4. Preservation

The goal is to ensure evidence maintains its integrity and authenticity throughout an investigation.

### Investigation Roles

#### Digital Evidence First Responder (DEFR)

Responsible for:

- Recognising evidence
- Securing incident scenes
- Collecting evidence
- Preserving evidence integrity

#### Digital Evidence Specialist (DES)

Responsible for:

- Advanced acquisition techniques
- Technical forensic analysis
- Specialist investigations

---

# RFC 3227

RFC 3227 provides guidelines for evidence collection and archiving during security incidents.

Key principles include:

- Collect evidence before analysis
- Minimise alteration of evidence
- Maintain detailed documentation
- Follow a repeatable methodology
- Preserve evidence integrity

One of the most important principles is:

> Collect first, analyse later.

---

# Order of Volatility

Evidence should be collected from most volatile to least volatile.

Typical order:

1. CPU Registers
2. CPU Cache
3. RAM
4. Running Processes
5. Temporary File Systems
6. Storage Media
7. Remote Logs
8. Physical Configuration
9. Archive Media

Collecting volatile evidence first reduces the risk of losing important information.

---

# Chain of Custody

Chain of Custody is the documented history of evidence handling.

Information typically recorded includes:

- Who collected the evidence
- When evidence was collected
- Where evidence was collected
- How evidence was stored
- Who accessed the evidence
- Any transfer of evidence ownership

Maintaining Chain of Custody helps ensure evidence remains admissible and trustworthy.

---

# Practical Investigation – OSForensics

## Investigation Objective

The objective of this practical exercise was to introduce forensic investigation techniques and demonstrate how user activity can be identified as digital evidence.

---

## Tool Used

### OSForensics

OSForensics is a digital forensic toolkit used to:

- Create investigation cases
- Search user activity
- Analyse browser artifacts
- Index files
- Locate evidence on Windows systems

---

## Activity 1 – Generate Evidence

To create forensic artifacts for analysis:

1. Opened Google Chrome
2. Searched for "Seek Roles"
3. Visited seek.com.au
4. Closed the browser

Additional evidence was created by generating a text file named:

```text
Contacts.txt
```

The file contained the keyword:

```text
Tony
```

---

## Activity 2 – Create a Forensic Case

A new forensic case was created within OSForensics.

Example details:

```text
Case Name: Week 1
Investigator: Student
```

This demonstrated how investigators organise and document evidence.

---

## Activity 3 – User Activity Investigation

The User Activity module was used to:

- Scan the local system
- Review browser activity
- Locate browsing artifacts

Evidence identified:

- Google Chrome browser history
- Visit to seek.com.au

This demonstrated how web browsing activity can become digital evidence.

---

## Activity 4 – File Indexing

Desktop text files were indexed using OSForensics.

The index was searched using the keyword:

```text
Tony
```

Evidence located:

```text
Contacts.txt
```

This demonstrated how forensic indexing enables investigators to quickly locate relevant information within large data sets.

---

# Evidence Identified

## Browser Evidence

Recovered examples of:

- Web searches
- Browser history
- Website visits
- User activity records

Example:

```text
seek.com.au
```

---

## File Evidence

Recovered examples of:

- Text file content
- Indexed file data
- User-generated files

Example:

```text
Contacts.txt
Keyword: Tony
```

---

# Key Learning Outcomes

This practical exercise demonstrated that:

- User activity leaves identifiable digital artifacts.
- Browser history can provide useful investigative evidence.
- File indexing significantly improves evidence discovery.
- Windows systems store large volumes of potentially valuable evidence.
- Forensic tools help investigators efficiently locate relevant information.

---

# Reflection

Week 1 provided a strong foundation in Digital Forensics by introducing internationally recognised standards, forensic evidence handling procedures, and practical evidence collection techniques.

The OSForensics exercise showed that routine user actions such as visiting websites and creating files leave recoverable digital traces. These traces can later be collected, preserved, and analysed as evidence during an investigation.

---

# Related Resources

- Resources/ISO27037.md
- Resources/RFC3227.md
- Resources/ChainOfCustody.md
- Resources/OrderOfVolatility.md

---

# References

1. ISO/IEC 27037 – Guidelines for Identification, Collection, Acquisition and Preservation of Digital Evidence
2. RFC 3227 – Guidelines for Evidence Collection and Archiving
3. UTS Digital Forensics Week 1 Lecture Materials
4. Week 01 Investigations Instructions
5. Week 01 Investigations Report Template

# Course 3, Module 2 - Network Security

## Overview

This module covered how organizations defend the network perimeter — protocols, firewalls, proxy servers, security zones, VPNs, and subnetting — and how to read live network traffic to diagnose a real incident. The centerpiece of this module is a hands-on incident investigation (below), where I used `tcpdump` packet analysis to trace a website outage to a DNS resolution failure.

## Applied: Incident Investigation

**[Incident Report: Website Outage — DNS Resolution Failure](./Incident-Report-DNS-ICMP-Outage.md)**

Given a customer-reported outage and a raw `tcpdump` capture, I identified that DNS queries over UDP port 53 were failing (returning ICMP "port unreachable" errors instead of resolved IP addresses), correctly scoped the issue to the DNS layer rather than the web server, and produced a structured incident report separating confirmed findings from open hypotheses and next steps.

This is the practical counterpart to the protocol/port knowledge below — being able to look at raw traffic and say *which* protocol failed and *why* is the actual SOC/analyst skill; memorizing port numbers is just the prerequisite.

## Key Concepts

### Protocols in Three Categories

| Category | Purpose | Examples |
|---|---|---|
| Communication | Governs how data is exchanged and its timing | TCP, UDP, HTTP, DNS |
| Management | Monitors/manages network activity, error reporting | SNMP, ICMP, DHCP |
| Security | Encrypts data in transit | HTTPS, SFTP/SSH, IPSec, SSL/TLS |

Ports worth knowing cold (came up repeatedly in labs and quizzes): **20/21 FTP · 22 SSH · 23 Telnet · 25 SMTP · 53 DNS · 67/68 DHCP · 80 HTTP · 110 POP3 · 143 IMAP · 443 HTTPS · 587 SMTP(TLS) · 995 POP3(SSL/TLS)**.

### Wireless Security Evolution

`WEP (1999, broken) → WPA (2003, TKIP, KRACK-vulnerable) → WPA2 (2004, AES/CCMP, still KRACK-vulnerable) → WPA3 (2018, SAE fixes KRACK)`

### Subnetting & CIDR

Subnetting divides one network into smaller, organized subnets — improving efficiency and enabling security zoning without requesting new address space from the ISP. CIDR (`198.51.100.0/24`) replaced the older classful addressing system to make this flexible.

### Firewalls

**Stateless** (static rules, no memory, needs rules both directions) → **Stateful** (tracks connection state, one-directional rules) → **NGFW** (adds deep packet inspection, intrusion prevention, application-layer awareness).

### Proxy Servers

- **Forward proxy**: handles internal clients' *outbound* requests — hides internal IPs, approves/forwards outbound traffic.
- **Reverse proxy**: handles *inbound* external requests to internal servers — protects internal servers from direct exposure.

### Security Zones

`Uncontrolled zone (internet) → Controlled zone (buffer) → DMZ (perimeter, internet-facing servers) → Restricted zone (highest sensitivity, privileged access only)`

### VPNs

Encrypt traffic and mask IP via **encapsulation**. Remote access VPN (individual → server) vs. site-to-site VPN (network → network, often via IPSec). WireGuard = newer/faster/simpler; IPSec = older/more established/broadly supported.

---

## Key Takeaway

Network security is layered defense — protocols with known ports, firewalls of increasing sophistication, proxies, subnetted security zones, and VPNs — but the applied skill isn't memorizing the layers, it's being able to read live traffic and correctly localize a failure to the right layer, as demonstrated in the incident report above.

---

*Course 3, Module 2: Networks and Network Security*
*Google Cybersecurity Professional Certificate*
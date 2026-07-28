# Module 1 - Network Architecture

## Key Concepts

### Network Devices

Network devices maintain and route information between users on a network. Understanding their roles is foundational to identifying where vulnerabilities exist and how attackers exploit them.

| Device | Role | Security Relevance |
|---|---|---|
| Firewall | Monitors and restricts inbound/outbound traffic | First line of defense — not a complete defense on its own |
| Server | Responds to client requests (client-server model) | DNS, file, and mail servers are common targets |
| Hub | Broadcasts data to all connected ports | Vulnerable to eavesdropping — rarely used in modern networks |
| Switch | Forwards packets only to the intended device via a MAC address table | Improves both performance and security |
| Router | Routes traffic between networks based on IP address | Can include built-in firewall functionality |
| Modem | Converts ISP signals into a format usable by the local network | Entry point from the ISP |
| Wireless Access Point | Sends/receives data over radio waves using Wi-Fi | — |

Security analysts use **network diagrams** to visualize this architecture and develop strategies to secure it.

---

### Cloud Computing & Software-Defined Networks

- **On-premise vs. Cloud**: on-premise keeps infrastructure physically owned by the company; cloud uses a **Cloud Service Provider (CSP)**'s remote servers instead.
- **Service models**:
  - **SaaS** – ready-to-use software, hosted remotely
  - **IaaS** – virtual infrastructure (compute/storage), configured via API/console
  - **PaaS** – development platform for building custom applications
- **Hybrid cloud** (CSP + on-premise) vs. **multi-cloud** (2+ CSPs) — most organizations use hybrid for cost and control.
- **SDN (Software-Defined Networks)**: virtualized switches, routers, and firewalls, hosted at the CSP's data center.
- **Why organizations adopt cloud**: reliability, cost efficiency (no upfront infrastructure spend), scalability (elastic, pay-as-you-go), remote accessibility, and built-in business analytics for monitoring traffic. Note: cloud adoption does **not** remove the need for additional security measures — this is a common misconception.

---

### TCP/IP Model (4 Layers)

| Layer | Function | Key Protocols |
|---|---|---|
| Application | User-facing network requests | HTTP, SMTP, SSH, FTP, DNS |
| Transport | Delivery + flow control between systems | TCP (reliable), UDP (fast, connectionless) |
| Internet | Routes packets to the destination network | IP, ICMP |
| Network Access | Physical transmission + local addressing | ARP, hubs, cables |

---

### OSI Model (7 Layers)

A more granular version of the TCP/IP model, used by security professionals to communicate precisely about where in the stack an issue occurred.

`Application → Presentation → Session → Transport → Network → Data Link → Physical`

- **Presentation (L6)**: data translation/encryption (e.g., SSL for HTTPS)
- **Session (L5)**: establishes, maintains, and terminates connections; handles authentication and checkpoints
- **Network (L3)**: IP-based routing between networks
- **Data Link (L2)**: packet delivery within a single network (switches, NICs)
- **Physical (L1)**: raw hardware transmission (hubs, modems, cabling)

---

### IP Addressing & Packet Structure

- An **IP address identifies the location** of a device on a network.
- **IPv4**: 4 decimal numbers (0–255), ~4.3 billion addresses (e.g., `172.16.254.1`)
- **IPv6**: 8 hexadecimal groups, ~340 undecillion addresses — developed to solve **IPv4 address exhaustion**
- **Public IP**: ISP-assigned, tied to geographic location, shared across a LAN via NAT
- **Private IP**: local-network-only, not geographically tied
- **IPv4 header** carries routing metadata (source/destination IP, TTL, protocol, checksum) — not the actual message content, which lives in the data section
- **TTL** prevents infinite routing loops; **checksum** detects header corruption

---

## Lab / Quiz Highlights

- Correctly distinguished **LAN vs. WAN** by geographic scope, and **TCP/IP vs. OSI** (4 vs. 7 layers).
- Identified **hub** as the broadcast device and **switch** as the MAC-address-table-based device — a recurring exam distinction.
- Identified the valid reasons a security professional would adopt a CSP: elastic pay-as-you-go processing power, remote accessibility of web applications, and built-in traffic/sales analytics. Confirmed that "no additional cloud security measures needed" is a **false** benefit — cloud environments still require dedicated security controls (shared responsibility model).
- One self-corrected item: initially selected **Private IP** instead of **Public IP** for "ISP-assigned, geographically tied" — corrected and logged in studynote.md.

---

## Key Takeaway

Network architecture — devices, addressing, and layered models (TCP/IP, OSI) — provides the structural foundation for identifying where security controls belong and where an incident originated. This maps directly onto later GRC/audit work: understanding *which layer or control* failed is the first step in both incident response and control-gap analysis.

---

*Course 3/9: Network-Security*
*Google Cybersecurity Professional Certificate*
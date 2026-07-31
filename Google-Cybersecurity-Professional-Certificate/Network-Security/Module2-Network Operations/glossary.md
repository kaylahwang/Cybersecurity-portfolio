# Course 3, Module 2 - Network Security: Glossary

## Protocols

| Term | Definition | In Practice |
|---|---|---|
| Network Protocol | A set of rules two or more devices use to describe the order of delivery and structure of data | The common "language" all network devices rely on |
| TCP (Transmission Control Protocol) | A connection-oriented protocol that allows two devices to form a connection and stream data | Establishes a connection via a three-way handshake (SYN → SYN/ACK → ACK) |
| UDP (User Datagram Protocol) | A connectionless protocol used when speed matters more than reliability | Common for DNS lookups and streaming |
| HTTP | An application-layer protocol enabling communication between clients and web servers | Port 80, unencrypted |
| HTTPS | A secure version of HTTP using SSL/TLS encryption | Port 443; digital certificates authenticate the connection |
| DNS (Domain Name System) | A protocol that translates domain names into IP addresses | UDP port 53 (switches to TCP for large responses) |
| SNMP (Simple Network Management Protocol) | A protocol for monitoring and managing network devices | Can reset configs, report bandwidth usage |
| ICMP (Internet Control Message Protocol) | A protocol used to report data transmission errors between devices | Basis of the `ping` command |
| SFTP (Secure File Transfer Protocol) | A secure protocol for transferring files between devices | Uses SSH, typically TCP port 22; common with cloud storage |
| SSH (Secure Shell) | A protocol for creating a secure, encrypted connection to a remote system | TCP port 22; replaces Telnet |
| Telnet | A protocol for remote system access that sends data in clear text | TCP port 23 — insecure |
| DHCP (Dynamic Host Configuration Protocol) | A management protocol that auto-assigns IP addresses and network settings to devices | UDP port 67 (server) / 68 (client) |
| ARP (Address Resolution Protocol) | A protocol used to determine the MAC address of the next device/router on the path | Layer 2 — no port number |
| POP3 (Post Office Protocol v3) | An email protocol that downloads mail to a local device | Port 110 (plain) / 995 (encrypted) — doesn't reliably sync across devices |
| IMAP (Internet Message Access Protocol) | An email protocol that keeps mail on the server for multi-device access | Port 143 (plain) / 993 (encrypted) |
| SMTP (Simple Mail Transfer Protocol) | A protocol used to send and route outgoing email | Port 25 (plain) / 587 (encrypted); helps throttle spam |

## Wireless Security

| Term | Definition | In Practice |
|---|---|---|
| IEEE 802.11 (Wi-Fi) | Standards defining communication for wireless LANs | Maintained by the IEEE; "Wi-Fi" is a marketing term from the Wi-Fi Alliance |
| WEP (Wired Equivalent Privacy) | The earliest wireless security protocol (1999) | Now considered high-risk/breakable |
| WPA (Wi-Fi Protected Access) | A wireless security protocol improving on WEP via TKIP | Vulnerable to KRACK attacks |
| WPA2 | The current baseline Wi-Fi security standard, using AES/CCMP | Personal mode (home) vs. Enterprise mode (centralized control) |
| WPA3 | The latest Wi-Fi security standard | Fixes WPA2's KRACK vulnerability via SAE |

## Addressing & Subnetting

| Term | Definition | In Practice |
|---|---|---|
| NAT (Network Address Translation) | Translates private IP addresses into a shared public IP for internet-facing traffic | Requires a router/firewall configured for NAT |
| Subnetting | Dividing one large network into smaller, organized subnets | Improves efficiency and enables security zoning |
| CIDR (Classless Inter-Domain Routing) | A flexible method for assigning subnet masks, replacing older classful addressing | Notation example: `198.51.100.0/24` |
| Network Segmentation | A security technique that divides a network into sections | Basis for creating security zones |

## Security Zones

| Term | Definition | In Practice |
|---|---|---|
| Security Zone | A segment of a company's network that protects the internal network from the internet | Building block of layered network defense |
| Uncontrolled Zone | The portion of the network outside the organization | Effectively "the internet" from the org's perspective |
| Controlled Zone | A subnet that protects the internal network from the uncontrolled zone | — |
| DMZ (Demilitarized Zone) | A perimeter zone isolating internet-facing servers from the internal network | — |
| Restricted Zone | Protects highly confidential information, accessible only to privileged users | Typically sits behind its own dedicated firewall |

## Firewalls

| Term | Definition | In Practice |
|---|---|---|
| Firewall | A network security device that monitors and filters traffic to/from a network | Rules based on port number and IP address |
| Stateless Firewall | Operates on predefined rules only, without tracking packet history | Requires rules configured in both directions |
| Stateful Firewall | Tracks passing connection information and proactively filters threats | Only needs a rule in one direction (uses a state table) |
| NGFW (Next-Generation Firewall) | The most advanced firewall class, with deep packet inspection and intrusion prevention | Application-aware; can include malware sandboxing, AV, URL/DNS filtering |
| Cloud-Based Firewall | A software firewall hosted by a cloud service provider | — |
| Port Filtering | A firewall function that blocks/allows traffic based on port number | E.g., restricting POP3 (995) access to only internal IPs |

## Proxies & VPNs

| Term | Definition | In Practice |
|---|---|---|
| Proxy Server | A server that fulfills client requests by forwarding them to other servers | Uses NAT to sit between clients and external threats |
| Forward Proxy Server | Regulates and restricts a client's outgoing access to the internet | Approves/forwards outbound employee traffic; masks internal IPs |
| Reverse Proxy Server | Regulates and restricts the internet's incoming access to an internal server | Protects internal servers from direct exposure |
| VPN (Virtual Private Network) | A service that changes a user's public IP and masks their location to keep data private on a public network | Encrypts data in transit end-to-end |
| Encapsulation | The process of wrapping sensitive data inside other data packets | Performed by VPN services to protect data in transit |
| Remote Access VPN | Connects an individual device to a VPN server | Common for remote work |
| Site-to-Site VPN | Connects entire office networks/locations together | More complex to manage; often uses IPSec |
| WireGuard | A newer, faster, open-source VPN protocol | Good for high-speed use cases like streaming/downloads |
| IPSec | An older, widely supported, extensively tested VPN protocol | Common in site-to-site VPN configurations |
| SD-WAN (Software-Defined WAN) | A virtual WAN service securely connecting users to applications across multiple locations | Increasingly paired with VPNs for cloud-based network security |

---

*Course 3, Module 2: Networks and Network Security*
*Google Cybersecurity Professional Certificate*
# Course 3, Module 2 - Network Security: Study Notes

## 1. Common Network Protocols

**What a protocol is**: a shared set of rules that tells devices how to structure and deliver data — essentially a common language across all network devices. Even though protocols are essential, some carry security risk (e.g., DNS can be exploited to redirect legitimate traffic to a malicious site).

**Communication protocols**
- **TCP**: connection-oriented. Uses a **three-way handshake**: device sends SYN → server responds SYN/ACK → device sends final ACK → connection established. Operates at the transport layer.
- **UDP**: connectionless — no handshake, less reliable, but faster. Used for time-sensitive traffic like DNS requests to local servers. Also transport layer.
- **HTTP**: application layer, port 80. Insecure — being phased out in favor of HTTPS.
- **DNS**: application layer, resolves domain names to IPs. Normally UDP port 53, switches to TCP if the reply is large.

**Management protocols**
- **SNMP**: monitors/manages devices — can reset passwords, change configs, report bandwidth usage. Application layer.
- **ICMP**: reports transmission errors between devices. Basis of the `ping` command for troubleshooting connectivity/latency. Internet layer.

**Security protocols**
- **HTTPS**: HTTP + SSL/TLS encryption, port 443.
- **SFTP**: secure file transfer using SSH, typically TCP port 22 — uses AES encryption. Common with cloud storage uploads/downloads.

*(Note from the reading: encryption protocols like HTTPS/SFTP do NOT hide the source/destination IP address — an attacker intercepting traffic can still learn basic metadata even if the payload is encrypted.)*

---

## 2. Additional Network Protocols

**NAT (Network Address Translation)**
- Private IPs (used only within the LAN) can't communicate directly with the public internet — NAT translates them into a single public IP for outbound traffic and reverses it for inbound responses.
- Requires a router/firewall configured specifically for NAT. Operates across the internet and transport layers.
- Private IP ranges: `10.0.0.0–10.255.255.255`, `172.16.0.0–172.31.255.255`, `192.168.0.0–192.168.255.255` — assigned by the router, free, only unique within the LAN.
- Public IPs: assigned by the ISP/IANA, globally unique, cost to lease.

**DHCP**: management protocol, application layer. Auto-assigns IP addresses + DNS server + default gateway to devices. DHCP servers use UDP port 67; clients use UDP port 68.

**ARP**: translates IP addresses (in packets) into MAC addresses. Network access layer (Layer 2) — no port number, since ports are an application-layer (Layer 7) concept. Each device keeps an **ARP cache** of known IP↔MAC mappings.

**Telnet vs. SSH**
- Telnet: remote system access, sends everything in **clear text** — insecure. TCP port 23.
- SSH: secure alternative to Telnet — encrypted authentication and communication. TCP port 22.

**Email protocols**
- **POP3**: downloads email to a local device; mail may or may not remain on the server afterward → doesn't reliably sync across multiple devices. Port 110 (plain) / 995 (SSL/TLS).
- **IMAP**: downloads headers + content but keeps mail on the server → supports multi-device sync, and allows partial reading before a message finishes downloading. Port 143 (plain) / 993 (TLS).
- **SMTP**: sends/routes outgoing mail using MTA software that queries DNS to resolve recipient addresses. Port 25 (plain, often abused for spam) / 587 (TLS). SMTP also helps throttle spam by regulating how many emails a source can send.

*(Memory tip: POP = "pull it down and (maybe) delete it locally" vs. IMAP = "keep it on the server, sync everywhere." That's the core distinction that quiz questions test.)*

**Port filtering**: firewalls can allow/deny traffic based on port number — e.g., restricting POP3 (port 995) access to only the organization's own IP ranges.

---

## 3. The Evolution of Wireless Security Protocols

**Background**: Wi-Fi = a marketing term for the IEEE 802.11 family of wireless standards (the IEEE maintains these standards; WECA/Wi-Fi Alliance coined the "Wi-Fi" branding).

| Protocol | Year | Key Points | Weakness |
|---|---|---|---|
| WEP | 1999 | Oldest wireless security protocol; tries to match wired-level privacy | Encryption is breakable — now high-risk, still occasionally found on old/misconfigured hardware |
| WPA | 2003 | Fixed WEP via TKIP (larger keys), added message integrity checks | Vulnerable to KRACK attacks (attacker inserts a zeroed key during the handshake) |
| WPA2 | 2004 | Uses AES + CCMP; current baseline standard. Personal mode (single shared passphrase, good for home) vs. Enterprise mode (centralized, per-user credentials, no user ever sees the key) | Still vulnerable to KRACK |
| WPA3 | 2018 | Fixes the KRACK handshake vulnerability using SAE (Simultaneous Authentication of Equals); 128-bit encryption (192-bit optional in Enterprise) | Still gaining adoption as compatible devices roll out |

*(Personal note: this history is a good example of how security standards evolve reactively — each version exists specifically because a documented attack broke the previous one. Useful narrative for interviews about "why does security keep changing.")*

---

## 4. Subnetting and CIDR

- **Subnetting**: dividing one large network into smaller "subnets," similar to dividing a city into neighborhoods. Each subnet is defined by a unique IP + network mask combination. Improves efficiency (switches keep same-subnet traffic local) and supports security zoning.
- **Classful vs. classless addressing**: 1980s classful addressing (Class A–E) ran out of room as internet adoption grew in the 1990s. **CIDR** replaced it with a flexible, classless system.
- **CIDR notation**: an IPv4 address + `/` + a network prefix number, e.g., `198.51.100.0/24` — this single notation represents the entire range `198.51.100.0`–`198.51.100.255`.
- **Security benefit**: subnetting lets an organization create internal "networks within a network" without requesting additional address space from its ISP — combined with physical isolation, routing rules, and firewalls to build isolated segments.

---

## 5. Virtual Networks and Privacy

**Firewalls (deeper dive)**

| Type | Behavior |
|---|---|
| Stateless | Filters using fixed, predefined rules only; no memory of previous packets — needs rules configured in both directions |
| Stateful | Maintains a "state table" tracking active connections; only needs a rule in one direction since it recognizes return traffic automatically |
| NGFW (Next-Generation Firewall) | Most advanced tier — adds deep packet inspection + intrusion prevention + application-layer awareness. Can filter by *application*, not just IP/port. May include malware sandboxing, antivirus, URL/DNS filtering. |

**Proxy servers**
- Use NAT to sit between internal clients and external threats.
- **Forward proxy**: handles internal clients' requests going *out* to external resources.
- **Reverse proxy**: handles external requests coming *in* to internal services — regulates and restricts internet access to an internal server.
- Can be configured with filtering rules, similar to a firewall (e.g., blocking known-malicious sites).

**VPNs**
- Encrypts data in transit and disguises the user's IP via **encapsulation** — wrapping unencrypted data inside an encrypted packet so it can travel safely over the public internet.
- Used by both enterprises (securing device-to-corporate-resource communication) and individuals (personal privacy).
- Increasingly paired with **SD-WAN** (software-defined WAN) to securely connect users to applications across multiple locations at scale.

---

## 6. VPN Protocols: WireGuard and IPSec

- A **VPN protocol** is a specific rule set (like a network protocol) that determines how the secure tunnel between endpoints is formed.
- **Remote access VPN**: connects an individual device to a VPN server — typically for personal/remote-work use, established over the internet.
- **Site-to-site VPN**: connects entire office networks/locations together — more complex to configure/manage, common for multi-office enterprises. IPSec is commonly used here.

| | WireGuard | IPSec |
|---|---|---|
| Age | Newer | Older, more established |
| Speed | Faster — fewer lines of code, ideal for streaming/large downloads | Comparatively slower |
| Complexity | Simple to set up and maintain | More complex |
| Openness | Open source | Vendor/OS support varies, but very broadly supported |
| Use case | Site-to-site AND remote access | Primarily site-to-site |

---

## 7. Quiz Review (Consolidated)

### Concept-check items

- Network protocols describe the **order of delivery and structure of data** (not speed, access level, or max size).
- **HTTPS** is the protocol that secures client–web server communication (uses SSL/TLS, can run on ports 443 and 80).
- **SSL/TLS** is the underlying security protocol that keeps information safe from malicious actors by securing HTTP into HTTPS.
- **IEEE 802.11 (Wi-Fi)** = standards defining wireless LAN communication — confirmed true.
- **Firewall** = the device that monitors and filters traffic in/out of a network, allowing/denying based on defined rules.
- **Stateful** (not stateless) firewalls track passing information and proactively filter threats — a commonly reversed true/false trap.
- **Encapsulation** is performed by a **VPN service** to protect data by wrapping it in other packets.
- **Restricted zone** protects highly confidential information accessible only to privileged employees, typically behind its own firewall.
- **Reverse proxy server** regulates/restricts access from the internet to an internal server (accepts, approves, then forwards external traffic inward).
- Wireless protocol facts (3 correct out of 4 options): IEEE 802.11 = Wi-Fi; WPA relates to internet connection security; the IEEE maintains Wi-Fi standards. (❌ "Wi-Fi provides significantly lower security than wired connections" was **not** marked correct — a nuance worth double-checking rather than assuming as fact.)
- **Port filtering** = the firewall function that blocks/allows specific port numbers to limit unwanted traffic.
- **NGFW** = the firewall type capable of deep packet inspection and intrusion detection.
- A **VPN** is the correct tool for securely enabling remote work with access to internal resources.
- **Encapsulation** (again) = the fill-in-the-blank answer for "VPN services perform ___ to protect sensitive data by wrapping it in other packets."
- A **controlled zone** protects the internal network from the **uncontrolled zone**.
- The **DMZ** = the zone acting as a perimeter, isolating internet-facing servers from the internal network.
- A generic **proxy server** fulfills client requests by forwarding them to other servers.
- Forward proxy servers secure internal networks by: (1) hiding a user's IP address and approving all outgoing requests, and (2) receiving outgoing traffic from an employee, approving it, then forwarding it to its destination on the internet. (❌ "protecting internal web servers with confidential data" is a **reverse** proxy function, not forward; ❌ "both forward and reverse add protection from the internet" is too generic to be the specific answer this question was testing for.)

---

*Course 3, Module 2: Networks and Network Security*
*Google Cybersecurity Professional Certificate*
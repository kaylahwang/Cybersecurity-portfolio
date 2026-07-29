# Module 1 - Network Architecture: Study Notes

## 1. Network Components, Devices, and Diagrams

**Core idea: how network devices communicate**

Network devices connect over wired and wireless connections, and once a connection is established, they exchange data packets containing source and destination information. The "network" is the overall infrastructure that lets devices communicate; "network devices" like routers and switches manage what's sent and received within it.

**By device:**

- **Firewall**: The first line of defense — monitors and restricts inbound/outbound traffic based on organization-defined security rules. Typically sits between the secured internal network and untrusted external networks (like the internet). *(Key point: a firewall is only one layer of defense, not a complete solution — ties directly into the defense-in-depth concept.)*
- **Server**: Responds to client requests in the client-server model. Examples: DNS servers, file servers, mail servers.
- **Hub vs. Switch**:
  - Hub: repeats incoming information out to every connected port → vulnerable to eavesdropping → rarely used on modern networks, mostly limited to small home-office setups.
  - Switch: maintains a MAC address table and forwards packets only to the intended device → improves both performance and security. Operates at the TCP/IP data link layer.
- **Router**: Connects different networks and routes traffic based on destination IP address. Operates at the TCP/IP network layer. Some routers include built-in firewall functionality.
- **Modem**: Connects the local network to an ISP, converting incoming signals into a format the router/local network can use.
- **Wireless Access Point (WAP)**: Sends/receives digital signals over radio waves to create a wireless network, using Wi-Fi protocols to relay data to routers and switches.

**Security analysts and network diagrams**: Network diagrams are maps showing devices and how they connect. Security analysts use them to develop and refine strategies for securing network architecture. *(Personal note: the principle "you have to understand the structure before you can find the vulnerabilities" connects directly to the risk-assessment process in GRC.)*

---

## 2. Cloud Computing and Software-Defined Networks

**On-premise vs. Cloud**: On-premise networks keep all infrastructure at a location physically owned by the company. Cloud computing uses remote servers, applications, and network services hosted on the internet via a Cloud Service Provider (CSP), accessed through the CSP's API or web console.

**Three CSP service models**
- **SaaS**: Ready-to-use software hosted remotely (e.g., Gmail, Google Docs) — no hosting required by the customer.
- **IaaS**: Virtual computing resources (containers, storage) configured remotely via API/console — existing applications can be moved with minimal modification.
- **PaaS**: A development platform for building custom applications tailored to a company's needs.

*(Memory tip: the amount of infrastructure a company manages directly decreases in the order IaaS > PaaS > SaaS.)*

**Hybrid vs. Multi-Cloud**: Hybrid = CSP services + on-premise infrastructure combined (most organizations choose this for cost savings and control). Multi-cloud = using 2+ CSPs.

**SDN (Software-Defined Networks)**: Virtualizes physical network devices (switches, routers, firewalls) so packet routing is handled by software. In cloud environments, SDN tools are hosted on servers at the CSP's data center.

**Three main benefits of cloud computing**: Reliability (availability, secure connections, consistent uptime), Cost (large-scale CSP data centers offer services far cheaper than self-managed infrastructure), Scalability (elastic, pay-as-you-go model that adapts to changing business needs).

*(GRC note: as organizations move to the cloud, the shared responsibility model — who owns which security obligations — becomes central. This directly connects to why "CSPs remove the need for additional security measures" is a false statement in the quiz below.)*

---

## 3. TCP/IP Model (4 Layers)

A framework for visualizing how data is organized and transmitted across a network. Security professionals use it to determine which layer(s) were affected during an incident.

1. **Network Access Layer** (a.k.a. Data Link): packet creation and physical transmission — hubs, modems, cables. **ARP** maps IP addresses to MAC addresses for local delivery.
2. **Internet Layer** (a.k.a. Network): ensures delivery to the destination host. **IP** routes packets to the correct destination; **ICMP** shares error/status information for troubleshooting.
3. **Transport Layer**: delivers data between systems and controls traffic flow. **TCP** (connection-oriented, reliable, includes port number) vs. **UDP** (connectionless, prioritizes speed — e.g., video streaming).
4. **Application Layer**: handles requests/responses and defines which services are accessible. Key protocols: **HTTP, SMTP, SSH, FTP, DNS**.

*(Memory tip: TCP = reliability first (guarantees retransmission); UDP = speed first — think of it as a "reliability vs. speed" tradeoff.)*

**TCP/IP vs. OSI**: OSI is more granular (7 layers vs. 4). OSI is typically used when professionals need to communicate more precisely about where an issue occurred. Both models conceptualize data transmission in layers.

---

## 4. The OSI Model (7 Layers)

Reviewed from Layer 7 (closest to the user) down to Layer 1 (physical hardware):

| Layer | Name | Core Function | Protocols/Examples |
|---|---|---|---|
| 7 | Application | Direct user interaction with the network | HTTP/HTTPS, SMTP, DNS |
| 6 | Presentation | Data format translation and encryption | SSL (core of HTTPS), compression |
| 5 | Session | Establishes/maintains/terminates sessions; authentication, reconnection, checkpoints | — |
| 4 | Transport | Delivery, flow/speed control, segmentation | TCP, UDP |
| 3 | Network | Delivers frames to the destination via IP-based routing | IP packets, routers |
| 2 | Data Link | Organizes packet delivery within a single network | Switches, NICs, NCP/HDLC/SDLC |
| 1 | Physical | Raw hardware transmission — converts data to 0s and 1s | Hubs, modems, cabling |

*(Security/GRC note: identifying *which layer* an incident occurred at is central to triage during incident response. From an audit perspective, this model is also useful for identifying which layer's controls are weak or missing.)*

---

## 5. Components of Network Layer Communication (IP Packets in Depth)

**Role of the Network Layer (L3)**: Organizes addressing and delivery of packets from host to destination, hopping router to router until reaching the destination network's IP address. The destination IP is stored in the packet header and logged in routing tables along the path.

- IP Packet (TCP) / Datagram (UDP) — same concept, different name depending on protocol.

**IPv4 packet = Header (20–60 bytes) + Data (up to 65,535 bytes)**

| Field | Role |
|---|---|
| Version | Indicates which IP protocol version is used |
| HLEN | Header length — marks where the header ends and data begins |
| Type of Service (ToS) | Gives routers packet-priority information (QoS) |
| Total Length | Total packet length (header + data) |
| Identification | Unique ID used to reassemble fragmented packets |
| Flags | Indicates whether the packet is fragmented and if more fragments follow |
| Fragmentation Offset | Indicates where a fragment belongs in the original packet |
| **TTL** | Prevents infinite routing loops — decremented by 1 at each router; discarded + ICMP Time Exceeded sent when it hits 0 |
| Protocol | Tells the receiving device which protocol the data section uses |
| Header Checksum | Detects header corruption in transit; corrupted packets are discarded |
| Source/Destination IP | Sending/receiving device addresses |
| Options | Security options applied when HLEN > 5 |

*(Security note: abnormal TTL values or checksum mismatches can be indicators of network anomalies — worth checking during SOC log analysis.)*

**IPv4 vs. IPv6**

| | IPv4 | IPv6 |
|---|---|---|
| Format | 4 decimal numbers (e.g., 198.51.100.0) | 8 hexadecimal groups (e.g., 2002:0db8::ff21:0023:1234) |
| Size | 4 bytes, ~4.3 billion addresses | 16 bytes, ~340 undecillion addresses |
| Header | Includes IHL/Identification/Flags | Simpler — introduces the Flow Label field instead |
| Background | — | Developed to solve IPv4 address exhaustion |

---

## 6. Quiz Review (Consolidated)

### Concept-check items

- **Connecting an entire city → WAN** (LAN covers a smaller area)
- **Broadcasting to every computer → Hub** (repeats data to every port, like a radio tower)
- **Three benefits of a Switch**: controls traffic flow / improves network performance / delivers data only to the intended destination (❌ "automatically installs device-protection software" is not a switch function)
- **Using internet-hosted servers, apps, and network services = Cloud Computing**
- **IP packet header contents = sender IP + destination MAC + protocol to use** (routing metadata, not the message body)
- **TCP/IP and OSI share**: they both illustrate data transmission between systems / both define networking standards divided into layers / both include an application and transport layer (❌ "both have 7 layers" is false — only OSI has 7)
- **TCP = an internet communication protocol/convention** (not a software app or a unique address)
- **Port = a software-based location that organizes data sending/receiving between devices**
- **File transfer/email protocols (FTP, SMTP) live in the Application Layer**
- **An IP address identifies a device's "location"**
- **Example IPv4 address**: `172.16.254.1` (four decimal numbers, 0–255, dot-separated) — distinct from IPv6, port numbers, and MAC addresses
- **A switch uses a MAC address table to deliver packets to the correct device**
- **Traffic path**: computer → router → modem → internet
- **Connecting specific devices on a local network by sending/receiving data between them = Switch**
- **Purpose of the protocol number = tells the receiving device what to do with the packet's information**
- **127.0.0.1 = an IPv4 address** (loopback address)
- **Port used for large file transfers = 20** (FTP data port)
- **File transfer/email handling layer = Layer 4, Application**
- **Valid IPv6 format**: 8 hexadecimal groups separated by single colons, "::" used at most once, each group up to 4 hex digits → `fda2:7360:1e5b:e8f5:a69f:c8bd:1b3e:2578` is valid (other options were invalid due to repeated "::", too many groups, or invalid hex characters like g/h/j)

### ✅ Confirmed — Reasons a Security Professional Would Use a CSP

- **Question**: What are valid reasons a security professional might choose to use a CSP?
- **Correct answers (confirmed)**:
  1. A CSP offers processing power that is only paid for as needed.
  2. CSP remote servers allow web applications to be accessed from any location.
  3. A CSP provides business analytics to monitor web traffic and sales.
- **Incorrect option**: "CSP services do not require any additional cloud security measures" — false; cloud environments still require dedicated security controls under the shared responsibility model.

### ❌ Error Log — Public vs. Private IP Address

- **Question**: What type of address is assigned by an ISP and connected to a geographic location?
- **My initial answer**: Private IP address (incorrect)
- **Correct answer**: Public IP address
- **Why I got it wrong**: I associated "Private IP" too strongly with "local-network-only" and missed that a **Public IP is the one assigned by the ISP and tied to geographic location**. Also newly noted: all devices on the same LAN share a single public-facing address via NAT (network address translation) or a forwarding proxy.
- **Corrected understanding**: Public IP = externally visible, ISP-assigned, tied to geographic location / Private IP = local-network-only, not geographically tied.

---

*Course 3/9: Network-Security*
*Google Cybersecurity Professional Certificate*
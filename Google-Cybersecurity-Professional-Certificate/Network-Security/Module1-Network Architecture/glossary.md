# Module 1 - Network Architecture: Glossary

## Core Networking Terms

| Term | Definition | In Practice |
|---|---|---|
| Network | A group of connected devices | — |
| Network Device | Hardware that maintains and routes information/services for network users | Routers, switches, hubs, modems, firewalls, WAPs |
| Data Packet | The basic unit of information that travels between devices on a network | Carries both header (routing metadata) and data (message content) |
| Bandwidth | Maximum data transmission capacity of a network, measured in bits per second | Determines how much traffic a link can handle before congestion |
| Speed | The rate at which a device sends/receives data, measured in bits per second | — |
| LAN (Local Area Network) | A network spanning a small area — an office, school, or home | — |
| WAN (Wide Area Network) | A network spanning a large geographic area — a city, state, or country | Connecting an entire city requires a WAN, not a LAN |

## Network Devices

| Term | Definition | In Practice |
|---|---|---|
| Firewall | A security device that monitors and restricts inbound/outbound network traffic | The first line of defense — not a complete defense on its own; sits between trusted internal and untrusted external networks |
| Server | Provides information/services to client devices in the client-server model | DNS, file, and mail servers are common examples |
| Hub | Broadcasts incoming data to every device on the network | Vulnerable to eavesdropping — largely replaced by switches on modern networks |
| Switch | Connects specific devices on a network by directing data only to its intended destination | Uses a MAC address table; improves both performance and security |
| Router | Connects multiple networks together and routes traffic based on destination IP address | Can include built-in firewall functionality |
| Modem | Connects a router to the internet, bringing connectivity to the LAN | Converts ISP signals into a locally usable format |
| Wireless Access Point (WAP) | Sends/receives digital signals over radio waves to create a wireless network | Uses Wi-Fi protocols to relay data to routers/switches |

## Addressing

| Term | Definition | In Practice |
|---|---|---|
| IP (Internet Protocol) | Standards used for routing and addressing data packets between devices on a network | Works with TCP/UDP to deliver packets to the correct service |
| IP Address | A unique string that identifies the location of a device on the internet | — |
| IPv4 | 32-bit address format written as four decimal numbers (0–255) separated by dots | ~4.3 billion possible addresses (e.g., `172.16.254.1`) |
| IPv6 | 128-bit address format written as eight hexadecimal groups separated by colons | Developed to solve IPv4 address exhaustion; ~340 undecillion possible addresses |
| Public IP Address | An address assigned by an ISP and tied to a geographic location | Shared by all devices on a LAN via NAT |
| Private IP Address | An address used only within a local network | Not geographically tied; not visible externally |
| NAT (Network Address Translation) | Translates multiple private IPs on a LAN into a single shared public IP | Allows an entire local network to share one ISP-assigned address |
| MAC Address | A unique alphanumeric identifier assigned to each physical device on a network | Used by switches to forward packets correctly |
| Port | A software-based location that organizes the sending/receiving of data between devices | Identifies which service on a device should receive the traffic |

## TCP/IP Model & Protocols

| Term | Definition | In Practice |
|---|---|---|
| TCP/IP Model | A four-layer framework for visualizing how data is organized and transmitted across a network | Network Access → Internet → Transport → Application |
| TCP (Transmission Control Protocol) | A connection-oriented protocol that allows two devices to form a connection and reliably stream data | Includes a destination port number in its header; retransmits lost/corrupt data |
| UDP (User Datagram Protocol) | A connectionless protocol that transmits data without first establishing a connection | Used for performance-sensitive, real-time applications like video streaming |
| ARP (Address Resolution Protocol) | Maps IP addresses to MAC addresses for communication within a local network | Operates at the Network Access Layer |
| ICMP (Internet Control Message Protocol) | Shares error information and status updates about data packets | Used for troubleshooting network connectivity issues |
| Datagram | A unit of data transmitted over UDP | Functionally equivalent to a "packet" in TCP terminology |

## OSI Model (7 Layers)

| Term | Definition | In Practice |
|---|---|---|
| OSI Model | A standardized concept describing the seven layers computers use to communicate over a network | Application → Presentation → Session → Transport → Network → Data Link → Physical |
| Presentation Layer | Handles data format translation and encryption between sending/receiving systems | SSL encryption (core of HTTPS) operates here |
| Session Layer | Establishes, maintains, and terminates connections between two devices | Handles authentication, reconnection, and checkpoints during transfer |
| Data Link Layer | Organizes sending/receiving of packets within a single network | Home to switches and network interface cards (NICs) |
| Physical Layer | The physical hardware layer that transmits raw 0/1 signal data | Hubs, modems, cables, and wiring |
| SSL (Secure Sockets Layer) | A protocol that encrypts data between web servers and browsers | Underlies HTTPS; operates at the Presentation Layer |
| Segmentation | Dividing a large data transmission into smaller pieces for easier transport | Performed at the Transport Layer; reassembled at the destination |

## IPv4 Packet Structure

| Term | Definition | In Practice |
|---|---|---|
| IPv4 Header | The 20–60 byte portion of an IPv4 packet containing routing information | Distinct from the data section, which carries the actual message |
| TTL (Time to Live) | A counter that prevents packets from being routed indefinitely | Decremented at each router hop; discarded and reported via ICMP when it reaches zero |
| Header Checksum | A value used to detect corruption of the IP header in transit | Corrupted packets are discarded |
| Fragmentation | Splitting an oversized IP packet into smaller pieces to fit network limits | Identification, Flags, and Fragmentation Offset fields manage reassembly |
| Flow Label | An IPv6 header field indicating a packet requires special handling by routers | Not present in IPv4 headers |

## Cloud Computing

| Term | Definition | In Practice |
|---|---|---|
| Cloud Computing | Using remote servers, applications, and network services hosted on the internet instead of on local physical devices | Delivered by a Cloud Service Provider (CSP) |
| Cloud Network | A collection of servers/computers storing resources and data in remote data centers, accessible via the internet | — |
| CSP (Cloud Service Provider) | A company that owns large data centers and sells compute, storage, and networking services | AWS, Azure, GCP are common examples |
| SaaS (Software as a Service) | Ready-to-use software hosted and operated remotely by the CSP | Requires no hosting or maintenance by the customer |
| IaaS (Infrastructure as a Service) | Virtual computing resources (compute, storage) configured remotely via API/console | Existing applications can be migrated with minimal changes |
| PaaS (Platform as a Service) | Development tools and platforms for building custom applications | Aimed at application developers |
| Hybrid Cloud | An environment combining CSP services with on-premise infrastructure | Most organizations use this model for cost savings and control |
| Multi-Cloud | An environment using two or more CSPs | — |
| SDN (Software-Defined Network) | A network built from virtualized devices and services rather than physical hardware | Provides virtual switches, routers, and firewalls hosted at the CSP's data center |

## Security Practices

| Term | Definition | In Practice |
|---|---|---|
| Packet Sniffing | The practice of capturing and inspecting data packets traveling across a network | Used both defensively (monitoring) and offensively (eavesdropping) |
| Routing Table | A stored record of destination IP addresses used to determine packet paths | Updated as packets travel along their route |

---

*Course 3/9: Network-Security*
*Google Cybersecurity Professional Certificate*
# Module 3 - Secure Against Network Intrusions: Glossary

## Network Intrusion Attacks

| Term | Definition | In Practice |
|---|---|---|
| Packet Sniffing | The practice of capturing and inspecting network traffic | Used for both network monitoring and malicious eavesdropping |
| Passive Packet Sniffing | Reading packets in transit without altering them | Common on hub-based networks |
| Active Packet Sniffing | Capturing and manipulating packets in transit | Can redirect traffic or modify packet contents |
| IP Spoofing | Falsifying the source IP address of a packet | Used to impersonate trusted systems |
| On-Path Attack | Intercepting communications between trusted devices | Can capture credentials or modify data |
| Replay Attack | Re-sending previously captured network traffic | Used to exploit valid communications |
| Smurf Attack | An attack combining IP spoofing with ICMP flooding | Generates excessive responses to overwhelm a target |
| Backdoor | A hidden method that bypasses normal authentication controls | May provide persistent system access |

## Denial of Service Attacks

| Term | Definition | In Practice |
|---|---|---|
| DoS (Denial of Service) | An attack that exhausts network or server resources | Prevents legitimate users from accessing services |
| DDoS (Distributed Denial of Service) | A DoS attack launched from multiple systems | Often coordinated through a botnet |
| SYN Flood Attack | A DoS attack that abuses the TCP handshake process | Consumes connection resources on a server |
| ICMP Flood | A DoS attack using repeated ICMP requests | Can overwhelm network bandwidth |
| Ping of Death | A DoS attack using oversized ICMP packets | May cause system instability or crashes |

## Traffic Analysis & Monitoring

| Term | Definition | In Practice |
|---|---|---|
| Network Protocol Analyzer | A tool used to capture and inspect network traffic | Helps investigate suspicious activity |
| Packet Capture | The collection of network packets for analysis | Often used during incident investigations |
| Traffic Analysis | The process of examining network communications | Helps identify abnormal behavior |
| tcpdump | A command-line packet analysis tool | Common in Linux and Unix environments |
| Wireshark | A graphical packet analysis tool | Widely used for packet inspection |

## TCP/IP Concepts

| Term | Definition | In Practice |
|---|---|---|
| TCP Three-Way Handshake | The process used to establish a TCP connection | SYN → SYN-ACK → ACK |
| SYN Packet | A request to initiate a TCP connection | First step of the handshake |
| SYN-ACK Packet | A response accepting a connection request | Second step of the handshake |
| ACK Packet | A confirmation packet completing the connection | Final step of the handshake |
| RST Packet | A packet used to terminate or reject a connection | Indicates a failed connection attempt |

## Infrastructure & Security

| Term | Definition | In Practice |
|---|---|---|
| DNS (Domain Name System) | A service that translates domain names into IP addresses | Required to access websites by name |
| Botnet | A group of malware-infected devices controlled remotely | Frequently used in DDoS attacks |
| Bot-Herder | The attacker responsible for controlling a botnet | Coordinates attack activity |
| VPN (Virtual Private Network) | An encrypted network connection | Helps protect data in transit |
| TLS (Transport Layer Security) | A protocol used to encrypt network communications | Protects against interception attacks |
| Incident Report | A document used to record and analyze security incidents | Supports investigation and response activities |
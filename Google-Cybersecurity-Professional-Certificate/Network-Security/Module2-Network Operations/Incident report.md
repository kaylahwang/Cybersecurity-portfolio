# Incident Report: Website Outage — DNS Resolution Failure

**Type:** Network Traffic Analysis (tcpdump packet capture)
**Role:** Cybersecurity Analyst (IT services provider, client-facing incident)
**Tools:** tcpdump, protocol analysis (UDP / DNS / ICMP)

---

## Summary

Customers of a client company reported they could not reach `www.yummyrecipesforme.com`, receiving a **"destination port unreachable"** error. Packet capture and protocol analysis identified the root cause as a **failed DNS resolution due to UDP port 53 being unreachable** on the DNS server — meaning the browser could never obtain the site's IP address, so the connection never got as far as the web server itself.

---

## Timeline

| Time | Event |
|---|---|
| 13:24:32.192571 (1:24 p.m.) | Incident occurs / first logged in capture |
| Same day | Multiple customers report inability to access the site, seeing "destination port unreachable" |
| Same day | Analyst reproduces the issue directly, confirms the same error |
| Same day | Analyst captures live traffic with `tcpdump` while reloading the page |
| Same day | Issue escalated to security engineers for remediation; analysis handed off with findings below |

---

## Investigation Steps

1. **Reproduced the customer-reported issue** by visiting the site directly and confirming the same "destination port unreachable" error.
2. **Captured live traffic** using `tcpdump` while reloading the page, to observe exactly what the browser was sending and receiving.
3. **Isolated the failing exchange** in the capture: an outbound UDP request to the DNS server, followed by an ICMP error response instead of a normal DNS reply.
4. **Cross-referenced the port number** (53) against known service assignments to confirm it belonged to DNS, ruling out a web-server-layer issue.

---

## Technical Analysis

**What should have happened:** the browser sends a UDP query to the DNS server (port 53) asking for the IP address behind `www.yummyrecipesforme.com`. The DNS server should reply with that IP address, after which the browser proceeds to make the actual HTTPS request to the web server.

**What actually happened:** the DNS query went out over UDP as expected, but instead of a DNS answer, the browser received an **ICMP error message: `udp port 53 unreachable`**. This means the packet reached the destination host, but nothing was listening on port 53 to answer it — the DNS service itself was not responding.

Because port 53 is exclusively associated with DNS traffic, this pinpoints the failure specifically to **DNS service availability**, not the web server, not the client's network, and not general internet connectivity (the ICMP response itself proves the network path was working — a host on the other end *did* respond, just with a rejection rather than a valid answer).

**Why this breaks the whole site, not just DNS lookups:** without a resolved IP address, the browser has nowhere to send the subsequent HTTPS request. The "destination port unreachable" error customers saw is a downstream symptom of a DNS-layer failure, not a web-server-layer failure — an important distinction for scoping the incident correctly and directing the fix to the right team/system.

---

## Root Cause (Assessed)

The DNS service on UDP port 53 was **unavailable or unreachable**, preventing name resolution and blocking all downstream access to the website — regardless of whether the web server itself was healthy.

**Two candidate explanations, to be confirmed in follow-up:**
- The DNS server process itself was down or misconfigured.
- Traffic to port 53 was being blocked at the firewall (e.g., a recent rule change).

---

## Recommended Next Steps

1. Check whether the DNS service is actually running on the target server (process status, error logs).
2. Review recent firewall rule changes for anything affecting inbound/outbound UDP port 53.
3. If the DNS server is healthy and reachable internally, test port 53 specifically from outside the firewall to isolate a network-layer block from a service-layer failure.
4. Once resolved, re-run the same `tcpdump` capture to confirm a normal DNS response (rather than an ICMP error) is returned.

---

## Skills Demonstrated

- Reading and interpreting raw `tcpdump` output, including source/destination IPs, protocol type, and ICMP error codes
- Mapping a port number (53) to its associated service to correctly scope an incident
- Distinguishing between a DNS-layer failure and a web-server-layer failure from traffic evidence alone, rather than assumption
- Structuring findings into a decision-ready incident report: what happened, what's confirmed, what's still hypothesis, and what to check next

**Relevance to GRC / SOC work:** this is the same reasoning pattern used in control-gap analysis and audit findings — separate *confirmed fact* (DNS query failed, ICMP shows why) from *root cause hypothesis* (DoS vs. misconfiguration), and always leave a clear, testable next step rather than a guess presented as a conclusion.

---

*Course 3: Networks and Network Security*
*Google Cybersecurity Professional Certificate*
# Elevate-lab-Task3


# Task 3: Networking Basics for Cyber Security

## Tool Used
- **Wireshark**

## PCAP File
- `dos1.pcap`

---

## Basic Networking Concepts (Observed from PCAP)

### IP Address
- IP addresses identify devices on the network.
- In `dos1.pcap`, one destination IP receives a very large number of packets.
- This indicates a single target system being attacked.

### MAC Address
- MAC addresses appear in Ethernet frames.
- Source MAC addresses may repeat or appear spoofed in attack traffic.

### TCP
- TCP packets are visible with flags such as SYN.
- Many TCP connections are initiated but not completed.

### UDP
- Some DoS attacks use UDP because it is faster and connectionless.
- If present, UDP packets appear without any handshake process.

### DNS
- DNS packets, if present, show domain name lookups in plain text.

---

## Capturing Live Network Traffic

Since a PCAP file is already provided:
- Live traffic capture was not performed.
- The PCAP represents traffic captured earlier during a network event.
- This method is commonly used in network forensics and incident analysis.

**Observation:**  
The PCAP contains abnormal traffic rather than normal user browsing activity.

---

## Filtering Packets by Protocol

### TCP Filter

**Observation:**
- Large number of TCP packets
- Many SYN packets
- Very few completed TCP connections

### DNS Filter

**Observation:**
- Domain names are visible in plain text
- Repeated queries may indicate automated or malicious behavior

### HTTP Filter

**Observation:**
- Little or no normal HTTP browsing traffic
- Confirms that the traffic is attack-focused rather than user-focused

---

## Three-Way TCP Handshake

### Normal TCP Handshake
1. SYN  
2. SYN-ACK  
3. ACK  

### Observation in `dos1.pcap`
- Many SYN packets are sent
- Very few SYN-ACK responses are received
- Almost no ACK packets are observed

**Conclusion:**  
The TCP handshake is intentionally left incomplete, which is a common technique used in Denial of Service (DoS) attacks.

---

## Plain-text vs Encrypted Traffic

### Plain-text Traffic
- DNS queries with readable domain names
- TCP headers are fully visible

### Encrypted Traffic
- No meaningful HTTPS payloads observed
- Payload data is empty or irrelevant

**Key Insight:**  
DoS attacks focus on overwhelming the target with traffic volume rather than stealing or reading data.

---

## DNS Queries and Analysis

### Observations
- DNS packets may show repeated domain lookups
- Queries are visible in readable text format
- DNS commonly uses UDP protocol

### Security Meaning
- Repeated DNS queries can indicate DNS flooding or amplification attacks.

---

## Saving Packet Captures

- The network traffic is saved as `dos1.pcap`
- PCAP files preserve packet structure and timestamps
- These files are used for:
  - Attack investigation
  - Evidence collection
  - Training and learning purposes

---

## Final Observations

- The network traffic captured is abnormal.
- A single system is targeted with excessive packets.
- TCP connections are repeatedly initiated but not completed.
- Traffic behavior is automated, not human-driven.
- The observed pattern matches a **Denial of Service (DoS) attack**.

---

## Final Outcome

- Gained understanding of network traffic analysis using Wireshark.
- Learned how to identify abnormal traffic patterns.
- Built foundational skills in network forensics and cybersecurity monitoring.


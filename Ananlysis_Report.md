# Network Traffic Analysis Report

## Objective
To analyze captured network traffic using Wireshark and identify abnormal behavior related to cybersecurity threats.

---

## Tool Used
- **Wireshark**
- **PCAP file:** `dos1.pcap`

---

## Traffic Overview
The packet capture shows a very high volume of repetitive network traffic targeting a single destination system. The traffic pattern is abnormal and does not resemble normal user activity.

---

## Protocol Analysis

### TCP
- Large number of SYN packets observed.
- Connections are initiated but not completed.

### UDP
- Present in limited cases.
- No session establishment observed.

### DNS
- Repeated DNS queries resolving the same destination.
- Indicates preparatory or supporting activity for the attack.

---

## TCP Handshake Analysis
Most TCP connections fail to complete the three-way handshake (SYN, SYN-ACK, ACK).  
This behavior suggests an attempt to exhaust server resources by keeping connections half-open.

---

## Security Findings
- Traffic appears automated.
- Packet frequency is extremely high.
- Communication is largely one-sided.
- Behavior is consistent with a Denial of Service (DoS) attack.

---

## Conclusion
The analyzed PCAP file clearly demonstrates a Denial of Service attack pattern.  
Wireshark analysis helps identify such attacks by examining packet volume, protocol behavior, and TCP connection patterns.

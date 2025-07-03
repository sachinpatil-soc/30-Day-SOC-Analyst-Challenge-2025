
🚀 Day#6: Wireshark Basics – ICMP Protocol Analysis

🎯 Objective

The objective of this lab is to help, understand and analyse ICMP (Internet Control Message Protocol) packets using Wireshark. will learn to identify echo requests/replies, interpret ICMP packet fields, and apply relevant filters for investigation.


🛠️ Lab Setup

System Requirements

Operating System: Windows 10/11 (or Linux/macOS)
Software: Wireshark (latest version)
Files Needed

ICMP is a Layer 3 protocol used for sending error messages and operational information. The most common ICMP messages include Echo Request (Type 8) and Echo Reply (Type 0).

Key ICMP Fields:

Field Name	Description
Type	Defines the ICMP message type
Code	Provides further detail for the type
Checksum	Error-checking for header
Identifier	Helps match requests and replies
Sequence No.	Sequence of the request/reply
Data	Optional payload
🔍 Most Common ICMP Display Filters

Use these filters in Wireshark’s Display Filter bar:

Filter	Description
icmp	Show all ICMP traffic
icmp.type == 8	Show Echo Requests (ping)
icmp.type == 0	Show Echo Replies
icmp.code == 3	Destination unreachable
ip.addr == 192.168.1.10	ICMP traffic from/to specific host
✅ Conclusion

ICMP is a fundamental protocol for network troubleshooting.
Wireshark helps visualise ICMP packet flow and structure.
Understanding ICMP helps detect network scanning, ping sweeps, and unreachable hosts.
📸 Submission

Submit a screenshot showing:

ICMP Echo Request and Echo Reply packets
# 30-Day-SOC-Analyst-Challenge-2025
This repository documents my progress through a 30-day hands-on challenge, designed to build and showcase essential SOC Analyst skills for job readiness. Each day features a focused lab or task to deepen understanding and practical expertise in cybersecurity operations.

# 🚀 Day#07: Wireshark Basics – TCP Protocol Analysis

## 🎯 Objective
The objective of this lab is to analysing TCP (Transmission Control Protocol) traffic using Wireshark. Will learn how TCP establishes connections, the 3-way handshake process, and how to interpret common TCP fields and flags.



## 🛠️ Lab Setup

## System Requirements
Operating System: Windows 10/11 (or Linux/macOS)
Software: Wireshark (latest version)
Files Needed


## 📘 TCP Packet Structure and Fields
TCP is a Layer 4 (Transport Layer) protocol that ensures reliable, ordered, and error-checked delivery of data between applications.

### Key TCP Fields:
Field Name	Description
Source Port	Sender’s port number
Destination Port	Receiver’s port number
Sequence Number	Number of the first byte in the segment
Acknowledgment No	Confirms received data
Flags	Control bits (SYN, ACK, FIN, RST, PSH, URG)
Window Size	Buffer size available
Checksum	Error-checking field


## 🔍 Most Common TCP Display Filters

### Use these filters in Wireshark’s Display Filter bar:
Filter	Description
tcp	Show all TCP packets
tcp.flags.syn == 1	Show SYN packets (start of connection)
tcp.flags.fin == 1	Show FIN packets (end of connection)
tcp.port == 80	Show TCP packets on port 80
ip.addr == 192.168.1.1	TCP traffic to/from a specific host


## ✅ Conclusion

TCP ensures reliable and ordered data delivery through its 3-way handshake and flow control.
Understanding TCP flags is essential for:
Connection state tracking
Troubleshooting dropped or reset connections
Detecting scanning and abnormal behavior (e.g., RST floods)

## Submission
Submit a screenshot showing:
### Show all TCP packets
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/7dd1d0bb2934656d1f1c8e92a0e5d877857e8c47/TCP.png)


### Show SYN packets (start of connection)
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/7dd1d0bb2934656d1f1c8e92a0e5d877857e8c47/syn-flag.png)


### Show FIN packets (end of connection)
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/7dd1d0bb2934656d1f1c8e92a0e5d877857e8c47/Fin-flag.png)


### TCP traffic to/from a specific host
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/7dd1d0bb2934656d1f1c8e92a0e5d877857e8c47/host-traffic.png)

# 30-Day-SOC-Analyst-Challenge-2025
This repository documents my progress through a 30-day hands-on challenge, designed to build and showcase essential SOC Analyst skills for job readiness. Each day features a focused lab or task to deepen understanding and practical expertise in cybersecurity operations.

# 🚀 Day#9: Wireshark Basics – TLS Protocol Analysis

## 🎯 Objective
The objective of this lab is to analyse TLS (Transport Layer Security) traffic using Wireshark. will explore how TLS secures data over the network, understand key handshake messages, and identify crucial metadata such as server names and certificate details. This analysis is vital for a SOC Analyst to identify potential security anomalies or misconfigurations.

## 🛠️ Lab Setup

### System Requirements

Operating System: Windows 10/11 (or Linux/macOS)
Software: Wireshark (latest version recommended)

## 📘 TLS Packet Structure and Fields
TLS is a cryptographic protocol that provides secure communication over the internet. It operates over TCP, commonly on port 443 (for HTTPS), but is also used in other secure protocols like FTPS and SMTPS. Understanding the TLS handshake is fundamental for network security analysis.

### Key TLS Handshake Messages:
| Message Type                     | Description                                      |
| :------------------------- | :----------------------------------------------- |
| `Client Hello`                  | Client initiates secure connection, offers cipher suites                          |
| `Server Hello`                       | Server selects cipher and provides certificate |
| `Certificate `                        | Server provides digital certificate (X.509)     |
| `Key Exchange`                  | Client and server exchange keys for session|
| `Finished`                               | Secure session begins          |



## 🔍 Most Common TLS Display Filters

Use these filters in Wireshark’s Display Filter bar to analyze TLS traffic effectively:

| Filter                     | Description                                      |
| :------------------------- | :----------------------------------------------- |
| `tls`                      | Show all TLS traffic                             |
| `tcp.port == 443`          | TLS over HTTPS (standard port)                   |
| `tls.handshake.type == 1`  | Client Hello messages (start of handshake)       |
| `tls.handshake.type == 2`  | Server Hello messages (response to Client Hello) |
| `tls.record.version == 0x0303` | TLS 1.2 traffic (specific version)             |
| `tls.record.version == 0x0304` | TLS 1.3 traffic (specific version)             |

## ✅ Conclusion	
- TLS secures communication using encryption, making network traffic unreadable to unauthorised parties without the proper keys.
- Wireshark cannot decrypt encrypted TLS traffic by default (without pre-shared keys or private keys).
- Wireshark can still reveal crucial metadata such as:
- Server Name Indication (SNI)
- Certificate chain details
- Negotiated TLS versions and cipher suites
- Analysing TLS metadata helps SOC Analysts detect:
- Use of outdated or insecure TLS versions (e.g., TLS 1.0/1.1).
- Suspicious or self-signed certificates that might indicate a Man-in-the-Middle (MitM) attack.
- Malicious domains abusing encryption for command-and-control (C2) communication.


## 📸 Submission

### Submit a screenshot showing:

### All TLS traffic filtered in Wireshark.
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/c85fc6a476c020ae82423501169c0429b184ff63/Images/TLS.png)


### Client Hello messages filtered in Wireshark.
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/c85fc6a476c020ae82423501169c0429b184ff63/Images/hello-msg.png)



### TLS 1.2 traffic filtered in Wireshark.
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/c85fc6a476c020ae82423501169c0429b184ff63/Images/tlc-1.2-traffic.png)

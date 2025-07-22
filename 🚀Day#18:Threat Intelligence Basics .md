# 30-Day-SOC-Analyst-Challenge-2025
This repository documents my progress through a 30-day hands-on challenge, designed to build and showcase essential SOC Analyst skills for job readiness. Each day features a focused lab or task to deepen understanding and practical expertise in cybersecurity operations.

# 🚀Day#18:Threat Intelligence Basics

---

## 🎯 **Lab Objective**

The objective of this lab is to help learn how to extract Indicators of Compromise (IOCs) from a suspicious email and use **threat intelligence tools** to investigate their context and maliciousness.


---

## 📘 **What is Threat Intelligence?**

**Threat Intelligence (TI)** is information about threats, threat actors, and their tactics. It helps SOC analysts investigate alerts faster, make informed decisions, and respond to incidents more effectively.

### 💡 Types of Threat Intelligence:
- **Tactical:** IOCs like IPs, hashes, domains
- **Operational:** Info about campaigns, malware families
- **Strategic:** Big-picture trends, threat groups, geopolitical context

---

## 💼 **Scenario:**

While triaging a phishing alert, you discovered three suspicious indicators:

- IP Address: 18.188.148.80
- Domain: aaronthompson.ug
- File Hash(SHA256): d45a079c59c2860f9cf4578a8fc9f5fe8009cff8aaa83c572474d6bfe15ba95b

---

## 🛠️ **Lab Setup**

- 📩 **Download Email Sample:** [sample-1.eml](sandbox:/mnt/data/sample-1.eml)  
- 💻 **Tools Use:**
  - [VirusTotal](https://www.virustotal.com)
  - [AbuseIPDB](https://abuseipdb.com)
  - [URLScan.io](https://urlscan.io)
  - [AlienVault OTX](https://otx.alienvault.com/)
  - [ThreatFox](https://threatfox.abuse.ch/)
  - [MXToolbox Header Analyzer](https://mxtoolbox.com/EmailHeaders.aspx)


## 📥 **Tasks**

1. What is the type of the malicious file?
2. What country is this IP registered in?  
3. What malware name (if any) is associated with this file on VirusTotal?

---

## ✅ **Expected Outcome**

By completing this lab will:
- Understand how to extract IOCs from phishing emails  
- Use free tools to assess IPs, domains, and links  
- Gain confidence in making escalation decisions based on threat intelligence  
- Develop investigation habits like documentation and screenshot evidence


## 📸Submission

- 🔹 **Task-1-What is the type of the malicious file? **
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/57e74df86e768d2aeb856f6b02621a147b06501f/Images/7-zip.png)


- 🔹 **Task-2-What country is this IP registered in?**
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/57e74df86e768d2aeb856f6b02621a147b06501f/Images/ip-location.png)

- 🔹 **Task-3**-What malware name (if any) is associated with this file on VirusTotal?
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/57e74df86e768d2aeb856f6b02621a147b06501f/Images/malware-name.png)


# 30-Day-SOC-Analyst-Challenge-2025
This repository documents my progress through a 30-day hands-on challenge, designed to build and showcase essential SOC Analyst skills for job readiness. Each day features a focused lab or task to deepen understanding and practical expertise in cybersecurity operations.

# 🚀Day#14/ Splunk Basics – Zeek Connection Log Analysis


## 🎯 Objective

In this lab will:
- Learn how to upload and search Zeek connection logs in Splunk. 
- Find top clients, top servers, and most common services.
- Identify large traffic and long connections.


## 🖥️ Lab Setup

- ✅ Splunk: Already installed and accessible.
- ✅ Data Source: JSON-formatted Zeek-style connection logs.
- 🌐 Log File: Download and upload to Splunk using the steps below.


 <a href=""> 📥 Download Zeek Conn Log File </a>

## ⚙️ Steps to Upload Conn Log into Splunk

- Go to Splunk Web → Settings > Add Data.
- Choose Upload and select zeek_conn_logs.json.
- Set Source type: json or create a new one like zeek:conn.
- Index: Use main or create a new one called conn_lab.
- Complete the upload and check that logs are searchable.

## 🔍 Lab Tasks

#### Used the following SPL queries to complete each task:

### ✅Task 1: Find the Top 10 Client IPs (id.orig_h)

	•	index=sachin_patil sourcetype=“json”
	•	| stats count by id.orig_h
	•	| sort -count
	•	| head 10


### ✅Task 2: List Most Common Services

	•	index=sachin_patil sourcetype=“json”
	•	| stats count by service
	•	| sort -count

### ✅Task 3: Find Connections with Duration > 1 Second

	•	index=sachin_patil sourcetype=“json” duration>1
	•	table ts,” “id.orig_h,” “id.resp_h,” “service duration
	•	sort -duration


### ✅Task 4: Identify the Most Accessed Internal Servers

	•	sachin_patil sourcetype=“json”
	•	| stats count by “id.resp_h”
	•	| sort -count
	•	| head 10


## 📸 Submission

### Screenshot for each of the following:
### ✅Task 1: Find the Top 10 Client IPs (id.orig_h)
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/01ed4f00d16be25a94a20aa2a0ee1f48588ad73b/Images/zee_10%20Client%20IPs_1.png)

### ✅Task 2: List Most Common Services
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/01ed4f00d16be25a94a20aa2a0ee1f48588ad73b/Images/zee_sservices_2.png)

### ✅Task 3: Find Connections with Duration > 1 Second
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/01ed4f00d16be25a94a20aa2a0ee1f48588ad73b/Images/zee_duration%3E1_3.png)

### ✅Task 4: Identify the Most Accessed Internal Servers
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/01ed4f00d16be25a94a20aa2a0ee1f48588ad73b/Images/zee_Internal%20Servers_4.png)



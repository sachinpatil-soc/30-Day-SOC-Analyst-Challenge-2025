# 30-Day-SOC-Analyst-Challenge-2025
This repository documents my progress through a 30-day hands-on challenge, designed to build and showcase essential SOC Analyst skills for job readiness. Each day features a focused lab or task to deepen understanding and practical expertise in cybersecurity operations.

## 🚀 Day#11: Splunk Basics – DNS Log Analysis

## 🎯 Objective
In this lab will Learn how to ingest and analyze DNS logs in Splunk.
Understand how to extract useful information such as DNS query types, source hosts, and common destinations.
Practice building basic SPL (Search Processing Language) queries to investigate DNS activity.


## 🖥️ Lab Setup
- ✅ Splunk: Already installed and accessible.
- ✅ Data Source: JSON-formatted Zeek DNS logs.
- 🌐 Log File: Download the file below and place it in a directory accessible to Splunk for ingestion.
- 📥 Download sample dns file

## ⚙️ Steps to Upload DNS Log into Splunk
- Go to Splunk Web → Settings > Add Data.
- Choose Upload and select the file dns.log.
- Set Source type: json or create a custom source type dns.
- Index: Choose main or create a new index like dns_lab.
- Finish the upload and confirm indexing.


## 🔍 Lab Tasks

### Use SPL queries to answer the following:

✅Task 1: Identify the most frequently queried domain names

	•	index=dns_lab sourcetype=“json”
	•	stats count by query
	•	sort -count


✅Task 2: Find the most active user IPs generating DNS traffic

	•	index=dns_lab sourcetype=“json”
	•	| stats count by “id.orig_h”
	•	| sort -count


✅Task 3: Breakdown of DNS query types (A, AAAA, CNAME, PTR)

	•	index=dns_lab sourcetype=“json”
	•	| stats count by qtype



## 📸Submission

### Submit a screenshot of each of the following:

### SPL query and result for Task 1
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/07d5e554958a0cbf7925be19d81e828b4223dedf/Images/SPL_Query-task-1.png)


### SPL query and result for Task 2
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/07d5e554958a0cbf7925be19d81e828b4223dedf/Images/SPL-Query-task-2.png)


### SPL query and result for Task 3
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/07d5e554958a0cbf7925be19d81e828b4223dedf/Images/SPL-Query-task-3.png)

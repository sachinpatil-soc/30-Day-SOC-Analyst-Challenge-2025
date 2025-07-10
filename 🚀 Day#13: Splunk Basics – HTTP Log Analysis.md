# 30-Day-SOC-Analyst-Challenge-2025
This repository documents my progress through a 30-day hands-on challenge, designed to build and showcase essential SOC Analyst skills for job readiness. Each day features a focused lab or task to deepen understanding and practical expertise in cybersecurity operations.

# 🚀 Day#13/ Splunk Basics – HTTP Log Analysis

## 🎯 Objective
In this lab will Learn how to ingest and analyse HTTP logs using Splunk.
Detect client errors, server errors, and suspicious web activity.
Identify large file transfers and suspicious URI access attempts.

## 🖥️ Lab Setup


	•	Software Availability: Splunk is installed and accessible.
	•	Data Source: JSON-formatted Zeek-style HTTP logs.
	•	Data Ingestion: Log file needs to be downloaded and uploaded to Splunk.


## 📥 Download HTTP Log file

## ⚙️ Steps to Upload HTTP Log into Splunk

1. Go to Splunk Web → Settings > Add Data.
2. Choose Upload and select synthetic_zeek_http.json.
3. Set Source type: json or create a new one zeek:http.
4. Index: Choose main or create a new index like http_lab.
5. Finish the upload and confirm indexing.

## 🔍 Lab Tasks

### Use SPL queries to complete the following analysis:

### ✅ Task 1: Find the top 10 endpoints generating web traffic

	•	index=http_lab sourcetype=“json”
	•	| stats count by “id.orig_h”
	•	| sort -count
	•	| head 10

### ✅Task 2: Count the number of server errors (5xx) observed

	•	index=http_lab sourcetype="json" status_code>=500 status_code<600.
	•	| stats count as server_errors.

### ✅Task 3: Identify User-Agents associated with possible scripted attacks

	•	index=http_lab sourcetype="json" user_agent IN ("sqlmap/1.5.1", "curl/7.68.0", "python-requests/2.25.1", "botnet-checker/1.0")
	•	| stats count by user_agent
	
### ✅Task 4: Find large file transfers (greater than 500 KB)

  	•	index=http_lab sourcetype="json" resp_body_len>500000.
	•	table ts “id.orig_h” “id.resp_h” uri resp_body_len.
	•	sort -resp_body_len



## 📸Submission

### Submit a screenshot for each of the following:

### Your query and result for Task 1.
### Your query and result for Task 2.
### Your query and result for Task 3.
### Your query and result for Task 4.
### Your query and result for Task 5.

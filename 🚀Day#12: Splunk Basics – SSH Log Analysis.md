# 30-Day-SOC-Analyst-Challenge-2025
This repository documents my progress through a 30-day hands-on challenge, designed to build and showcase essential SOC Analyst skills for job readiness. Each day features a focused lab or task to deepen understanding and practical expertise in cybersecurity operations.

# 🚀Day#12: Splunk Basics – SSH Log Analysis

## 🎯 Objective
In this lab will Learn how to ingest and analyse SSH logs using Splunk.
Detect failed and successful SSH authentication attempts.
Identify unusual SSH activity that may indicate brute force or unauthorised access.


## 🖥️ Lab Setup
**Splunk:**
- Installation and accessibility confirmed.

**Data Source:**
- JSON-formatted Zeek-style SSH logs.

**Log File:**
- Download and upload to Splunk using the following steps:

## 📥 Download SSH Log file

## ⚙️ Steps to Upload SSH Log into Splunk
1. Open Splunk Web and navigate to Settings > Add Data.
2. Click on Upload and select  synthetic_zeek_ssh.json.
3. Choose the Source type as json or create a new one called zeek:ssh.
4. Select the Index as main or create a new one called ssh_lab.
5. Finish the upload and confirm that indexing is complete.


## 🔍 Lab Tasks

## Use SPL queries to complete the following analysis:

### ✅Task 1: List the top 10 endpoints with failed SSH login attempts,

		index=ssh_lab sourceType=“json”	auth_success=false
		| stats count by “id.orig_h”
		| sort -count
		| head 10



### ✅Task 2: Find the number of total SSH connections,

		index=ssh_lab sourcetype=“json”
		| stats count as total_ssh_connections


### ✅Task 3: Count all event types (successful, failed, no-auth, multiple-failed) seen in the logs

		index=ssh_lab sourcetype=“json”
		| stats count by event_type



## 📸Submission

### Submit a screenshot for each of the following:

### Your query and result for Task 1.
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/0e771627d4457365e890ed420c7bf971e4087ea5/Images/Days/failed%20SSH%20login%20attempts-1.png)


### Your query and result for Task 2.
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/0e771627d4457365e890ed420c7bf971e4087ea5/Images/Days/ssh-total-connection-2.png)

### Your query and result for Task 3.
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/0e771627d4457365e890ed420c7bf971e4087ea5/Images/Days/ssh-event-type-3.png)

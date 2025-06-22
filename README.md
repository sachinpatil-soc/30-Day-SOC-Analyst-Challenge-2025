# 30-Day-SOC-Analyst-Challenge-2025
"A 30-day hands-on challenge to develop and showcase SOC Analyst skills for job readiness.

🚀 Day 1: Introduction to Log Analysis

🧠 Objective
This lab introduces the foundational concepts of log analysis in cybersecurity. The goal is to understand how logs are generated, collected, and analyzed for security monitoring. As a future SOC Analyst, developing these skills is crucial for detecting suspicious activity and investigating incidents.

📌 What Is a Log?
A log is a record of events or activities on a system. These are vital for monitoring, diagnostics, and forensic analysis. Logs typically include:

Timestamp – When the event occurred
Event Description – What happened
Severity – Level of criticality (Information, Warning, Error, Critical)
Source – Origin of the event (User, Process, Service)
Logs are the eyes and ears of security operations.

🔬 Lab Task: Simulate and Detect Suspicious PowerShell Activity
💻 Environment

Operating Systems:
Windows 10/11 or Windows Server 2019/2022
Linux (Ubuntu or CentOS)
Tools Required:
Windows Event Viewer
PowerShell (pre-installed on Windows)

⚙️ Lab Setup – Windows
1️⃣ Enable Logging Features:

Open Group Policy Editor (gpedit.msc) and navigate to:
Computer Configuration → Administrative Templates → Windows Components → Windows PowerShell

Enable the following:

Module Logging
Script Block Logging
Script Execution Logging
2️⃣ Verify in Event Viewer:

Open Event Viewer (eventvwr.msc) and navigate to:
Applications and Services Logs → Microsoft → Windows → PowerShell → Operational

🔍 Step-by-Step: Simulate & Detect an Event
🛠️ Step 1: Simulate a Suspicious PowerShell Command

Run PowerShell as Administrator and execute:
Get-LocalUser | Select-Object Name, Enabled
This command lists local user accounts—behavior commonly seen during reconnaissance by attackers.

🕵️ Step 2: Detect the Event in Logs

In Event Viewer:

Go to PowerShell → Operational logs
Use Filter Current Log → Enter Event ID: 4104
Look for an event showing the execution of Get-LocalUser
📸 Take a screenshot of the event details.

✅ Conclusion
Why It Matters: Logs help security professionals detect, investigate, and respond to threats.
SOC Analyst Insight: Analysts rely on tools like Event Viewer to monitor real-time events and investigate suspicious behavior.
Skill Gained: Basic familiarity with Windows logging and detection of PowerShell events.

🚀 Day#2: Introduction to Log Analysis
🎯 Objective

The objective of this lab is to introduce the foundational concepts of log analysis in cybersecurity. Participants will learn how logs are generated, collected, analyzed, and leveraged for effective security monitoring. This lab will demonstrate how SOC Analysts use log data to detect security incidents on both Windows and Linux systems.

🧠 What is a Log?

A log is a chronological record of events or activities that occur on a system, application, or network device. Logs are indispensable for monitoring system behavior, detecting security incidents, debugging, and conducting forensic investigations. Key information typically captured in a log entry includes:

Timestamp: The exact date and time the event occurred.

Event Description: A concise summary of what happened.

Severity: The criticality level of the event (e.g., Critical, Error, Warning, Information).

Source: The origin of the event (e.g., User, Process, Service, IP Address).

🐧 Linux auth.log Example

Here’s an example of a failed SSH login attempt from a Linux auth.log:

Apr  7 10:42:15 ubuntu sshd[12345]: Failed password for invalid user admin from 192.168.1.100 port 54321 ssh2

Explanation of Log Components:

Apr 7 10:42:15 — Timestamp

ubuntu — Hostname

sshd[12345] — Service name and process ID

Failed password for invalid user admin — Event Description (failed login attempt)

from 192.168.1.100 — Source IP address

port 54321 — Source port

ssh2 — Protocol version

🌐 Common Log Sources

On Linux:

System Logs (/var/log/): Contains core system messages. Important files include:

/var/log/syslog (general system messages)

/var/log/auth.log (authentication attempts, e.g., SSH, sudo)

/var/log/kern.log (kernel-related messages)

Application Logs: Specific to applications, such as web server logs (/var/log/apache2/access.log), or database logs (/var/log/mysql/error.log).

On Windows:

Accessible via Event Viewer (eventvwr.msc), providing centralized access to:

System Logs: Records events related to operating system health and components.

Security Logs: Crucial for security, logging events like login attempts (successful/failed), permission changes, and audit policy modifications.

Application Logs: Contains events from installed applications.

PowerShell Logs: Logs detailed information about PowerShell command execution, including suspicious scripts (requires specific logging to be enabled).

👩‍💻 How Does a SOC Analyst Use Log Analysis?

Log analysis is a cornerstone of Security Operations Center (SOC) activities:

Incident Detection: SOC Analysts review logs to detect unusual or unauthorized activities, such as multiple failed login attempts, suspicious process executions, or anomalous network connections.

Forensics & Investigation: Logs provide an immutable timeline of events, essential for tracing back the actions taken by an attacker during or after a security incident.

Security Monitoring: Continuous, real-time log analysis helps in proactively identifying and responding to potential security threats.

Compliance & Auditing: Logs are vital for demonstrating adherence to regulatory standards (e.g., GDPR, HIPAA) and for internal auditing.

📊 Popular Tools for Log Analysis

While Event Viewer and grep/tail are basic tools, SOCs use more advanced platforms for large-scale log management:

ELK Stack (Elasticsearch, Logstash, Kibana): A powerful open-source suite for log collection, processing, storage, and visualization.

Splunk: A leading commercial solution for searching, analyzing, and visualizing machine-generated data, widely used in enterprise SOCs.

Graylog: An open-source log management platform offering centralized logging and analysis.

Wazuh: An open-source security monitoring platform that integrates host-based intrusion detection (HIDS), log analysis, and security analytics.

🧪 Lab Task: Simulating and Detecting Windows PowerShell Events

This hands-on task will guide you through generating a specific event in Windows and then locating it within the security logs.

Lab Setup

Systems: Windows 10/11 or Windows Server 2019/2022

Tools: Windows Event Viewer, PowerShell (pre-installed)

Preparation

To ensure detailed PowerShell logging for this lab, follow these steps:

Open Group Policy Editor: Press Win + R, type gpedit.msc, and press Enter.

Navigate to PowerShell Logging Settings: Go to Computer Configuration → Administrative Templates → Windows Components → Windows PowerShell.

Enable Logging Features: Ensure that the following policies are Enabled:

Module Logging

Script Block Logging

Script Execution

Verify Event Viewer Path: Familiarize yourself with the location where PowerShell operational logs are stored:

Applications and Services Logs → Microsoft → Windows → PowerShell → Operational.

⚔️ Step 1: Simulate a Suspicious PowerShell Command

To simulate an activity commonly performed during reconnaissance by attackers, open an elevated PowerShell session (Run as Administrator) and execute the following command:

Get-LocalUser | Select-Object Name, Enabled

Context: This command lists all local user accounts on the system. Attackers frequently use such enumeration techniques post-exploitation to gather information about potential targets or privilege escalation paths.

🔍 Step 2: Detect the Log in Windows Event Viewer

After executing the PowerShell command, verify its logging in Event Viewer:

Open Event Viewer: Press Win + R, type eventvwr.msc, and press Enter.

Navigate to: Applications and Services Logs → Microsoft → Windows → PowerShell → Operational.

Filter Current Log: Right-click on "Operational" and select Filter Current Log....

In the Event IDs: field, enter 4104 (This Event ID specifically logs PowerShell script block execution).

Click OK.

Look for an entry that clearly shows the execution of the Get-LocalUser command within the event details.

📸 Take a screenshot of the event details. This screenshot should clearly show the execution of Get-LocalUser command logged under Event ID 4104.
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/main/Windows-powershell.JPEG?raw=true) 

✅ Conclusion

Understanding Log Analysis: This lab reinforces that logs are crucial for detecting, investigating, and responding to security incidents. Through hands-on experience with Windows Event Viewer and an introduction to Linux log files, you can begin to monitor system activity and identify potential security issues.

SOC Analyst Role: Log analysis is a core competency for SOC Analysts, enabling them to detect threats, investigate incidents, and help ensure system compliance.

📸 Submission

Submit a screenshot of the log generated on the Windows machine, specifically showing the PowerShell Get-LocalUser command execution (Event ID 4104) in Event Viewer.


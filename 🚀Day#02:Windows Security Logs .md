# 30-Day-SOC-Analyst-Challenge-2025
This repository documents my progress through a 30-day hands-on challenge, designed to build and showcase essential SOC Analyst skills for job readiness. Each day features a focused lab or task to deepen understanding and practical expertise in cybersecurity operations.

# 🚀 Day#02: Log Analysis Basics – Windows Security Logs

## 🎯 Objective

The objective of this lab is to learn Windows Security Logs and provide hands-on experience in analysing these logs for security-related events. Will learn to explore and interpret various critical security logs, including login attempts, user account changes, and other system events that may indicate potential security threats.

## 🛠️ Lab Setup

## Requirements

System: Windows 10/11 or Windows Server 2019/2022

## Tools:

Windows Event Viewer (pre-installed)

PowerShell (pre-installed)

Privileges: Administrative Privileges (required to access and manage certain security logs)

## 🧠 What are Windows Security Logs?

Windows Security Logs contain vital records of security-related events occurring on the system. These logs are indispensable for monitoring security incidents, detecting unauthorized access, and auditing system changes. Key events tracked include:

Successful and Failed Login Attempts: Records users who successfully log in or fail to authenticate, providing crucial insights into access patterns.

Account Lockouts: Logs instances where a user account is locked out due to exceeding the maximum allowed number of incorrect login attempts.

Audit Policy Changes: Tracks modifications made to system audit settings and configurations, which could indicate attempts to hide malicious activity.

Group Membership Changes: Monitors alterations in user group memberships and associated privileges, signaling potential privilege escalation.

Privilege Escalation: Logs events where a user or process successfully gains elevated privileges on the system.

## 🔍 Understanding Event IDs in Security Logs

To effectively analyze Windows Security Logs, it's essential to understand common Event IDs. Here are some you will frequently encounter:

Event ID 4624: Successful Logon.

Event ID 4625: Failed Logon.

Event ID 4740: Account Lockout.

Event ID 4732: A user was added to a security-enabled local group.

Event ID 4672: Special privileges assigned to a new logon (often associated with privilege escalation).

## 🧪 Lab Task: Explore and Analyze Windows Security Logs

## ⚔️ Step 1: Simulate a Failed Login Attempt

To generate relevant log data, we will simulate a failed login attempt.

Create a Test User: First, create a test user, for example, "haxuser1", on your Windows machine (if you don't have a non-admin user already).

Simulate Failed Account Access: Open PowerShell as Administrator and execute the following command with an intentionally incorrect password:

net use \\127.0.0.1\IPC$ /user:haxuser1 WrongPassword

net use: A command used to connect to shared network resources.

\\127.0.0.1\IPC$: This refers to a special hidden administrative share on your local machine (127.0.0.1 is localhost). IPC$ is used for inter-process communication, particularly for authentication.

/user:haxuser1: Specifies the username to attempt authentication with.

WrongPassword: The intentionally incorrect password for the authentication attempt.

Alternatively: You can sign out of your current Windows account and attempt to sign in with the "haxuser1" account using an invalid password at the login screen.

## 🔍 Step 2: Detect the Log in Windows Event Viewer

After simulating the failed login, proceed to the Event Viewer to analyze the generated logs.

Open Event Viewer (run eventvwr.msc).

Navigate to: Windows Logs → Security.

Filter the Security Logs: Right-click on "Security" and select Filter Current Log....

In the Event IDs: field, enter 4625 (for Failed Logon events).

Click OK.

Look for entries that correspond to your simulated failed login attempt.



## 📸 Take a screenshot of the event details for Event ID 4625. Ensure the screenshot clearly shows:

Failed Login Attempt Details

User Name (haxuser1)

Logon Type

Source Network Address (should be 127.0.0.1 or your local machine's IP)

## ✅ Conclusion

Understanding Windows Security Logs: These logs are fundamental for identifying suspicious behavior such as unauthorized login attempts, privilege escalation, and critical system configuration changes.

## SOC Analyst Role: As a SOC Analyst, reviewing and analyzing these logs regularly is critical to detecting and responding to security incidents in real-time.

Threat Detection: By continuously monitoring for patterns like multiple failed logins, account lockouts, and privilege escalations, SOC Analysts can quickly detect and mitigate malicious activities on a network.


## 📸 Submission

Screenshots demonstrating successful log analysis for both successful and failed login attempts:

Event ID 4624 (Successful Login): A screenshot showing a successful login event from the Security logs.

![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/e74d7e17ca4fb65d6fca37346c0d2cba58a14fcd/windows-securty-logs-4624.JPEG)



Event ID 4625 (Failed Login): A screenshot showing a failed login attempt event (Event ID 4625) from the Security logs, explicitly highlighting the username, logon type, and source network address. 

![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/45038830a4e1d079a427b6b45100b10956b0be3a/Images/windows-securty-logs-4625.JPEG)

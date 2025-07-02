# 🚀 Day#3: Log Analysis Basics – Linux Auth Log


## 🎯Objective
The objective of this lab is to simulate an SSH brute force attack and demonstrate how to detect it using Linux authentication logs. This exercise will teach you how to identify multiple failed login attempts and analyze patterns to uncover brute force activity, a critical skill for any SOC Analyst.


## 🛠️ Lab Setup

## System Requirements   
	•      Attacker Machine: Kali Linux (or any Linux distribution with hydra installed)
	•      Target Machine: Ubuntu Linux Server (or any Debian-based Linux)
## Tools Needed
	•	hydra (on the attacker machine)
	•	openssh-server (ensure it's installed and running on the target machine)
	•	rsyslog (default logging service on most Linux distributions)
## Log Files
	•	/var/log/auth.log – Primary authentication log file (for Ubuntu/Debian-based systems)
	•	/var/log/secure – Equivalent authentication log file (for CentOS/RHEL-based systems)
 
## 📘 Preparation
Linux systems diligently log every authentication event, including both successful and failed SSH login attempts. Brute force attacks can be effectively identified by analyzing specific patterns within these logs, such as:
	•	Rapid failed login attempts originating from a single IP address.
	•	Repeated attempts with various usernames, particularly common or privileged accounts.
	•	A sudden successful login following a string of numerous failures (indicating a successful brute force).

 
## 🧠 What is an SSH Brute Force Attack?
An SSH brute force attack involves an attacker attempting to guess a user’s SSH password by systematically trying many combinations in rapid succession, typically using automated tools.
Why It’s Dangerous
	•	Full Shell Access: A successful brute force attack grants the attacker full command-line access to the target system.
	•	Lateral Movement & Malware: From there, attackers can pivot to other systems, install malware, exfiltrate sensitive data, or establish persistent access.
	•	Stealth: Without proper log monitoring and analysis, these attacks can often go unnoticed.

 
## 🛡️ Attack Patterns Detectable via Auth Logs
	•	Numerous consecutive failed password attempts from the same source IP address.
	•	Repeated login attempts targeting sensitive accounts (e.g., root, admin).
	•	A successful login entry immediately preceded by a high volume of failed attempts.
	•	Login attempts originating from suspicious, unknown, or geographically unusual IP addresses.

 
## What is Hydra?
Hydra is a powerful, fast, and open-source parallelized password-cracking tool used for brute-forcing login credentials across various network services.
	•	It supports over 50 protocols, including SSH, FTP, HTTP, SMB, and more.
	•	Common Use: Widely used in penetration testing to audit for weak passwords in network services.
	•	Basic Syntax: hydra -L users.txt -P passlist.txt <target_ip> <protocol>
	•	
	•	
	•	Single User/Pass: Use -l <username> for a single username and -p <password> for a single password.
	•	Verbose Output: Add -vV for detailed output during the attack.
	•	Threads: Use -t <number> (e.g., -t 4) to set the number of parallel tasks (threads).

 
## 🧪 Lab Task: Explore and Analyze Auth Logs for SSH Brute Force
## ⚔️ Step 1: Attack Simulation – Brute Force SSH using Hydra
⚠️ Important: Only perform this attack on systems you own or have explicit authorization to test.
	1	On the Attacker Machine (e.g., Kali Linux): Execute the hydra command to attempt a brute force attack against the target SSH service. Replace TARGET-IP with the actual IP address of your Ubuntu target server. # Example: Brute force 'root' user using rockyou.txt wordlist
	2	hydra -l root -P /usr/share/wordlists/rockyou.txt ssh://TARGET-IP
	3	
	4	 This command will systematically attempt various passwords for the root user on the SSH port.
	5	Verify SSH Service on the Target Machine: Ensure the SSH service (sshd) is active and running on your Ubuntu target server. sudo systemctl status ssh
	6	
	7	
## 🔍 Step 2: Detection and Analysis – Analyze Auth Logs
	1	Check for Failed Login Attempts: On the Target Machine, use grep to find entries indicating failed password attempts in the authentication log. sudo grep "Failed password" /var/log/auth.log
	2	
	3	
	4	Identify Attempted Usernames and Frequencies: To see which usernames were targeted and how many times, combine grep, awk, sort, and uniq. sudo grep "Failed password" /var/log/auth.log | awk '{print $(NF-5)}' | sort | uniq -c | sort -nr
	5	
	6	
	7	Watch Live Log Activity: Monitor the authentication log in real-time to see new entries as they appear (e.g., during another attack attempt). sudo tail -f /var/log/auth.log
	8	
	9	
## 🔍 What to Look For
	•	Volume: More than 20 failed attempts from the same IP address within a short timeframe (e.g., under 5 minutes).
	•	Targets: Repeated attempts against sensitive or default user accounts like root or admin.
	•	Success After Failures: A sudden successful login entry immediately following a high number of failed attempts.
 
## ✅ Conclusion
	•	Auth logs are vital for detecting brute force login attempts, serving as a primary source of evidence for such attacks.
	•	Identifying multiple failed attempts from a single IP is a strong and clear signal of a potential brute force attack.
	•	Combine log analysis with automated tools like fail2ban to automatically block repeat offenders and enhance your system's defensive posture.
 
## 📸 Submission Submit a screenshot showing:
        •       Multiple failed login entries originating from the same IP address.
	•       The username(s) that were attempted during the brute force attack.
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/91443d13e184d7d3e302adefa68e33b0e9d33c2e/Linux-Auth-Failed-log.png)
	

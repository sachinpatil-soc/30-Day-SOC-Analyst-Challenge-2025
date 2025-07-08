# 30-Day-SOC-Analyst-Challenge-2025
This repository documents my progress through a 30-day hands-on challenge, designed to build and showcase essential SOC Analyst skills for job readiness. Each day features a focused lab or task to deepen understanding and practical expertise in cybersecurity operations.

# 🚀 Day#10: Install and Configure Splunk

## Objective
The objective of this task is to install and configure Splunk on an Ubuntu machine. By completing this task, will have Splunk up and running to collect and analyze security logs.

## Lab Setup Requirements
System: Ubuntu 22.04 / 20.04 (Server or Desktop)
Tools Required:
Splunk Enterprise (Free version for local setup)
Terminal (Command Line Access)

### Steps to Install and Configure Splunk on Ubuntu
Step 1: Download Splunk

Open Terminal and download Splunk using wget:

wget -O splunk-9.3.0-51ccf43db5bd-linux-2.6-amd64.deb "https://download.splunk.com/products/splunk/releases/9.3.0/linux/splunk-9.3.0-51ccf43db5bd-linux-2.6-amd64.deb" ``` 2. Once downloaded, install Splunk:

sudo dpkg -i splunk-ubuntu.deb
Step 2: Enable Splunk as a Service

Move to the Splunk installation directory:
cd /opt/splunk/bin
Accept the license agreement and enable Splunk at boot:
sudo ./splunk enable boot-start --accept-license
Start Splunk:
sudo ./splunk start
When prompted, set up an admin username and password.
Step 3: Access Splunk Web Interface

Open a web browser and go to:
http://<your-server-ip>:8000
Log in with the admin credentials created earlier.

## Conclusion
✅ Successfully installed Splunk on an Ubuntu machine.
✅ Configured Splunk as a service and enabled auto-start.

## Submission
Share a screenshot of Splunk Web
![image alt](https://github.com/sachinpatil-soc/30-Day-SOC-Analyst-Challenge-2025/blob/f49d28d1b1ea19dd1a885e19ffc92a426ea42b96/Images/Splunk-enterprise.png)

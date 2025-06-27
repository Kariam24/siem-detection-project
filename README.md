📡 SIEM Detection Project
This project demonstrates hands-on detection engineering using Splunk and Sigma rules to identify suspicious activity across Windows and AWS environments. It focuses on two key threat scenarios:

Obfuscated PowerShell Execution (T1059.001)

AWS Reconnaissance via Describe API Calls (T1526, T1087)

By ingesting and analyzing Sysmon and AWS CloudTrail logs, I created actionable detections mapped to MITRE ATT&CK and deployed real-time alerts in Splunk.

📁 Folder Structure & Detection Rules
🔹 Detection 1: Obfuscated PowerShell (MITRE T1059.001)
Log Source: Sysmon

Technique: PowerShell Scripting (Encoded Commands)

Detection Logic: Flags usage of -enc, -EncodedCommand, or Base64 strings in command-line input.

Rule File: powershell_encoded_command.yml

✅ Includes screenshot of triggered Splunk alert

🔹 Detection 2: AWS API Reconnaissance (MITRE T1526, T1087)
Log Source: AWS CloudTrail

Technique: Cloud Service Discovery

Detection Logic: Detects excessive Describe* API activity in a short time window.

Rule File: aws_describe_recon.yml

✅ Includes Splunk alert and example CloudTrail logs

🛠 Tools Used
Splunk Enterprise (local): Data ingestion, alerting

Sigma: YAML-based detection rules

MITRE ATT&CK: Threat technique mapping

Visual Studio Code: Log formatting/redaction

🎯 Learning Objectives
Detect adversary behaviors across Windows and AWS

Map detection logic to MITRE ATT&CK techniques

Write Sigma rules from real-world logs

Practice Splunk alerting and false positive tuning

👤 Author
Kariam Rodriguez
Aspiring cybersecurity engineer with interests in threat detection, SIEM, and security automation.



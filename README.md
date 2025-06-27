# 📡 SIEM Detection Project

This project demonstrates hands-on detection engineering using **Splunk** and **Sigma** rules to identify suspicious activity across Windows and AWS environments. It focuses on two key threat scenarios:

- **Obfuscated PowerShell Execution** (MITRE T1059.001)  
- **AWS Reconnaissance via Describe API Calls** (MITRE T1526, T1087)

By ingesting and analyzing **Sysmon** and **AWS CloudTrail** logs, I created actionable detections mapped to **MITRE ATT&CK** and deployed real-time alerts in Splunk.

---

## 📁 Folder Structure & Detection Rules

### 🔹 Detection 1: Obfuscated PowerShell (MITRE T1059.001)
- **Log Source:** Sysmon  
- **Technique:** PowerShell Scripting (Encoded Commands)  
- **Detection Logic:** Flags usage of `-enc`, `-EncodedCommand`, or embedded Base64 strings in PowerShell command-line input  
- **Rule File:** `powershell_encoded_command.yml`  
- ✅ Includes screenshot of triggered Splunk alert

### 🔹 Detection 2: AWS API Reconnaissance (MITRE T1526, T1087)
- **Log Source:** AWS CloudTrail  
- **Technique:** Cloud Service & Account Discovery  
- **Detection Logic:** Detects excessive `Describe*` API calls in a short time window  
- **Rule File:** `aws_describe_recon.yml`  
- ✅ Includes Splunk alert logic and CloudTrail event samples

---

## ⚙️ Tools Used

- **Splunk Enterprise (local):** Data ingestion, search, and alerting  
- **Sigma:** YAML-based detection rule development  
- **MITRE ATT&CK:** Tactic and technique mapping  
- **Visual Studio Code:** Log editing and rule authoring

---

## 🎯 Learning Objectives

- Detect real-world adversary behaviors in enterprise environments  
- Practice mapping detection logic to the MITRE ATT&CK framework  
- Write custom Sigma rules and tune false positives  
- Use Splunk to build alerting pipelines from log ingestion to response  
- Work with structured log data (e.g., Sysmon XML, JSON-based CloudTrail)

---

## 👤 Author

**Kariam Rodriguez**  
Aspiring cybersecurity engineer passionate about **threat detection**, **SIEM**

# SIEM Detection Project

This project showcases hands-on detection engineering using Splunk and Sigma rules to identify suspicious activity in enterprise environments. Specifically, it focuses on two threat scenarios:

1. **Obfuscated PowerShell Execution** on a Windows host
2. **Reconnaissance via AWS CloudTrail Describe* API calls**

By ingesting and analyzing both **Sysmon logs** and **AWS CloudTrail logs**, this project demonstrates how to create, map, and operationalize detections using MITRE ATT&CK and real-time Splunk alerts.

---

## 📁 Folder Structure


---

## 📌 Detection 1: Obfuscated PowerShell (MITRE T1059.001)

**Log Source**: Sysmon  
**Technique**: Command and Scripting Interpreter: PowerShell  
**Data**: `CommandLine` field with encoded content  
**Detection Logic**: Looks for use of `-enc`, `-EncodedCommand`, or embedded base64 strings in PowerShell command line.

**Mapped to**: [T1059.001](https://attack.mitre.org/techniques/T1059/001/) – PowerShell  
**Detection Rule**: [`powershell_encoded_command.yml`](detections/powershell_encoded_command.yml)

✅ Also includes a Splunk alert screenshot for triggering on detection.

---

## 📌 Detection 2: AWS API Reconnaissance (MITRE T1526)

**Log Source**: AWS CloudTrail  
**Technique**: Cloud Service Discovery  
**Data**: `eventName` values like `DescribeSubnets`, `DescribeSecurityGroups`, etc.  
**Detection Logic**: Flags excessive use of `Describe*` API calls in a short time period.

**Mapped to**:
- [T1526](https://attack.mitre.org/techniques/T1526/) – Cloud Service Discovery
- [T1087](https://attack.mitre.org/techniques/T1087/) – Account Discovery

**Detection Rule**: [`aws_describe_recon.yml`](detections/aws_describe_recon.yml)

✅ Includes alert logic screenshot and CloudTrail event samples.

---

## ⚙️ Tools Used

- **Splunk Enterprise (local)** – Data ingestion, search, alerting
- **Sigma** – Detection rule creation in YAML
- **MITRE ATT&CK** – Threat technique mapping
- **Visual Studio Code** – Log editing and redaction

---

## 🧪 How to Use

1. Clone this repo or download the files.
2. In Splunk:
   - Create two indexes: `security_lab` (for Sysmon), `cloudtrail` (for AWS logs)
   - Upload logs from the `/logs` folder
   - Run queries provided in the Sigma rules or screenshots
3. Create alerts using the visual reference in the `/alerts` folder.
4. Tune and extend the detections for production usage.

---

## ✅ Learning Objectives

- Learn how to detect real-world adversary behaviors
- Practice mapping to the MITRE ATT&CK framework
- Develop alerting logic in Splunk
- Work with structured log data (JSON, Sysmon XML)
- Understand Sigma rule syntax and purpose

---

## 📢 Author

**Kariam Rodriguez**  
Aspiring cybersecurity engineer passionate about detection engineering, threat hunting, and security automation.

---

## 📄 License

MIT License – feel free to fork and build on this project.

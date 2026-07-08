# 🛡️ Incident Detection & Threat Hunting using Splunk SIEM

> A hands-on Security Operations Center (SOC) lab built using Splunk Enterprise to simulate cyberattacks, collect logs, detect threats, and perform incident triage.

![Splunk](https://img.shields.io/badge/Splunk-Enterprise-green)
![Windows](https://img.shields.io/badge/Windows-Server-blue)
![Ubuntu](https://img.shields.io/badge/Ubuntu-Linux-E95420)
![SIEM](https://img.shields.io/badge/SIEM-Security-orange)
![SOC](https://img.shields.io/badge/SOC-Analyst-red)

---

# 📌 Overview

This project demonstrates the implementation of a Security Information and Event Management (SIEM) solution using **Splunk Enterprise** in a simulated SOC environment.

A multi-machine lab was configured to generate real-world attack scenarios, collect security logs, create custom detection rules, and investigate alerts.

The objective was to gain practical experience in:

- SIEM Deployment
- Log Collection
- Threat Detection
- Incident Triage
- IOC Analysis
- Security Monitoring

---

# 🏗️ Lab Architecture

```
                +--------------------+
                | Ubuntu Attacker VM |
                +---------+----------+
                          |
                Simulated Cyber Attacks
                          |
                          ▼
                +--------------------+
                | Windows Web Server |
                | IIS + Event Logs   |
                +---------+----------+
                          |
               Universal Forwarder
                          |
                          ▼
                +--------------------+
                | Splunk Enterprise  |
                | Analyst Machine    |
                +--------------------+
```

---

# 🖥️ Environment

| Component | Description |
|-----------|-------------|
| SIEM | Splunk Enterprise |
| Log Forwarder | Splunk Universal Forwarder |
| Attacker Machine | Ubuntu Linux |
| Victim Machine | Windows Server |
| Web Server | IIS |
| Analyst Machine | Windows |
| Log Sources | Windows Security Logs, IIS Logs |

---

# 🎯 Objectives

- Configure Splunk Enterprise
- Forward Windows Event Logs
- Monitor IIS Logs
- Create SPL detection rules
- Generate security alerts
- Investigate Indicators of Compromise (IoCs)
- Perform incident triage

---

# 🔍 Attack Scenarios

The following attack simulations were performed.

## 1. Brute Force Attack

### Detection

- Windows Event IDs
  - 4624 (Successful Login)
  - 4625 (Failed Login)

### Detection Logic

- Multiple failed logins
- Successful login after repeated failures
- Alert generation

---

## 2. Ransomware Detection

### Detection

- Suspicious Process Execution
- Privilege Escalation Events

### Windows Event IDs

- 4674
- 4688
- 4689

### Indicators

- Unexpected executable launch
- Encryption process
- Suspicious process creation

---

## 3. SQL Injection Detection

### Detection

Monitoring IIS logs for SQL Injection payloads.

Examples:

```
' OR 1=1--
```

```
%27
```

```
#
```

```
--
```

---

## 4. Cross Site Scripting (XSS)

Detection of malicious JavaScript payloads inside IIS logs.

Examples:

```html
<script>alert("You are hacked")</script>
```

Detection keywords:

- %3CSCRIPT
- Javascript
- Alert

---

## 5. Broken Access Control

Detection of unauthorized access to admin pages.

Example:

```
/Admin/AdminOrders.aspx
```

Checks whether a non-admin user attempts to access restricted resources.

---

## 6. Remote Code Execution (RCE)

Detection of suspicious application crashes and malicious process execution.

Indicators include:

- Application crash
- mqsvc.exe
- Event ID 1000
- Event ID 1001

---

# 📊 Splunk Features Used

- Search Processing Language (SPL)
- Alert Creation
- Triggered Alerts
- Event Correlation
- Time Window Analysis
- Windows Event Monitoring
- IIS Log Analysis
- Incident Investigation

---

# 🧠 Skills Demonstrated

- Security Operations Center (SOC)
- SIEM Operations
- Splunk Enterprise
- SPL Queries
- Threat Detection
- Threat Hunting
- Log Analysis
- IOC Analysis
- Incident Triage
- Security Monitoring
- Alert Engineering
- Windows Event Logs
- IIS Log Monitoring

---

# ⚙️ Technologies

- Splunk Enterprise
- Splunk Universal Forwarder
- Windows Server
- Ubuntu Linux
- IIS
- Windows Event Viewer
- SSH
- FTP
- SPL

---

# 📈 Learning Outcomes

Through this project I gained practical experience in:

- Deploying Splunk Enterprise
- Configuring Universal Forwarders
- Collecting Windows Security Logs
- Monitoring IIS Logs
- Building custom SPL queries
- Detecting multiple cyber attacks
- Investigating security events
- Classifying incidents based on severity
- Understanding SOC workflows

---

# 🚨 Sample Detection Workflow

```
Attack Simulation
        │
        ▼
Windows Event Logs / IIS Logs
        │
        ▼
Universal Forwarder
        │
        ▼
Splunk Enterprise
        │
        ▼
SPL Detection Query
        │
        ▼
Alert Triggered
        │
        ▼
SOC Investigation
        │
        ▼
Incident Triage
```

---

# 📸 Screenshots

Add screenshots for:

- Lab Architecture
- Splunk Dashboard
- Triggered Alerts
- SPL Queries
- Brute Force Detection
- SQL Injection Detection
- XSS Detection
- Ransomware Detection

---

# 📚 Key Concepts

- SIEM
- SOC
- Windows Event Logs
- SPL
- Universal Forwarder
- IOC
- Threat Detection
- Incident Response
- Security Monitoring
- Threat Hunting

---

# 👨‍💻 Author

**Khubaib PP**

Aspiring SOC Analyst | Cybersecurity Enthusiast

- LinkedIn: https://linkedin.com/in/khubaibpp
- GitHub: https://github.com/khub000
- Portfolio: https://www.khubaibpp.online

---
######

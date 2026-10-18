# AI-SOAR-Wazuh-DeepSeek
Real-time integrating Wazuh SIEM, Python log-tailing and DeepSeek AI via OpenRouter API 
<div align="center">

# 🎯 AI-SOAR Sentinel
### Real-Time Automated SOC Incident Triage Pipeline

![Status](https://img.shields.io/badge/STATUS-COMPLETED-success?style=for-the-badge)
![Category](https://img.shields.io/badge/CATEGORY-AI%20SOAR%20--%20SIEM-blue?style=for-the-badge)
![Focus](https://img.shields.io/badge/FOCUS-ALERT%20TRIAGE-purple?style=for-the-badge)

<p align="center">
  <b>🤖 AI-Powered Triage</b> • 
  <b>🛡️ Incident Response</b> • 
  <b>⚡ Real-Time Automation</b> • 
  <b>🔍 Threat Analysis</b>
</p>

<!-- Tech Stack Badges -->
![Wazuh](https://img.shields.io/badge/Wazuh_SIEM-007ACC?style=flat-square&logo=wazuh&logoColor=white)
![Python](https://img.shields.io/badge/Python_Automation-3776AB?style=flat-square&logo=python&logoColor=white)
![DeepSeek](https://img.shields.io/badge/DeepSeek_AI-412991?style=flat-square&logo=openai&logoColor=white)
![OpenRouter](https://img.shields.io/badge/OpenRouter_API-FF6C37?style=flat-square&logo=postman&logoColor=white)
![MITRE](https://img.shields.io/badge/MITRE_ATT%26CK-FF4500?style=flat-square)
![Kali](https://img.shields.io/badge/Kali_Linux-555555?style=flat-square&logo=kalilinux&logoColor=white)
![Windows](https://img.shields.io/badge/Windows_10-0078D6?style=flat-square&logo=windows&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu_Server-E95420?style=flat-square&logo=ubuntu&logoColor=white)

---

</div>

## 📑 Overview

The **AI-SOAR Sentinel** is an enterprise-grade, real-time Security Operations Center (SOC) incident response pipeline designed to eliminate **Tier-1 Alert Fatigue**. 

By bridging **Wazuh SIEM** alert telemetry with **DeepSeek AI** (via OpenRouter API), the system continuously monitors log pipelines, extracts high-severity events (**Rule Level ≥ 7**), and generates structured, actionable threat analysis within seconds—directly onto the analyst's terminal.

---

## 🎯 Key Project Objectives

* 🚨 **Reduce Alert Fatigue:** Automatically filter noise and highlight critical threats.
* ⚡ **Instant AI Triage:** Streamline incident context without manual log hunting.
* 🛡️ **Actionable Response:** Provide mapped MITRE ATT&CK techniques and remediation steps immediately.
* 🛠️ **Lightweight & Modular:** Pure Python log-tailing engine requiring zero complex middleware.

---

## 🏗️ System Architecture & Workflow







┌─────────────────┐ ┌────────────────────────┐ ┌────────────────────────┐
│ Victim Host │ │ Wazuh SIEM Manager │ │ Python Triage Engine │
│ (Windows 10) │ ───► │ (/var/ossec/logs/...) │ ───► │ (grop-triage.py) │
└─────────────────┘ └────────────────────────┘ └───────────┬────────────┘
▲ │
│ Attacked By ▼ Filter (Level ≥ 7)
┌─────────────────┐ ┌────────────────────────┐
│ Attacker Node │ │ DeepSeek AI Engine │
│ (Kali Linux) │ │ (via OpenRouter API) │
└─────────────────┘ └────────────────────────┘


1. **Telemetry Collection:** Wazuh Manager aggregates logs from endpoints.
2. **Real-time Engine:** Custom Python script tails `/var/ossec/logs/alerts/alerts.json`.
3. **Severity Check:** Events with `rule.level >= 7` trigger the AI analysis pipeline.
4. **AI Report Generation:** DeepSeek evaluates the payload and outputs a structured SOC Triage Report.

---

## 🧪 Live Lab Verification & Attack Simulation

* **Target Host:** Windows 10 Endpoint (`192.168.1.42`)
* **Attacker Host:** Kali Linux (`Nmap -A -T4` scanning & file modifications)
* **Detection Engine:** Wazuh Manager (Ubuntu Server)
* **Verified Result:** Instant alert processing and AI Triage generation on terminal upon rule level 7 detection.

---

## 🚀 Quick Start Guide

### 1. Prerequisites
Ensure Python 3 and `requests` library are installed on your Wazuh Manager node:
```bash
sudo apt-get update
sudo apt-get install python3 python3-pip -y
pip3 install requests

2. Configuration
Clone the repository and add your API credentials :
git clone [https://github.com/basitsajidSOC/AI-SOAR-Wazuh-DeepSeek.pkg](https://github.com/basitsajidSOC/AI-SOAR-Wazuh-DeepSeek.pkg)
cd AI-SOAR-Wazuh-DeepSeek
Edit grop-triage.py to insert your OpenRouter API key:API_KEY = "YOUR_OPENROUTER_API_KEY_HERE"
3: Execution
Run the triage engine with root privileges:
sudo python3 grop-triage.py

🤝 Acknowledgments
Special thanks to TCM Security and TryHackMe for providing hands-on training, practical labs, and knowledge that helped inspire this Blue Team automation build.
<div align="center">
<b>Developed by Basit Sajid | Aspiring SOC Analyst & Security Automation Enthusiast</b>
</div>


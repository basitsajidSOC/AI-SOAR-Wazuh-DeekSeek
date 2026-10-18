# AI-SOAR-Wazuh-DeepSeek
Real-time integrating Wazuh SIEM, Python log-talling and DeepSeek AI via OpenRouter API 

# 🚀 AI-SOAR Sentinel: Wazuh SIEM & DeepSeek AI Automated Incident Triage

An automated, real-time Security Operations Center (SOC) triage pipeline that bridges **Wazuh SIEM** alert logging with **DeepSeek AI** via the **OpenRouter API** to combat Level-1 alert fatigue and speed up incident response.

---

## 📌 Project Overview & Architecture

In high-volume SOC environments, analysts face alert fatigue from manual log evaluation. This project automates the first layer of triage:

1. **Log Ingestion:** Wazuh Manager monitors endpoints (e.g., Windows 10 Client) and writes security events to `/var/ossec/logs/alerts/alerts.json`.
2. **Real-time Engine:** A custom Python script continuously tails `alerts.json`.
3. **Smart Filtering:** Filters incoming JSON objects for high-severity events (**Rule Level ≥ 7**).
4. **AI Triage Generation:** Passes the filtered alert payload to DeepSeek AI, receiving structured, actionable triage reports in seconds.

---

## 🛠️ Lab Environment Setup

* **SIEM / Manager:** Ubuntu Server running Wazuh Manager & Dashboard.
* **Victim Endpoint:** Windows 10 Enterprise Agent (`192.168.1.42`).
* **Attacker Machine:** Kali Linux (`Nmap` reconnaissance & execution attacks).
* **AI Engine:** DeepSeek-R1 / DeepSeek-V3 via OpenRouter API.

---

## 📋 Features of Generated AI Reports

The AI engine outputs standardized Markdown summaries directly to the SOC terminal, including:
* ⚠️ **Threat Severity & Summary**
* 🎯 **Impact Assessment**
* 🔍 **MITRE ATT&CK Mapping**
* 🛡️ **Actionable Remediation & Containment Steps**

---

## 🚀 Getting Started

### 1. Prerequisites
Ensure Python 3 is installed on your Wazuh Manager node

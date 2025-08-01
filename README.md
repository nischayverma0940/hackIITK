# 🛡️ Threat Intelligence Extraction Using NLP

This Jupyter Notebook demonstrates a lightweight threat intelligence pipeline that automatically extracts key cybersecurity insights from unstructured threat reports using Python and natural language processing (NLP).

## 📌 Purpose

The goal is to extract structured threat intelligence indicators from raw text reports, including:

- **Indicators of Compromise (IoCs)** – IP addresses and domain names  
- **Tactics, Techniques, and Procedures (TTPs)** – using MITRE ATT&CK mappings  
- **Threat Actor(s)** – names and organization references  
- **Targeted Entities** – companies, sectors, tools targeted  
- **Malware** – detection of known malware families and their hashes  

## ⚙️ How It Works

The notebook:
1. Uses **regex** to extract IPs/domains as IoCs  
2. Maps **TTPs** using keyword-based heuristics aligned to the [MITRE ATT&CK framework](https://attack.mitre.org/)  
3. Leverages **spaCy** NLP to extract named entities (e.g., ORG, PERSON)  
4. Detects **malware** from a predefined knowledge base using string matching  

## 🔍 Example Report Processed

```text
The APT33 group, suspected to be from Iran, has launched a new campaign targeting
the energy sector organizations. The attack utilizes Shamoon malware, known for 
its destructive capabilities. The threat actor exploited a vulnerability to gain 
initial access and used spear-phishing. It communicated with 192.168.1.1 and 
example.com using PowerShell for lateral movement.

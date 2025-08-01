🛡️ Threat Intelligence Extraction Using NLP
This Jupyter Notebook demonstrates a lightweight threat intelligence pipeline that automatically extracts key cybersecurity insights from unstructured threat reports using Python and natural language processing (NLP).

📌 Purpose
The goal is to extract structured threat intelligence indicators from raw text reports, including:

Indicators of Compromise (IoCs) – IP addresses and domain names

Tactics, Techniques, and Procedures (TTPs) – using MITRE ATT&CK mappings

Threat Actor(s) – names and organization references

Targeted Entities – companies, sectors, tools targeted

Malware – detection of known malware families and their hashes

⚙️ How It Works
The notebook:

Uses regex to extract IPs/domains as IoCs

Maps TTPs using keyword-based heuristics aligned to the MITRE ATT&CK framework

Leverages spaCy NLP to extract named entities (e.g., ORG, PERSON)

Detects malware from a predefined knowledge base using substring matching

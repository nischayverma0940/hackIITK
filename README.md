# 🛡️ Threat Intelligence Extraction Using NLP

This Jupyter Notebook demonstrates a lightweight threat intelligence pipeline that extracts structured cyber threat intelligence from unstructured reports using Python and NLP techniques.

---

## 📌 Features

The notebook extracts:

- **Indicators of Compromise (IoCs):**
  - IP addresses
  - Domain names
- **Tactics, Techniques, and Procedures (TTPs)** (mapped to MITRE ATT&CK)
- **Threat Actor(s)** (using spaCy entity recognition + optional keyword matches)
- **Malware details** (from a static knowledge base)
- **Targeted Entities** (organizations, technologies, sectors)

---

## ⚙️ How It Works

The pipeline performs the following steps:

1. **IoC Extraction** using Regular Expressions
2. **TTP Extraction** using keyword-to-MITRE mappings
3. **Named Entity Recognition (NER)** using spaCy for threat actors and targets
4. **Malware Detection** from known malware family signatures

---

## 🧠 Dependencies

Install the required packages:

```bash
pip install spacy
python -m spacy download en_core_web_sm

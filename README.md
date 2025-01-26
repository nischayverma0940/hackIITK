# Threat Intelligence Extraction Tool

This tool extracts Indicators of Compromise (IoCs), MITRE ATT&CK TTPs, Threat Actors, and Malware details from cybersecurity reports.

## Features

- Extract IoCs (IP addresses, domains) using regular expressions.
- Identify MITRE ATT&CK Tactics, Techniques, and Procedures (TTPs).
- Detect Threat Actors and Targeted Entities using Named Entity Recognition (NER).
- Search VirusTotal for malware hash lookups.
- Recognize and report known malware families based on predefined hash values.

## Requirements

The project uses the following libraries:

1. **[Transformers](https://huggingface.co/docs/transformers/index)**

   - Provides pre-trained models for Named Entity Recognition (NER).
   - Install using:
     ```bash
     pip install transformers
     ```

2. **[Torch](https://pytorch.org/)**

   - Backend for the Transformers library.
   - Install using:
     ```bash
     pip install torch
     ```

3. **[Requests](https://docs.python-requests.org/)**

   - For making API requests to VirusTotal.
   - Install using:
     ```bash
     pip install requests
     ```

4. **[Python-dotenv](https://pypi.org/project/python-dotenv/)**
   - For managing environment variables.
   - Install using:
     ```bash
     pip install python-dotenv
     ```

To simplify installation, all required libraries are listed in `requirements.txt`.

## Installation

### 1. Clone the Repository or Unzip

Download or unzip the package and navigate to the project directory:

```bash
cd project
```

### 2. Install Dependencies

Run the following command to install all required libraries:

pip install -r requirements.txt

### 3. Set Up VirusTotal API Key

Create a `.env` file in the project directory and add your VirusTotal API key:

VIRUS_TOTAL_API_KEY=your_api_key

### 4. Run the Tool

Run the script to analyze a sample report:

python main.py

## Input Report Example

The script processes a cybersecurity report like this:

Plaintext
The APT33 group, suspected to be from Iran, has launched a new campaign targeting the energy sector. The attack utilizes Shamoon malware, known for its destructive capabilities. The threat actor exploited a vulnerability in the network perimeter to gain initial access.

The output provides extracted IoCs, TTPs, Threat Actors, and more.

---

## Notes

- Ensure Python 3.8+ is installed on your system.
- Avoid sharing your VirusTotal API key publicly.
- The tool uses publicly available open-source libraries, as referenced in the installation section.

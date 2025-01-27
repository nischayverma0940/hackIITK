Here's an updated version of your `README.md` file that includes explanations of the code structure, usage, package versions, and more detailed instructions for running the project:

---

# Threat Intelligence Extraction Tool

This tool extracts Indicators of Compromise (IoCs), MITRE ATT&CK TTPs, Threat Actors, and Malware details from cybersecurity reports.

## Features

- **Extract IoCs (IP addresses, domains)** using regular expressions.
- **Identify MITRE ATT&CK Tactics, Techniques, and Procedures (TTPs)**.
- **Detect Threat Actors and Targeted Entities** using Named Entity Recognition (NER).
- **Search VirusTotal** for malware hash lookups.
- **Recognize and report known malware families** based on predefined hash values.

## Code Structure

1. **IoC Extraction**: Utilizes regular expressions to find IP addresses and domain names in the report text.
2. **TTPs Extraction**: Matches tactics and techniques based on predefined keywords and maps them to MITRE ATT&CK TTPs.
3. **Named Entity Recognition (NER)**: Uses the Hugging Face Transformers pipeline for entity extraction, focusing on threat actors and targeted entities.
4. **VirusTotal Integration**: Allows the user to perform hash lookups to gather information on malware families.
5. **Known Malware Recognition**: Compares hashes with predefined known malware families for identification.
6. **PDF Report Parsing**: Extracts text from PDF files and processes it for intelligence extraction.

## Requirements

The project uses the following libraries:

1. **[Transformers](https://huggingface.co/docs/transformers/index)**: For Named Entity Recognition (NER).

   - Install using:
     ```bash
     pip install transformers==4.28.0
     ```

2. **[Torch](https://pytorch.org/)**: Backend for the Transformers library.

   - Install using:
     ```bash
     pip install torch==1.13.1
     ```

3. **[Requests](https://docs.python-requests.org/)**: For making API requests to VirusTotal.

   - Install using:
     ```bash
     pip install requests==2.28.1
     ```

4. **[Python-dotenv](https://pypi.org/project/python-dotenv/)**: For managing environment variables.

   - Install using:
     ```bash
     pip install python-dotenv==0.21.0
     ```

5. **[PyPDF2](https://pypi.org/project/PyPDF2/)**: For PDF text extraction.
   - Install using:
     ```bash
     pip install PyPDF2==1.26.0
     ```

To simplify installation, all required libraries are listed in `requirements.txt` with their versions.

## Installation

### 1. Clone the Repository or Unzip

Download or unzip the package and navigate to the project directory:

```bash
cd project
```

### 2. Install Dependencies

Run the following command to install all required libraries:

```bash
pip install -r requirements.txt
```

### 3. Set Up VirusTotal API Key

Create a `.env` file in the project directory and add your VirusTotal API key:

```plaintext
VIRUS_TOTAL_API_KEY=your_api_key
```

### 4. Run the Tool

Run the script to analyze a sample report:

```bash
python main.py
```

## Input Report Example

The script processes a cybersecurity report like this:

```plaintext
The APT33 group, suspected to be from Iran, has launched a new campaign targeting the energy sector. The attack utilizes Shamoon malware, known for its destructive capabilities. The threat actor exploited a vulnerability in the network perimeter to gain initial access.
```

### Sample Output

The output will provide the following information:

```json
{
  "IoCs": {
    "IP addresses": ["192.168.1.1"],
    "Domains": ["example.com"]
  },
  "TTPs": {
    "Tactics": [
      ["TA0002", "Execution"],
      ["TA0001", "Initial Access"],
      ["TA0008", "Lateral Movement"]
    ],
    "Techniques": ["T1059", "T1210"]
  },
  "Threat Actor(s)": ["APT33"],
  "Malware": [
    {
      "Name": "Shamoon",
      "md5": "example_md5_hash",
      "sha1": "example_sha1_hash",
      "sha256": "example_sha256_hash"
    }
  ],
  "Targeted Entities": ["Iran"]
}
```

## Novel Contribution and Implementation Process

The **novel contribution** of this project lies in its **automated extraction** of key cybersecurity intelligence (IoCs, TTPs, Threat Actors, Malware) directly from cybersecurity reports, which are typically unstructured and difficult to analyze manually. This solution can be highly useful for security analysts and researchers by streamlining the process of parsing and analyzing threat reports.

### Implementation Process:

1. **Data Collection**: The first step involves gathering relevant cybersecurity reports (e.g., PDFs) that contain information about cyber threats.
2. **Text Extraction**: The tool leverages **PyPDF2** to extract the text content from these reports for further analysis.
3. **Named Entity Recognition**: Using Hugging Face’s **Transformers**, the system identifies key entities such as threat actors and targeted entities within the report text.
4. **IoC Detection**: The tool extracts Indicators of Compromise (IoCs) such as IP addresses and domains using regular expressions.
5. **MITRE ATT&CK Mapping**: The tool matches reported techniques and tactics to **MITRE ATT&CK** framework identifiers, categorizing them into tactics like "Execution" or "Lateral Movement".
6. **Malware Recognition**: The tool compares malware names and hashes with predefined known malware families and performs lookups in **VirusTotal** for further details.
7. **Results Output**: The final results are provided in a structured JSON format, making it easy for users to parse and analyze the extracted intelligence.

### Contributions

- **Automated Threat Intelligence Extraction**: The tool reduces the time analysts spend on manually extracting and categorizing threat intelligence from reports.
- **Integration with VirusTotal**: It offers an automated lookup of known malware hashes through the VirusTotal API, providing further context and enhancing malware analysis.
- **Named Entity Recognition for Threat Actors**: This is a key innovation that allows the tool to automatically detect threat actor names without manual intervention, improving accuracy and efficiency.

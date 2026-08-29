# Social Sentinel: AI-Powered Phishing & Social Engineering Analyzer

An open-source, AI-powered NLP tool designed to detect psychological manipulation, urgency, and social engineering tactics in emails and text messages.

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![Streamlit](https://img.shields.io/badge/Streamlit-1.31+-red.svg)
![Transformers](https://img.shields.io/badge/HuggingFace-Transformers-orange.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

Social Sentinel is an open-source, interactive web application that uses Natural Language Processing (NLP) to detect phishing attempts and social engineering tactics in emails and messages.

Instead of relying only on static blocklists, suspicious links, or predefined keywords, Social Sentinel analyzes the semantic intent of text to identify patterns associated with urgency, manipulation, authority, fear, and other social engineering techniques.

## Features

* **Real-time Inference:** Uses a fine-tuned BERT model to classify text and identify potential threats.
* **Probability Scoring:** Provides a confidence metric for each threat assessment.
* **Interactive UI:** Built with Streamlit for a clean and user-friendly analysis dashboard.
* **Semantic Analysis:** Examines the meaning and intent of messages rather than relying entirely on predefined malicious indicators.
* **Social Engineering Detection:** Designed to recognize psychological techniques such as urgency, authority, fear, and manipulation.
* **Unseen Threat Detection:** Semantic analysis can help identify previously unseen or payload-less social engineering attempts that may not appear on traditional blocklists.

## How It Works

Social Sentinel analyzes the semantic meaning and psychological characteristics of a message rather than relying only on known malicious links, keywords, or sender blocklists.

The analysis follows a simple pipeline:

**Message Input → Text Preprocessing → BERT-based NLP Analysis → Threat Classification → Confidence Score**

This approach allows the system to identify social engineering signals such as urgency, authority, fear, manipulation, and attempts to pressure a user into taking immediate action.

## Tech Stack

* **Frontend:** Streamlit
* **AI / Machine Learning:** PyTorch, Hugging Face `transformers`
* **Model Architecture:** BERT
* **ML Backend:** PyTorch
* **Data Processing:** Pandas
* **Language:** Python 3.9+

## System Architecture

The pipeline processes input text through linguistic preprocessing, transformer-based classification, and confidence scoring before rendering actionable telemetry in the UI.

```text
[ User Input (Email / SMS Text) ]
               │
               ▼
   ┌───────────────────────┐
   │   Streamlit Web UI    │
   └───────────┬───────────┘
               │
               ▼
   ┌───────────────────────┐
   │   NLP Preprocessing   │
   │  - Text Normalization │
   │  - Tokenization       │
   └───────────┬───────────┘
               │
               ▼
   ┌───────────────────────┐
   │   Inference Engine    │
   │  - Fine-Tuned BERT    │
   │  - PyTorch Backend    │
   └───────────┬───────────┘
               │
               ▼
   ┌───────────────────────┐
   │  Threat Assessment    │
   │  - Confidence Scoring │
   │  - Intent Red Flags   │
   └───────────┬───────────┘
               │
               ▼
   [ Visual Risk Dashboard ]



## Project Structure

```text
social-sentinel/
├── app.py                 # Core Streamlit application and ML inference logic
├── requirements.txt       # Python dependencies
├── .gitignore             # Files and directories excluded from Git
├── README.md              # Project documentation
├── CONTRIBUTING.md        # Guidelines for open-source contributors
└── LICENSE                # MIT License
```

## Local Installation

### 1. Clone the repository

```bash
git clone https://github.com/alpha-endgame/social-sentinel.git
cd social-sentinel
```

### 2. Create a virtual environment

Creating a virtual environment is recommended to keep the project's dependencies isolated.

```bash
python -m venv venv
```

**Windows:**

```bash
venv\Scripts\activate
```

**macOS / Linux:**

```bash
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the application

```bash
streamlit run app.py
```

Streamlit will display a local URL in the terminal, typically:

`http://localhost:8501`

## User Guide

Once you have completed the local installation and started the Streamlit server, follow these steps to analyze messages:

### 1. Launch the Dashboard
* Open your web browser and navigate to the local URL provided in your terminal (usually `http://localhost:8501`).

### 2. Analyze Text
* Locate the main text input box on the dashboard.
* Paste the contents of a suspicious email, SMS, or direct message into the box.
* Click the **Analyze Threat** button.

### 3. Understanding the Results
* **Classification:** The model will immediately flag the text as either *Safe*, *Suspicious*, or *Phishing*.
* **Probability Score:** You will see a confidence metric (e.g., 92%). A higher score indicates the model is highly confident in its assessment based on the semantic intent and psychological manipulation detected.
* **Threat Indicators:** If applicable, the dashboard will highlight specific sentences that exhibit urgency, authority-based threats, or manipulation.


## Current Scope

Social Sentinel currently focuses primarily on **text-based phishing and social engineering analysis**.

The system analyzes semantic and psychological indicators contained within message content. It does not currently replace URL scanners, malware analysis tools, email security gateways, sender reputation systems, or professional security analysis.

The project should therefore be considered an additional defensive analysis layer rather than a complete phishing detection solution.

## Contributing

Contributions are welcome.

Potential areas for contribution include:

* Model improvements and experimentation
* Additional social engineering detection techniques
* Dataset improvements
* UI and usability enhancements
* Testing and evaluation
* Documentation
* New defensive analysis capabilities

Please read `CONTRIBUTING.md` before submitting a contribution.

## Disclaimer

Social Sentinel is intended for **educational, research, and defensive cybersecurity purposes**.

Machine learning predictions are probabilistic and may produce false positives or false negatives. A message classified as safe should not automatically be considered trustworthy, and suspicious communications should be independently verified before taking action.

## License

This project is licensed under the **MIT License**.

See the `LICENSE` file for details.

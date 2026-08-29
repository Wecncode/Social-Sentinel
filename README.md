# Social-Sentinel - AI-Powered Phishing & Social Engineering Analyzer
An open-source, AI-powered NLP tool designed to detect psychological manipulation, urgency, and zero-day social engineering tactics in emails and text messages.

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![Streamlit](https://img.shields.io/badge/Streamlit-1.31+-red.svg)
![Transformers](https://img.shields.io/badge/HuggingFace-Transformers-orange.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

An open-source, interactive web application that uses Natural Language Processing (NLP) to detect phishing attempts and social engineering tactics in emails and messages. Instead of relying on static blocklists, this tool analyzes the semantic intent of the text to identify urgency, manipulation, and authority-based threats.

## Features
*   **Real-time Inference:** Uses a fine-tuned BERT model to classify text instantly.
*   **Probability Scoring:** Provides a confidence metric for the threat assessment.
*   **Interactive UI:** Built with Streamlit for a clean, user-friendly dashboard.
*   **Zero-day Protection:** Analyzes the *psychology* of the message, helping to catch payload-less phishing attacks that bypass traditional spam filters.

## Tech Stack
*   **Frontend:** Streamlit
*   **AI/Machine Learning:** Hugging Face `transformers` (PyTorch backend)
*   **Data Processing:** Pandas

📂 Project Structure
Plaintext
semantic-shield/
├── app.py                 # Core Streamlit application and ML inference logic
├── requirements.txt       # Python dependencies (Streamlit, Transformers, etc.)
├── .gitignore             # Configured to ignore virtual environments and cache
├── README.md              # This project documentation
├── CONTRIBUTING.md        # Guidelines for open-source contributors
└── LICENSE                # MIT License

## Local Installation

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/ai-phishing-analyzer.git](https://github.com/YOUR_USERNAME/ai-phishing-analyzer.git)
   cd ai-phishing-analyzer

2. **Install dependencies:**
```bash
   pip install -r requirements.txt
```

3. **Run the application:**
```bash
   streamlit run app.py
```

4. ## User Guide

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

> **Note:** 
> *(Optional: You can replace this blockquote with an actual screenshot of your Streamlit app running by using the image syntax below)*
> 
> `![Dashboard Preview](path/to/your/image.png)`

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

4. **Usage:**
   - Open the local URL shown in your terminal (typically `http://localhost:8501`).
   - Paste the suspicious email or message text into the input box.
   - Click **Analyze** to run it through the model.
   - Review the probability score and flagged indicators in the results panel.

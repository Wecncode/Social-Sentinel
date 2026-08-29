# Contributing to Social Sentinel - AI Phishing Analyzer

Welcome! We are excited you want to contribute. This project aims to create an open-source, accessible tool for detecting social engineering attacks using NLP.

## Table of Contents

1. [How You Can Help](#️-how-you-can-help)
2. [Development Setup](#-development-setup)
3. [Project Structure](#project-structure)
4. [Pull Request Process](#-pull-request-process)
5. [Code of Conduct](#-code-of-conduct)

## 🛠️ How You Can Help

We are currently looking for contributions in three areas:
1.  **Data Science:** Improving our training dataset by adding novel phishing templates.
2.  **AI Engineering:** Swapping the current BERT-tiny model for a more robust model (e.g., RoBERTa) or implementing SHAP (SHapley Additive exPlanations) to highlight exactly *which* words triggered the alert.
3.  **Cybersecurity / Threat Intel:** Connecting the app to external APIs (like VirusTotal or URLScan) to check links found within the text.

## 💻 Development Setup

1. Fork the repository and clone it locally.
2. Create a virtual environment: `python -m venv venv`
3. Activate the environment: `source venv/bin/activate`
4. Install dependencies: `pip install -r requirements.txt`
5. Run the app: `streamlit run app.py`

## Project Structure

social-sentinel/
├── app.py # Core Streamlit application and ML inference logic
├── requirements.txt # Python dependencies (Streamlit, Transformers, etc.)
├── .gitignore # Ignores virtual environments and cache
├── README.md # Project documentation
├── CONTRIBUTING.md # This file
└── LICENSE # MIT License

## 🔀 Pull Request Process

1. Create a new branch for your feature (`git checkout -b feature/AddShapleyValues`).
2. Ensure the Streamlit UI doesn't break by testing locally.
3. Update the `README.md` if you add new Python libraries.
4. Submit a PR with a clear description of the problem you solved.

## 📜 Code of Conduct
Be kind, write clean code, and never upload actual, un-anonymized malicious payloads or PII (Personally Identifiable Information) to the repository.

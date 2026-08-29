# Contributing to Social Sentinel - AI Phishing Analyzer

Welcome! We are excited you want to contribute. This project aims to create an open-source, accessible tool for detecting social engineering attacks using NLP.

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

## 🔀 Pull Request Process

1. Create a new branch for your feature (`git checkout -b feature/AddShapleyValues`).
2. Ensure the Streamlit UI doesn't break by testing locally.
3. Update the `README.md` if you add new Python libraries.
4. Submit a PR with a clear description of the problem you solved.

## 🤖 AI Engineering Guidelines

To keep the inference engine lightweight, secure, and production-ready:
* **Caching & Performance:** Always wrap model loading routines in `@st.cache_resource` to avoid reloading weights on every UI rerun.
* **Input Truncation & Token Limits:** Ensure tokenization pipelines safely handle inputs exceeding the 512-token limit via intelligent truncation or sliding window chunking.
* **Model Explainability:** When implementing explainability (e.g., SHAP, LIME, or attention maps), ensure output scores are normalized and mapped clearly to the UI without blocking main thread execution.
* **Artifact Management:** Do not commit raw `.pt` or `.bin` model weights directly to Git. Use Hugging Face Hub repositories or reference download scripts.
  
## 📜 Code of Conduct
Be kind, write clean code, and never upload actual, un-anonymized malicious payloads or PII (Personally Identifiable Information) to the repository.

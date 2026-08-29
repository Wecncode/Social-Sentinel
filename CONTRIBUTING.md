# Contributing to Social Sentinel - AI Phishing Analyzer

Welcome! We are excited you want to contribute. This project aims to create an open-source, accessible tool for detecting social engineering attacks using NLP. Whether you're fixing bugs, improving the model, or adding new features, your help is appreciated.

## 🛠️ How You Can Help

We are currently looking for contributions in three core areas:
1. **Data Science:** Improving our training dataset by adding novel phishing templates and reducing false positives.
2. **AI Engineering:** Swapping the current BERT-tiny model for a more robust model (e.g., RoBERTa) or implementing SHAP (SHapley Additive exPlanations) to highlight exactly *which* words triggered the alert.
3. **Cybersecurity / Threat Intel:** Connecting the app to external APIs (like VirusTotal or URLScan) to cross-reference links found within the text.

## 💻 Development Setup

1. Fork the repository on GitHub and clone your fork locally:
   ```bash
   git clone https://github.com/YOUR_USERNAME/Social-Sentinel.git
   cd Social-Sentinel
   ```
2. Create a virtual environment:
   ```bash
   python -m venv venv
   ```
3. Activate the environment:
   - **Mac/Linux:** `source venv/bin/activate`
   - **Windows:** `venv\Scripts\activate`
4. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
5. Run the app locally to ensure everything works:
   ```bash
   streamlit run app.py
   ```

## 🔀 Pull Request Process

1. **Open an Issue First:** If you plan on making significant changes, please open an issue first to discuss your proposed changes with the maintainers.
2. **Branch Naming:** Create a new branch for your feature or bugfix (e.g., `feat/add-shapley-values`, `fix/ui-layout`, `docs/update-readme`).
3. **Code Quality:** Ensure your Python code is clean, readable, and commented where necessary.
4. **Testing:** Ensure the Streamlit UI doesn't break by testing your changes locally. If you update the model inference, verify the predictions are still accurate.
5. **Dependencies:** Update `requirements.txt` and `README.md` if your PR introduces new Python libraries.
6. **Submit PR:** Submit a Pull Request with a clear description of the problem you solved and screenshots of UI changes if applicable.

## 🤖 AI Engineering Guidelines

To keep the inference engine lightweight, secure, and production-ready:
* **Caching & Performance:** Always wrap model loading routines in `@st.cache_resource` to avoid reloading weights on every UI rerun.
* **Input Truncation & Token Limits:** Ensure tokenization pipelines safely handle inputs exceeding the 512-token limit via intelligent truncation or sliding window chunking.
* **Model Explainability:** When implementing explainability (e.g., SHAP, LIME, or attention maps), ensure output scores are normalized and mapped clearly to the UI without blocking main thread execution.
* **Artifact Management:** Do not commit raw `.pt` or `.bin` model weights directly to Git. Use Hugging Face Hub repositories or reference download scripts.
  
## 📜 Code of Conduct

Be kind, write clean code, and **never upload actual, un-anonymized malicious payloads, live phishing links, or PII (Personally Identifiable Information)** to this repository. All datasets must be properly sanitized.

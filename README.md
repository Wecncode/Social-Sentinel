# Social Sentinel: AI-Powered Phishing & Social Engineering Analyzer

Social Sentinel is an open-source, lightweight Natural Language Processing (NLP) tool and interactive web application designed to analyze text messages and emails for social engineering tactics. By evaluating psychological manipulation, artificial urgency, and authority exploitation, Social Sentinel helps users and security analysts assess the potential threat level of incoming communications.

This project is built using Python, Scikit-Learn, and Gradio, making it an ideal starter or intermediate project for students learning Data Science, Artificial Intelligence, and Cybersecurity.

---

## Table of Contents

- [Key Features](#key-features)
- [Architecture & Workflow](#architecture--workflow)
- [Machine Learning Models](#machine-learning-models)
- [Dataset Structure](#dataset-structure)
- [Installation & Quickstart](#installation--quickstart)
  - [Running in Google Colab](#running-in-google-colab)
  - [Running Locally](#running-locally)
- [Usage Guide](#usage-guide)
- [Theoretical Concepts Learned](#theoretical-concepts-learned)
- [Contributing](#contributing)
- [License](#license)

---

## Key Features

- **Multi-Model Comparison:** Evaluates messages across four distinct classification algorithms in real time.
- **Tactical Feature Extraction:** Identifies specific social engineering indicators, including Urgency/Pressure, Authority Exploitation, and Psychological Manipulation.
- **Vocabulary Signal Analysis:** Highlights key n-grams and trigger words within the input text that influence the prediction.
- **Interactive UI:** Built with Gradio Blocks, offering a responsive interface with confidence probability distributions.
- **Zero GPU Requirement:** Lightweight design using TF-IDF vectorization and Scikit-Learn pipelines, enabling fast execution on CPU or Google Colab.

---

## Architecture & Workflow

1. **Input Ingestion:** Raw text (email body or SMS) is entered via the web interface.
2. **Text Vectorization:** The input is converted into numerical sparse matrices using Term Frequency-Inverse Document Frequency (TF-IDF) with unigrams and bigrams (`ngram_range=(1, 2)`).
3. **Model Inference:** 
   - The primary classifier predicts the overall status (`phishing` vs. `safe`) and outputs confidence probabilities.
   - Secondary logistic regression classifiers evaluate specific tactic flags.
4. **Keyword Attribution:** Active n-grams present in the vocabulary are extracted and reported.
5. **Dashboard Rendering:** Results are formatted and displayed along with interactive confidence distributions.

---

## Machine Learning Models

Social Sentinel implements four machine learning algorithms to showcase different approaches to text classification:

| Algorithm | Method Type | Key Characteristic |
| :--- | :--- | :--- |
| **Multinomial Naive Bayes** | Probabilistic | Uses Bayes' Theorem assuming feature independence; fast and effective baseline for text. |
| **Logistic Regression** | Linear / Sigmoidal | Fits a linear decision boundary; produces smoothly calibrated probability estimates. |
| **Random Forest** | Ensemble (Decision Trees) | Combines multiple decision trees; captures complex non-linear feature interactions. |
| **Support Vector Machine (SVM)** | Geometric Margin | Finds an optimal separating hyperplane in high-dimensional sparse vector spaces. |

---

## Dataset Structure

The project relies on a starter dataset (`social_sentinel_starter_dataset.csv`). The CSV requires the following schema:

| Column | Data Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique record identifier |
| `text` | String | The body of the email or text message |
| `urgency_flag` | Binary (0/1) | Indicates whether artificial urgency is present |
| `authority_flag` | Binary (0/1) | Indicates whether authority or trust exploitation is present |
| `manipulation_flag` | Binary (0/1) | Indicates general psychological manipulation or coercion |
| `label` | String | Target classification (`phishing` or `safe`) |

---

## Installation & Quickstart

### Running in Google Colab

1. Open Google Colab and create a new notebook.
2. Upload `social_sentinel_starter_dataset.csv` to the root directory.
3. Paste the project code into a code cell and run it.

### Running Locally

1. **Clone the Repository:**
   ```bash
   git clone [https://github.com/your-username/social-sentinel.git](https://github.com/your-username/social-sentinel.git)
   cd social-sentinel

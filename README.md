# Consumer Complaint Topic Analysis

NLP-based topic extraction from the [Consumer Financial Protection Bureau (CFPB) Consumer Complaint Dataset](https://www.consumerfinance.gov/data-research/consumer-complaints/) using Python.

This project was developed as part of the **Project: Data Analysis (DLBDSEDA02)** course at IU Internationale Hochschule.

---

## Project Overview

The goal of this project is to extract the most frequently discussed topics from a large collection of unstructured consumer complaint texts. The pipeline covers:

- Text preprocessing to produce clean inputs
- Vectorization using TF-IDF and Word2Vec
- Topic modelling using LDA and NMF
- Visualization using word clouds and bar charts

---

## Dataset

- **Source:** [CFPB Consumer Complaint Database](https://www.consumerfinance.gov/data-research/consumer-complaints/)
- **Columns used:** `Consumer complaint narrative` (text), `Product` (reference label)
- **Product categories mapped to 6 classes:** credit reporting, mortgage, credit card, retail banking, debt collection, loans
- **Downsampled to:** 10,000 records per category → **60,000 complaints total** (balanced corpus)

> Download the dataset from the CFPB website and place the CSV file in the `data/` directory before running the notebook.

---

## Requirements

Python 3.8 or higher is recommended.

### Install dependencies

```bash
pip install -r requirements.txt
```

### Key libraries

| Library | Purpose |
|---|---|
| `pandas`, `numpy` | Data loading and manipulation |
| `nltk` | Stopword removal, tokenization |
| `spacy` | Lemmatization (`en_core_web_sm` model) |
| `scikit-learn` | TF-IDF vectorization, LDA, NMF |
| `gensim` | Word2Vec embeddings |
| `matplotlib` | Visualization |
| `wordcloud` | Word cloud generation |

### Download required NLTK and spaCy data

```python
import nltk
nltk.download('stopwords')
nltk.download('punkt')
```

```bash
python -m spacy download en_core_web_sm
```

## How to Run

1. **Clone the repository**

```bash
git clone https://github.com/MKhant10/Complaint-Analysis.git
cd Complaint-Analysis
```

2. **Install dependencies**

```bash
pip install -r requirements.txt
```

3. **Download spaCy model**

```bash
python -m spacy download en_core_web_sm
```

4. **Place the dataset** in the `data/` directory.

5. **Open and run the notebook**
- data.ipynb (extract two key columns, renaming, and mapping 6 categories)
- preprocess.ipynb (preprocessing the complaint column)
- vectorization.ipynb (TF-IDF and Word2Vec are performed)
- topic_modeling.ipynb (LDA and NMF)

    Run all cells sequentially from top to bottom.



## Results Summary

### TF-IDF — Top 5 terms by mean score
`credit`, `account`, `report`, `payment`, `loan`

### LDA Topics (7)
| Topic | Label |
|---|---|
| 1 | Identity Theft |
| 2 | Retail Banking |
| 3 | Consumer Rights |
| 4 | Debt Collection |
| 5 | Credit Reporting |
| 6 | Legal Disputes |
| 7 | Loan and Mortgage |

### NMF Topics (7)
| Topic | Label |
|---|---|
| 1 | Bank Account / Card |
| 2 | Credit Reporting |
| 3 | Disputes |
| 4 | Debt Collection |
| 5 | Loan and Mortgage |
| 6 | Consumer Rights |
| 7 | Payment Statements |

---

## Author

**Min Khant**  
Matriculation Number: 42301870  
IU Internationale Hochschule — DLBDSEDA02
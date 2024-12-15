# Named Entity Recognition (NER) Project

This project implements Named Entity Recognition (NER) using Decison Tree, SVM and a transformer-based model (e.g., BERT). The workflow involves data preprocessing, tokenization, label alignment, and model evaluation. It is designed to analyze and extract named entities from text, with a focus on cybersecurity-related data.

## Table of Contents
- [Setup Instructions](#setup-instructions)
- [Data Requirements](#data-requirements)
- [How to Run](#how-to-run)

---

## Setup Instructions

### Prerequisites
Ensure you have the following installed:
- Python (>= 3.8)(No issue for 3.12 and 3.11)
- Required libraries:
  ```bash
  pip install pandas numpy torch transformers evaluate safetensors scikit-learn
  ```

### Repository Structure
- `data/`: Contains the dataset files in `.jsonlines` format for training, validation, and testing.
- `FineTuned-BERT.ipynb`: Main notebook implementing the fine tuned model from BERT.
- `SVM_DECISIONTree.ipynb`: This notebook implementing SVM and Decision Tree process.

### Dataset Preparation
Place the dataset files (`NER-TRAINING.jsonlines`, `NER-VALIDATION.jsonlines`, `NER-TESTING.jsonlines`) in the `data/` directory.

---

## Data Requirements
The dataset files should be in `.jsonlines` format, where each line is a JSON object with the following structure:
```json
{
    "tokens": ["token1", "token2", "token3", "..."],
    "ner_tags": ["O", "B-ENTITY", "I-ENTITY", "..."]
}
```
- `tokens`: The list of tokens in the sentence.
- `ner_tags`: Corresponding NER tags for the tokens.

---

## How to Run

1. **Set up the working directory:**
   Ensure the current directory is set to the project folder.
   ```python
   os.chdir("<path-to-project-folder>")
   ```

2. **Load the datasets:**
   The notebook provides code to load `.jsonlines` files into pandas DataFrames. Ensure these files are placed in the `data/` directory.

3. **Prepare the data:**
   - Map NER tags to numeric values.
   - Tokenize the dataset and align labels with subtokens.

4. **Train the model:**
   Follow the steps in the notebook to:
   - Initialize the tokenizer and model.
   - Train on the prepared dataset.
   - Evaluate performance using metrics like `seqeval`.

5. **Run the notebook:**
   Open the notebook `FineTuned-BERT.ipynb` in Jupyter or any compatible IDE, and execute the cells sequentially.

---

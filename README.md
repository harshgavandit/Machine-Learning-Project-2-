# Emotion Classification Notebook

## Project Title
Emotion Classification Notebook for Text-Based Emotion Detection

## Project Overview
This project is a simple machine learning notebook that reads a text dataset, cleans the text, and trains models to classify the emotion expressed in each sentence.

The project is built around a single notebook, `finalproject.ipynb`, and a labeled dataset file, `train.txt`.

## Problem It Solves
People write short sentences that express feelings, but it is not always easy for a computer to understand those feelings.

This project solves that problem by teaching a machine to recognize the emotion in a sentence, such as joy, sadness, anger, fear, love, or surprise.

Why it is useful:
- It helps turn unstructured text into meaningful emotion categories.
- It can be used for sentiment analysis, mood tracking, and emotion-aware applications.
- It provides a hands-on example of natural language processing (NLP) and machine learning.

## Key Features
- Loads a labeled text dataset from `train.txt`.
- Cleans and preprocesses text using lowercase conversion, punctuation removal, number removal, emoji filtering, and stop word removal.
- Splits data into training and test sets.
- Trains multiple models:
  - Multinomial Naive Bayes using bag-of-words features.
  - Multinomial Naive Bayes using TF-IDF features.
  - Logistic Regression using TF-IDF features.
- Evaluates model accuracy on held-out test data.

## How It Works
At a high level, the notebook follows these steps:
1. Read the dataset from `train.txt`.
2. Convert the emotion labels into numeric values.
3. Clean the text to remove irrelevant characters and words.
4. Split the data into training and testing groups.
5. Convert text into numeric features using vectorization.
6. Train one or more classification models.
7. Measure how well the models predict emotion labels.

## User Journey
A first-time user can follow this path:
1. Open the folder in a notebook environment.
2. Inspect `train.txt` to see the example sentences and emotion labels.
3. Open `finalproject.ipynb` to review the preprocessing and model training steps.
4. Run the notebook cells in order.
5. View the reported accuracy scores to understand model performance.
6. Optionally modify or extend the notebook with more data, new text cleaning, or additional models.

## Architecture & Technical Design
This project is not a multi-service application. It is a single research notebook with two main pieces:
- `train.txt`: a dataset containing sentences and emotion labels.
- `finalproject.ipynb`: a notebook that builds the machine learning workflow.

### Major Components
- `finalproject.ipynb`:
  - Data loading and inspection.
  - Text normalization and cleaning.
  - Label encoding.
  - Train/test split.
  - Feature extraction using CountVectorizer and TfidfVectorizer.
  - Model training with Multinomial Naive Bayes and Logistic Regression.
  - Accuracy evaluation.

- `train.txt`:
  - Raw data file with lines of text and emotion labels separated by semicolons.

### Data Flow
1. The notebook reads `train.txt`.
2. Each line is split into a text string and an emotion label.
3. Text is cleaned and normalized.
4. Labels are converted into numeric values.
5. The cleaned examples are converted into vectors.
6. Models are trained on the vectorized text.
7. Predictions are compared to the test labels.

## Technology Stack
| Technology | Role |
|---|---|
| Python | Main programming language for data processing and modeling |
| Jupyter Notebook (`.ipynb`) | Interactive analysis and model development |
| NumPy | Numerical operations and array handling |
| Pandas | Data loading and table-style data manipulation |
| Matplotlib / Seaborn | Data visualization libraries imported in the notebook |
| NLTK | Natural language processing utilities and stop words |
| scikit-learn | Machine learning algorithms, vectorizers, and evaluation |

## Project Structure
```
NLP-content/
├── finalproject.ipynb
├── train.txt
└── README.md
```

### File and Folder Purpose
- `finalproject.ipynb`: The main notebook containing code for data preprocessing, model training, and evaluation.
- `train.txt`: The training dataset with example sentences and their emotion labels.
- `README.md`: This documentation file.

## Database Design
This project does not use a database.

### Data File Design
- `train.txt` is a text dataset.
- Each row contains a sentence and a label separated by a semicolon (`;`).
- Example row:
  - `i didnt feel humiliated;sadness`

### Fields in `train.txt`
- `text`: The raw sentence that describes a feeling.
- `emotion`: The emotion label for that sentence.

## Setup & Installation
These steps let you run the notebook locally.

### Prerequisites
- Python 3.8 or newer installed.
- A Python environment or virtual environment.
- Jupyter Notebook or Jupyter Lab installed.

### Installation Steps
1. Open a terminal.
2. Navigate to the project folder:
   ```bash
   cd "g:\DL\NLP-content"
   ```
3. Create a virtual environment (recommended):
   ```bash
   python -m venv venv
   ```
4. Activate the virtual environment:
   - Windows PowerShell:
     ```powershell
     .\venv\Scripts\Activate.ps1
     ```
   - Windows Command Prompt:
     ```cmd
     .\venv\Scripts\activate.bat
     ```
5. Install libraries:
   ```bash
   pip install numpy pandas matplotlib seaborn nltk scikit-learn jupyter
   ```
6. Download NLTK data inside Python or the notebook:
   ```python
   import nltk
   nltk.download('punkt')
   nltk.download('stopwords')
   ```

## Usage Guide
### Running the Notebook
1. Start Jupyter Notebook from the project folder:
   ```bash
   jupyter notebook
   ```
2. Open `finalproject.ipynb` in the browser.
3. Run each cell in order.
4. Review the outputs and accuracy scores.

### Example Workflows
- Experiment with different text cleaning rules.
- Add new sample sentences to `train.txt`.
- Compare the performance of Naive Bayes vs Logistic Regression.
- Use the notebook to learn how emotion classification works.

## API Documentation
This project does not include APIs or web endpoints. It is a local research notebook.

## Screenshots & Visuals
There are no screenshots included in the repository.

Suggested visuals to add:
- A screenshot of the notebook running in Jupyter.
- A table or plot showing model accuracy results.
- An illustration of text preprocessing steps.

## Challenges & Solutions
### Challenge: Text is noisy and informal
Many sentences in `train.txt` contain contractions, punctuation, and informal language.

### Solution:
The notebook includes text cleaning to remove punctuation, numbers, and non-ASCII characters. It also removes common stop words before vectorization.

### Challenge: Emotion labels are text categories
The raw emotion labels are words like `sadness` and `joy`.

### Solution:
The notebook maps these emotion labels to numeric values so the machine learning model can learn from them.

## Future Improvements
- Add more labeled examples to improve model accuracy.
- Save the trained model to disk for re-use.
- Add a user interface for entering new sentences.
- Expand the label set and handle more subtle emotional states.
- Add more advanced NLP preprocessing such as lemmatization or word embeddings.

## Conclusion
This repository is a compact emotion classification project built around a Jupyter notebook and a text dataset. It shows how to clean text, build simple models, and evaluate emotion prediction. It is useful for learners, evaluators, and anyone who wants to understand a basic NLP workflow without needing complex infrastructure.

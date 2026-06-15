# Machine Learning Project: Heart Disease & Insurance Data Analysis

## Project Overview

This project contains two exploratory machine learning analyses using publicly available healthcare datasets. It is designed to help a non-technical reader understand how data related to heart disease and medical insurance costs can be cleaned, examined, and prepared for modeling.

The project is built as a pair of Jupyter notebooks that walk through:
- heart disease data analysis using `heart.csv`
- insurance cost analysis using `insurance.csv`

These notebooks demonstrate real-world data analysis tasks such as cleaning data, visualizing patterns, and preparing features for machine learning.

## Problem It Solves

Healthcare and insurance datasets often contain messy values, categorical labels, and patterns that are not obvious at first glance. This project helps translate raw healthcare data into a structured, easy-to-understand form.

It is useful because it:
- shows how to inspect and clean data before analysis
- reveals patterns in patient health and insurance costs
- prepares data for future predictive modeling
- demonstrates best practices for exploratory data analysis

## Key Features

- Exploratory Data Analysis (EDA) for two datasets
- Data cleaning to replace invalid or inconsistent values
- Visual charts for distribution and correlation analysis
- Encoding of categorical fields into numeric values
- Feature engineering to prepare columns for machine learning
- Correlation and statistical testing for feature selection

## How It Works

### High-Level Workflow

1. Load one of the dataset files (`heart.csv` or `insurance.csv`).
2. Inspect the data structure, missing values, and basic statistics.
3. Visualize distributions and relationships using plots.
4. Clean the data by handling invalid or duplicate values.
5. Convert categorical values into numeric format.
6. Scale numeric fields where appropriate.
7. Select the most meaningful features for modeling.

### User Journey

- A first-time user opens the project folder in a Jupyter or Python environment.
- They open `Heart.ipynb` to explore heart disease data.
- They open `insurance.ipynb` to explore health insurance charges.
- They run each notebook cell sequentially to reproduce the analysis.
- They review charts, tables, and preprocessing steps to understand the results.

## Architecture & Technical Design

This project is not a traditional web application. It is a data analysis project with the following main components:

- `Heart.ipynb`: notebook for heart disease dataset exploration and preprocessing.
- `insurance.ipynb`: notebook for health insurance dataset exploration and preprocessing.
- `heart.csv`: dataset containing clinical measurements and heart disease labels.
- `insurance.csv`: dataset containing personal and insurance cost details.
- `anaconda_projects/db/project_filebrowser.db`: metadata created by an Anaconda environment or IDE.

### Role of Each Component

- `Heart.ipynb`: performs data cleaning, visualization, and feature engineering for heart disease prediction.
- `insurance.ipynb`: performs data cleaning, visualization, categorical encoding, and feature selection for insurance cost analysis.
- `heart.csv`: source data with patient heart and clinical health variables.
- `insurance.csv`: source data with demographics, health factors, and insurance charges.
- `project_filebrowser.db`: system file created by the Anaconda project environment; not part of the core analysis.

## Technology Stack

- Python: primary language for data analysis.
- Jupyter Notebook: interactive environment for running and documenting analysis.
- pandas: data reading, cleaning, and transformation.
- seaborn: visualization, plotting distributions and relationships.
- matplotlib: plotting library used alongside seaborn.
- scikit-learn: preprocessing tools such as `StandardScaler`.
- scipy: statistical testing functions like `chi2_contingency`.
- sheryanalysis: a third-party EDA helper package used in the heart notebook.

### Why These Technologies

- `Python` is widely used for data science and machine learning.
- `Jupyter Notebook` allows readers to explore code, results, and commentary together.
- `pandas` is the standard library for working with CSV data.
- `seaborn` and `matplotlib` create visualizations that make patterns easier to understand.
- `scikit-learn` provides tools to prepare numeric data for models.
- `scipy` enables rigorous statistical tests for feature selection.

## Project Structure

```
Machine-Learning-Part-1/
├── .git/
├── .ipynb_checkpoints/
├── anaconda_projects/
│   └── db/
│       └── project_filebrowser.db
├── heart.csv
├── Heart.ipynb
├── insurance.csv
└── insurance.ipynb
```

### Important Files and Folders

- `.git/`: Git version control metadata.
- `.ipynb_checkpoints/`: temporary checkpoint files created by Jupyter.
- `anaconda_projects/db/project_filebrowser.db`: editor metadata for Anaconda/IDE navigation.
- `heart.csv`: heart disease dataset.
- `Heart.ipynb`: data analysis notebook for heart disease.
- `insurance.csv`: insurance cost dataset.
- `insurance.ipynb`: data analysis notebook for insurance costs.

## Database Design

This project uses CSV files instead of a database. The two datasets are:

### `heart.csv`

Important fields:
- `Age`: patient age
- `Sex`: male or female
- `ChestPainType`: type of chest pain
- `RestingBP`: resting blood pressure
- `Cholesterol`: serum cholesterol level
- `FastingBS`: fasting blood sugar indicator
- `RestingECG`: resting electrocardiogram result
- `MaxHR`: maximum heart rate achieved
- `ExerciseAngina`: exercise-induced angina indicator
- `Oldpeak`: ST depression induced by exercise
- `ST_Slope`: slope of peak exercise ST segment
- `HeartDisease`: target value indicating disease presence

### `insurance.csv`

Important fields:
- `age`: age of policyholder
- `sex`: male or female
- `bmi`: body mass index
- `children`: number of children covered by insurance
- `smoker`: yes/no smoker indicator
- `region`: geographic region
- `charges`: annual insurance charges

### Data Flow

- Data is loaded from CSV into a pandas DataFrame.
- The notebooks inspect and clean the raw values.
- Categorical values are converted to numeric form.
- Numeric columns are scaled where needed.
- Statistical tests are used to decide which features are most relevant.
- A final dataset subset is prepared for future model training.

## Setup & Installation

### Prerequisites

- Python 3 installed on your machine.
- A Python environment manager such as Anaconda, Miniconda, or virtualenv.
- Jupyter Notebook or JupyterLab installed.
- A code editor such as VS Code or Jupyter Notebook interface.

### Installation Steps

1. Open the project folder in your editor.
2. Create and activate a Python environment.
   ```bash
   python -m venv venv
   venv\Scripts\activate
   ```
3. Install required packages.
   ```bash
   pip install pandas seaborn matplotlib scikit-learn scipy jupyter
   ```
4. If the heart notebook uses `sheryanalysis`, install it as well.
   ```bash
   pip install sheryanalysis==0.1.0
   ```
5. Start Jupyter Notebook in the project folder.
   ```bash
   jupyter notebook
   ```
6. Open `Heart.ipynb` or `insurance.ipynb` in the browser and run the cells.

### Environment Variables

This project does not require any environment variables to run.

## Usage Guide

### How Users Interact with the Project

- Open the notebook file for the dataset you want to explore.
- Run the cells in order, from top to bottom.
- Review the charts and tables generated in each section.
- Observe how data cleaning changes the dataset and improves analysis.

### Example Workflows

1. **Heart Disease Analysis**
   - Run the first cells to load `heart.csv`.
   - Inspect the dataset shape and missing values.
   - Plot distributions for `Age`, `RestingBP`, `Cholesterol`, and `MaxHR`.
   - Replace zero values in clinical fields with mean values.
   - Use one-hot encoding to convert categorical fields.
   - Scale numeric columns using `StandardScaler`.

2. **Insurance Cost Analysis**
   - Load `insurance.csv` and inspect the dataset.
   - Check duplicates and missing values.
   - Map `sex` and `smoker` to numbers.
   - One-hot encode the `region` field.
   - Create a BMI category feature and run correlation analysis.
   - Use chi-squared testing for categorical feature selection.

## API Documentation

This project does not include a REST API or web service. It is built around interactive Jupyter notebooks and CSV datasets.

## Screenshots & Visuals

Add screenshots in this section if you want to show:
- the notebook interface with charts loaded
- key visualizations such as distribution plots and heatmaps
- tables showing cleaned datasets

For example, add images that show:
- `Heart.ipynb` after running the exploratory analysis section
- `insurance.ipynb` after feature engineering and correlation results

## Challenges & Solutions

### Challenges

- Working with raw healthcare data that contains zeros or invalid placeholder values.
- Converting categorical labels into a numerical format for machine learning.
- Establishing which features have the strongest relationship to the target variables.

### Solutions

- Invalid values such as zeros in `Cholesterol` and `RestingBP` were replaced with mean values.
- Categorical labels were encoded using mapping and one-hot encoding.
- Statistical tests and visual correlation analysis helped identify features worth retaining.

## Future Improvements

Potential enhancements for this project include:
- adding machine learning models to predict heart disease and insurance charges
- creating a clean script or package to run the full workflow automatically
- adding interactive dashboards using Streamlit or Dash
- saving the cleaned datasets to new CSV files for reuse
- adding README screenshots and output examples

## Conclusion

This project is a clear and practical demonstration of healthcare data exploration using Python. It helps readers understand how raw data can be analyzed, cleaned, and prepared for future machine learning tasks.

The notebooks make the work accessible to both technical and non-technical audiences by combining code, visualizations, and explanation in one place.

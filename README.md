# Teknofest Text Classification - Mammography Reports

This project uses a BERT model to classify Turkish mammography reports into BIRADS categories (1-5). 

## 1. Data Preprocessing and Cleaning:
- **Birads Extraction:** Extracts the BIRADS category from the last words of each report.
- **Text Normalization:** 
    - Converts Turkish characters to English equivalents.
    - Removes punctuation, extra spaces, and converts to lowercase.
    - Handles newline characters and hard spaces.
- **Text Cleaning:**
    - Removes single-character words (except specific allowed characters).
    - Removes the last two words of each report (often containing BIRADS info).
    - Identifies and removes the 25 most common words as stop words.
    - Removes conjunctions and abbreviations.

## 2. Spell Correction:
- Builds a vocabulary from the corpus of reports.
- Implements a spell correction function using a probabilistic approach (based on word frequency and edit distance).
- Corrects spelling errors in the text data.

## 3. Model Training:
- Splits the data into training, validation, and test sets.
- Initializes a BERT model (`dbmdz/bert-base-turkish-uncased`) for sequence classification with 5 output labels (BIRADS 1-5).
- Trains the model on the training data using Simple Transformers library.
- Saves the trained model.

## 4. Evaluation:
- Predicts BIRADS categories on the validation and test sets.
- Calculates accuracy, precision, recall, and F1 score for each set.
- Prints a classification report showing performance metrics for each BIRADS category.

## 5. Data Visualization:
- Creates a bar chart showing the distribution of BIRADS categories in the dataset.

## Files:

- `sequenceclassificationsimpletransformers.py`: Python script containing all the code for data preprocessing, model training, and evaluation.
- `outputs/`: Folder containing the saved trained BERT model.
- `README.md`: This file, providing a description of the project.

## Requirements:
- Python 3.7+
- pandas
- re
- collections
- os
- numpy
- datasets
- simpletransformers
- sklearn
- matplotlib

## How to Run:
1. Install the required packages.
2. Place your data file (`output.csv`) in the same directory as the script.
3. Run the `sequenceclassificationsimpletransformers.py` script.

## Notes:
- The script assumes the input data file (`output.csv`) has a "text" column containing mammography reports.
- You may need to adjust the file paths and parameters according to your needs.
- The script includes code for saving the trained model.

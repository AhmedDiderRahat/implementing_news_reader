---
Title: Implement newspaper scraper and create ML pipeline
Author: Rahat, A.D.
Date: July 23rd, 2022
---


## Introduction

This project is part of the Data Science Workflow course during the summer semester of 2022. The project's primary objective was to scrape news articles from the online version of a famous Bangladeshi newspaper, "The Daily Star" (https://www.thedailystar.net), and subsequently process the data for machine learning (ML) models. Additionally, the project aimed to apply ML models to categorize the articles.

## Project Parts
The project consisted of two major parts:

1. **Web Scraping and Data Processing:**
   - Web scraped news articles from "The Daily Star."
   - Cleaned and preprocessed the scraped data for ML model training.
   
2. **Machine Learning for Article Categorization:**
   - Implemented a Random Forest Classifier for article categorization.
   - Achieved an accuracy of approximately 36% on the categorization task.

# Web Scraping and Data Processing

## Data Collection

### Web Scraping
To gather data for this project, I performed web scraping on "The Daily Star" (https://www.thedailystar.net), a renowned Bangladeshi newspaper. The objective was to collect news articles from specific categories, including business, sports, and entertainment. I utilized Python for web scraping and leveraged the `requests` library to access web pages and the `BeautifulSoup` library for parsing HTML content.


### Data Cleaning and Preprocessing
Here's a step-by-step summary of the data cleaning and processing steps from the provided code:

**Step 1: Text Cleaning**
- The text data is first converted to lowercase to ensure uniformity.
- Newline characters ('\n') and carriage return characters ('\r') are replaced with spaces, and leading and trailing spaces are stripped.
- Extra spaces are removed to consolidate multiple spaces into a single space.
- Non-alphanumeric characters (punctuation, symbols, etc.) are removed to retain only words.

**Step 2: Stopword Removal**
- Stopwords, which are common words that do not carry significant meaning (e.g., "the," "and," "in"), are removed from the text.
- Tokenization is performed to split the text into individual words.

**Step 3: Tokenization and Stopword Removal**
- Tokenization is the process of splitting the text into individual words (tokens).
- The clean text is created by filtering out stopwords from the tokenized words.

**Step 4: Joining Clean Text**
- The clean text is joined back together into a single string.

**Step 5: Percentage of Text Removed**
- The code calculates and records the percentage of text removed during the cleaning process.

**Step 6: Label Encoding**
- The categories (in the 'category' column) are label-encoded, assigning a numeric label to each unique category.

**Step 7: Train-Test Split**
- The data is split into training and testing sets using the train_test_split function.
- 'X_train' and 'X_test' contain the clean text data.
- 'Y_train' and 'Y_test' contain the corresponding category labels.

**Step 8: TF-IDF Vectorization**
- Term Frequency-Inverse Document Frequency (TF-IDF) vectorization is applied to the text data.
- TF-IDF assigns numerical values to words based on their importance in the text corpus.
- Various parameters are configured for TF-IDF vectorization, including n-gram range, minimum document frequency, maximum document frequency, normalization, maximum features, and lowercase setting.

**Step 9: Feature Extraction**
- TF-IDF vectorization is applied to both the training and testing data to extract numerical features.
- The resulting features are stored in 'feature_train' and 'feature_test' arrays.

**Step 10: Label Encoding (Category Labels)**
- The category labels are encoded using label encoding.
- The encoded labels are stored in 'label_train' and 'label_test.'

**Step 11: Feature Shape**
- The code prints the shape (dimensions) of the feature objects, indicating the number of samples and features in the training and testing sets.


# Machine Learning for Article Categorization

## Model Implementation

### Random Forest Classifier

Here's a step-by-step summary of the machine learning part of the project:

**Step 1: Model Selection**
- A Random Forest Classifier model is chosen as the machine learning algorithm for this project.

**Step 2: Model Training**
- The selected model is trained using the training data (features and labels).
- The `model.fit()` method is used to fit the model to the training data.

**Step 3: Model Prediction**
- After training, the model is used to make predictions on the testing data.
- The `model.predict()` method is applied to the testing data to obtain predictions.


## Model Evaluation
Here's a step-by-step summary of the model evaluation of the project:

**Step 1: Accuracy Calculation**
- The accuracy of the machine learning algorithm is calculated by comparing the predicted labels to the actual labels in the testing data.
- The `accuracy_score()` function is used to calculate accuracy.
- The accuracy is expressed as a percentage.

**Step 2: Displaying Results**
- The calculated accuracy is printed, providing an evaluation of the model's performance.
- The accuracy score represents the percentage of correctly classified samples.

**Step 3: Summary Report**
- A classification report is generated to provide a detailed summary of the model's prediction performance.
- The classification report includes metrics such as precision, recall, F1-score, and support for each category.
- This report offers insights into the model's ability to classify articles into their respective categories.

---

Screencast is uploaded into drive: https://drive.google.com/file/d/1jAS26Z4bMbiMCWDMGay80BHP_NU0c3Pg/view?usp=sharing <br>
**Consent:** Anyone can use the code or data for learning/research purposes. <br> 
For any questions or further discussions about the project, please don't hesitate to reach out. <br>

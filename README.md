# SMS Spam Detection

This project involves building a spam detection model using the SMS Spam Collection dataset. The dataset contains 5,574 SMS messages in English, tagged as either 'ham' (legitimate) or 'spam'.

## Dataset Overview

- *Dataset Source:* [SMS Spam Collection Dataset on Kaggle](https://www.kaggle.com/uciml/sms-spam-collection-dataset)
- *Total Messages:* 5,574
- *Labels:* 
  - *Ham (Legitimate):* 4,825 messages
  - *Spam:* 747 messages

## Project Steps

1. *Data Preprocessing:*
   - The raw text messages were preprocessed by:
     - Replacing email addresses, URLs, money symbols, and phone numbers with specific tokens (emailaddr, httpaddr, moneysymb, phonenumbr).
     - Converting all characters to lowercase.
     - Removing all punctuations.
     - Stemming the words using PorterStemmer.
     - Removing stopwords.
   - The resulting cleaned text was stored in a corpus for further analysis.

2. *Feature Extraction:*
   - The CountVectorizer was used to convert the text corpus into a matrix of token counts.

3. *Label Encoding:*
   - The labels ('ham' and 'spam') were encoded as 0 and 1, respectively.

4. *Model Training and Evaluation:*
   - Two different classifiers were used to train the model:
     1. *Gaussian Naive Bayes*
        - *Accuracy:* 87.09%
        - *Confusion Matrix:*
          
          [[824, 125],
           [ 19, 147]]
          
        - *Classification Report:*
          
                      precision    recall  f1-score   support

                   0       0.98      0.87      0.92       949
                   1       0.54      0.89      0.67       166

            accuracy                           0.87      1115
           macro avg       0.76      0.88      0.80      1115
        weighted avg       0.91      0.87      0.88      1115
          
     2. *Decision Tree Classifier*
        - *Accuracy:* 97.13%
        - *Confusion Matrix:*
          
          [[944,   5],
           [ 27, 139]]
          
        - *Classification Report:*
          
                      precision    recall  f1-score   support

                   0       0.97      0.99      0.98       949
                   1       0.97      0.84      0.90       166

            accuracy                           0.97      1115
           macro avg       0.97      0.92      0.94      1115
        weighted avg       0.97      0.97      0.97      1115
          

## Conclusion

- The Decision Tree Classifier performed better with an accuracy of *97.13%, compared to **87.09%* with Gaussian Naive Bayes.

## Dependencies

- Python 3.x
- Libraries: pandas, numpy, nltk, sklearn, chardet, requests, io

## How to Run

1. Clone the repository:
   bash
   git clone https://github.com/yourusername/sms-spam-detection.git
   cd sms-spam-detection
   
2. Install the required dependencies:
   bash
   pip install -r requirements.txt
   
3. Run the notebook or script to train the model and make predictions.

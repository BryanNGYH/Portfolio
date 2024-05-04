---
title: "Spam-Ham Text Prediction"
description: "Using Natural Language Processing to classify spams"
dateString: April 2024
draft: false
tags: ["Python", "Pandas", "Numpy", "Scikit Learn", "nltk", "wordcloud", 'regex', "Naive Bayes", "Linear Support Vector Classifier", "Streamlit"]
showToc: false
weight: 202
cover:
    image: "projects/spam-ham-detection/cover.jpg"
--- 
### 🔗 [Github](https://github.com/BryanNGYH/Spam-Ham-Detection)

## Description
 In this project, I utilized Natural Language Processing(NLP) techniques to classify spam messages and texts. Furthermore, I built a simple web app using Streamlit which allows users to post their messages and identify spam messages.

## Tools and Resources
Python Version: 3.11\
Packages: Pandas, Numpy, Sklearn, nltk, wordcloud, Matplotlib, Seaborn, re, Streamlit, Pickle\
Dataset : [SMS Spam Collection Dataset](https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset)

## Data Preprocessing
To train the Machine Learning model, I preprocessed and cleaned the data to ensure the model can accurately predict with consistent performance. Here are the steps that I have taken:-

- Looked for missing entries
- Checked and removed duplicated data entries 
- Used data visualization and discovered that the data is highly skewed towards ham(non-spam) messages
- Label Encoded the 'spam' column
- Transformed the 'message' column
    - Replaced non-words characters into space
    - Converted all texts into lowercase letter
    - Split the texts
    - Normalized the texts using Lemmatization
- Feature-engineered 'message' columns to extract the number of characters before and after lemmatization in a given sentence  
- Generated wordcloud to visualize the frequent words that appeared in spam and ham messages
- Vectorized the processed texts for model training
 
 ![Spam Corpus](/projects/spam-ham-detection/spam_corpus.png)
 
 ![Word Cloud of Spam Messages](/projects/spam-ham-detection/spam_wordcloud.png)

 ![Ham Corpus](/projects/spam-ham-detection/ham_corpus.png)
 
 ![Word Cloud of Ham Messages](/projects/spam-ham-detection/ham_wordcloud.png)


## Model Building
80% of the dataset was used for training and the remaining 20% was used as a test set.

Here, I tested 2 classification models to predict spam messages and texts.

- **Linear Support Vector Classifier** - Chosen as it is powerful to address non-linear classification tasks and generalizes well in high dimensional spaces, in this case, we are dealing with texts.
- **Naive Bayes** - Assumed that the word vectors are independent and can accomplish high levels of accuracy. It is also a very fast method


## Model Performance
Both models had high scores on training sets.
        
1. **Linear Support Vector Classifier** - 1.0
2. **Multinomial Naive Bayes** - 0.99

On test sets, both models performed well too.
1. Linear Support Vector Classifier:-
    - Accuracy Score - 98.0
    - Precision Score - 96.3
    - Recall Score - 89.66
    - F1 Score - 92.86
    
2. Multinomial Naive Bayes:-
    - Accuracy Score - 97.58
    - Precision Score - 88.96
    - Recall Score - 94.48
    - F1 Score - 91.64

## Web Application
![Web App](/projects/spam-ham-detection/Web_App.png)

In the last step, I used the pickled model and users can access and interact with the model directly through the simple Web Application that was built with Streamlit.

Users can type or copy-paste messages in the typing space and the messages will be processed and vectorized in the background before prediction.
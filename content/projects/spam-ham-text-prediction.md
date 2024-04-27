---
title: "Spam-Ham Text Prediction"
description: "Using Natural Language Processing to classify spams"
dateString: April 2024
draft: false
tags: ["Python", "Numpy", "Scikit Learn", "nltk", "wordcloud", 'regex', "Streamlit"]
showToc: false
weight: 201
cover:
    image: "projects/spam-ham-detection/Web App.png"
--- 
### 🔗 [Github](https://github.com/BryanNGYH/Spam-Ham-Detection)


## Data Preprocessing
To train the Machine Learning model, we preprocess and cleaned the data to ensure the model can accurately predict with consistent performance. Here are the steps that I have took:-

- Looked for missing entries
- Checked and removed duplicated data entries 
- Used data visualization and discoevred that the data is highly skewed towards ham(non-spam) messages
- Label Encoded the 'spam' column
- Transformed the 'message' column
    - Replaced non words characters into empty space
    - Converted all texts into lowercase letter
    - Splitted the texts
    - Normalized the texts using Lemmetization
- Feature engineered 'message' columns to extract the number of characters before and after lemmetization in a given sentence  
- Generated wordcloud to visualize the frequent words appeared in spam and ham messages
- Vectorized the processed texts for model training
 
 ![Spam Corpus](https://github.com/BryanNGYH/Spam-Ham-Detection/blob/master/images/spam_corpus.png?raw=true)
 
 ![Word Cloud of Spam Messages](https://github.com/BryanNGYH/Spam-Ham-Detection/blob/master/images/spam_wordcloud.png?raw=true)

 ![Ham Corpus](https://github.com/BryanNGYH/Spam-Ham-Detection/blob/master/images/ham_corpus.png?raw=true)
 
 ![Word Cloud of Ham Messages](https://github.com/BryanNGYH/Spam-Ham-Detection/blob/master/images/ham_wordcloud.png?raw=true)


## Model Building
80% of the dataset was used for training and the remaining 20% was used as test set.

Here, I tested 2 classification model to predict spam messages and texts.

- **Linear Support Vector Classifier** - Chosen as it is powerful to address non-linear classification tasks and generalizes well in high dimensional spaces, in this case we are dealing with texts.
- **Naive Bayes** - Assumed that the word vectors are independent and can accomplish high levels of accuracy. It is also a very fast method


## Model Performance
Both model had high score on training sets.

    1. Linear Support Vector Classifier - 1.0
    2. Multinomial Naive Bayes - 0.99

On test sets, both models performed well too.

    1. Linear Support Vector Classifier :-
        - Accuracy Score - 98.07
        - Precision Score - 96.3
        - Recall Score - 89.66
        - F1 Score - 92.86
    
    2. Multinomial Naive Bayes :-
        - Accuracy Score - 97.58
        - Precision Score - 88.96
        - Recall Score - 94.48
        - F1 Score - 91.64
## Web Application
![Web App](https://github.com/BryanNGYH/Spam-Ham-Detection/blob/master/images/Web%20App.png?raw=true)

In the last step, I used the pickled model and users can access and interact with the model directly through the simple Web Application that was built with Streamlit.

Users can type or copy-paste messages in the typing space and the messages will be processed and vectorized in the background before prediction.
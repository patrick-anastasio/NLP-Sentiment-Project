# Gauging Sentiment of Emerging Technology on Twitter

![](Data/twitter-820x420-2.jpeg)

## Business Problem

Gauging sentiment of a market sector, company, or product is very helpful to investment analysis. An invetment firm is analyszing emerging technology and would like a predictive model that can analyze text data to classify the sentiment; poitive or negative. Being able to gauge overall sentiment will help in analysis of the sector and help them strategically place investments in the market.

## Data Understanding

The dataset consists of thousands of tweets from the SXSW festival pertaining to Apple and Google products. The tweets are labeled as positive, negative, no opinion, or "I can't tell." We will analyze the data from a binary classification standpoint and only keep the positive and negative classes.

The data is heavily imbalanced with positive tweets outnumbering the negative by a 6:1 ratio.

## Methods

Using NLP methods we will pre-process the data to get it ready for modeling.
> 1. First, we will clean the data by removing stop words, punctuation and other pieces of text that do not add value to the analysis such as numbers, and twitter slang.
> 2. Then we will tokenize he text with regular expressions
> 3. Next we will both stem and lemmatize the text separatley so that we can train models on both and see which is better.
> 4. Finally we will vectorize the text with both TF-IDF and Count vectorization so that we again can see which will provide a better model.
> 5. We will also look at removing mutually exclusive words from our training set to see if it imporoves our model.

We will split our dataset into training and testing data, and to handle the imbalance we with use SMOTE to provide a balanced training set. 

Once the data is ready for modeling we will build a baseline and then train several models with differing parameters, score them with cross validation, and generate predictions from our models to compare with the test set and attain our final results.

# Results

### While using mutually exclusive words in a Random Forest model showed some accuracy on predictions (negative: 65%, positive: 70%), It was not more accurate than our baseline model using Naive Bayes on the full text with lemmatization. Count Vectorization also prooved to be more accurate than using TF-IDF.

## Final Model:
> Multinomial Naive Bayes:      
> Lemmatized text with Count Vectorization           
>> Positive prediction accuracy: 88%             
> Negative prediction accuracy: 64%

### Interpretation:
Imbalanced data posed problems when testing the model
- Predicted the true positive class much better than the true negative class leading to a higher false positive rate

Words expressing positive sentiment like "great", and "awesome" appeared in both classes 
- Could lead to false negatives
- Did not appear in the mutually exclusive word models

# Conclusions

- ### Based on a general sense of the dataset the overwhelming sentiment was positive.

- ### This positive sentiment can be used in an overall investment strategy of emerging technologies

- ### This was a small dataset and more data is needed to improve the model
> - The use of synthetically produced data was used to balance the dataset         
> - With more data a downsampling technique could be employed instead

# Further Research

> - Gather more data to provide more balance for testing
> - Explore Neural Networking techniques and Word2Vec for modeling
> - Explore techniques for weighting specific words
> - Look at sentiment on an individual product level

For further information plase see the [Final Notebook](https://github.com/patrick-anastasio/NLP-Sentiment-Project/blob/main/Final%20Notebook.ipynb)

#### Repo Structure
```
├── Data                                       #datasets and visuals used in project
├── Final Noteboook.ipynb                      #code notebook
├── Notebook.pdf                               #pdf print out of code notebook
├── Presentation.pdf                           #non-technical stakeholder presentation slides
└── README.md                                  #the top-level README for reviewers of this project
```

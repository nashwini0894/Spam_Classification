# Spam_Classification
Classification of mails as Spam and Non Spam

# About the Dataset
The dataset considered for this model is equal number of spam and non-spam emails extracted from Ling-spam corpus. The extracted subset can be downloaded from here: https://www.dropbox.com/s/yjiplngoa430rid/ling-spam.zip

# About the Code

These are the following steps consider to build this model:
1. Preaparing the text data
2. Creating the word Dictionary
3. Creating a feature extraction process
4. Training the classifier
5. Test the model on the test set

## 1. Preparing the text data
The data-set is split into training set and test set containing 720 mails and 260 mails respectively, divided equally equally between spam and non-spam mails. The spam mails can be easily recognized, as they contain *spmsg* in its filename.

The first step of text mining is the text cleaning, removal of words from the document that do not contribute to the information we want to extract. The emails in Ling-spam corpus have already been preprocessed in 2 ways:

a) Removal of stop words: Words like "and", "or", "of", "the", etc are commonly used in all English sentences and do not play any active role in deciding the wether the emails are spam or non-spam, so these words have been removed.

b) Lemmatization: This is the process of grouping different inflected forms of a word so they can be analyzed as a single item. 

All that has to done here is to remove non-words like punctuations or special characters. We remove such words after creating a dictionary, convenient method becuase every such word has to be removed only once.

## 2. Creating the word dictionary
To create the dictionary of words and their frequnecy, we have utilized training set of 700 mails. The make_dictionary function creates the dictonary.

Once the dictionary is created, the absurd single characters in dictionary are removed. 

## 3. Creating a feature extraction process
Once the dictionary is ready, a word count vector is extracted. It contains the frequency of the words in the training file. 
The extract_feature function generates the feature matrix, where the number of rows denote the number of files of the traing set and columns denote the words of the dictionary.

## 4. Training the classifier
Here, we use the scikit-learn ML library for training classifiers. We have trained two models here, namely, Naive Bayes Classifier and Support Vector Machines


Once the classifiers are trained, performance of these models is tested on the test-set. We extract the word count vector for each mail in the test-set and predict its class with the trained Naive Bayes classifier and SVM model.


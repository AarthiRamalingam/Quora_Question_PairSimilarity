# Quora_Question_PairSimilarity

## Business Problem 

Quora is a place to gain and share knowledge—about anything. It’s a platform to ask questions and connect with people who contribute unique insights and quality answers. This empowers people to learn from each other and to better understand the world.

Over 100 million people visit Quora every month, so it's no surprise that many people ask similarly worded questions. Multiple questions with the same intent can cause seekers to spend more time finding the best answer to their question, and make writers feel they need to answer
multiple versions of the same question. Quora values canonical questions because they provide a better experience to active seekers and writers, and offer more value to both of these groups in the long term.

## Problem Statement 

-> Identify which questions asked on Quora are duplicates of questions that have already been asked.

-> This could be useful to instantly provide answers to questions that have already been answered.

-> We are tasked with predicting whether a pair of questions are duplicates or not.

## Real world/Business Objectives and Constraints

(1) The cost of a mis-classification can be very high.

(2) You would want a probability of a pair of questions to be duplicates so that you can choose any threshold of choice.

(3) No strict latency concerns.

(4) Interpretability is partially important.

## Data:  https://www.kaggle.com/c/quora-question-pairs

## Data Overview:  

- Data will be in a file Train.csv

- Train.csv contains 5 columns : qid1, qid2, question1, question2, is_duplicate

- Size of Train.csv - 60MB

- Number of rows in Train.csv = 404,290

## DataPoint

"id","qid1","qid2","question1","question2","is_duplicate"
"0","1","2","What is the step by step guide to invest in share market in india?","What is the step by step guide to invest in share market?","0"
"1","3","4","What is the story of Kohinoor (Koh-i-Noor) Diamond?","What would happen if the Indian government stole the Kohinoor (Koh-i-Noor) diamond back?","0"
"7","15","16","How can I be a good geologist?","What should I do to be a great geologist?","1"
"11","23","24","How do I read and find my YouTube comments?","How can I see all my Youtube comments?","1"

## Machine Leaning Problem

It is a binary classification problem, for a given pair of questions we need to predict if they are duplicate or not.

## Performance Metric 

-> log-loss : https://www.kaggle.com/wiki/LogarithmicLoss

-> Binary Confusion Matrix

## EDA 

Analysis on unique question and distribution of data points among labels

## Feature Engineering:

freq_qid1 = Frequency of qid1's
freq_qid2 = Frequency of qid2's
q1len = Length of q1
q2len = Length of q2
q1_n_words = Number of words in Question 1
q2_n_words = Number of words in Question 2
word_Common = (Number of common unique words in Question 1 and Question 2)
word_Total =(Total num of words in Question 1 + Total num of words in Question 2)
word_share = (word_common)/(word_Total)
freq_q1+freq_q2 = sum total of frequency of qid1 and qid2
freq_q1-freq_q2 = absolute difference of frequency of qid1 and qid2

## Preprocessing Texts

By Removing html tags, Punctuations, Performing stemming, Removing Stopwords and Expanding contractions etc

## Advanced Fature Extraction using Fuzzy

## Implementation of mean word2vec and TFIDF

## Models

Built logistics regression, SVM and XGBoost models

Are you curious on which model performs better? Scroll to the end and you will find it.











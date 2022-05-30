# Data-mining-and-visualization

#!/usr/bin/env python
# coding: utf-8

# # TF-IDF
# Natural Language Processing (NLP) is a sub-field of artificial intelligence that deals understanding and processing human language. In light of new advancements in machine learning, many organizations have begun applying natural language processing for translation, chatbots and candidate filtering.

# In[2]:


import pandas as pd
from sklearn.feature_extraction.text import TfidfVectorizer


# In[25]:






document0 ="Best data analytic programming language"
document1 =  "The python is the most comment programming language used for data analytics. "
document2 = "Most popular programming languages that use in data science are python and R programming."
document3 = "a lot of users used R programming "
document4 ="Best data analytics languages is Python "
document5 = "Python is an extremely popular general purpose."

#split so each word have their own string

document0 = document0.split(' ')
document1 = document1.split(' ')
document2 = document2.split(' ')
document3 = document3.split(' ')
document4 = document4.split(' ')
document5 = document5.split(' ')


# Machine learning algorithms cannot work with raw text directly. Rather, the text must be converted into vectors of numbers. In natural language processing, a common technique for extracting features from text is to place all of the words that occur in the text in a bucket. This aproach is called a bag of words model or BoW for short. It’s referred to as a “bag” of words because any information about the structure of the sentence is lost.

# In[26]:



total=  document0+document1+document2+document3+document4+document5
total


# In[4]:





# In[27]:


document0 = dict.fromkeys(total, 0)
for word in document1:
    document0[word] += 1


document1 = dict.fromkeys(total, 0)
for word in document1:
    document1[word] += 1
    
document2 = dict.fromkeys(total, 0)
for word in document2:
    document2[word] += 1
    
    
    
    
document3 = dict.fromkeys(total, 0)
for word in document3:
    document3[word] += 1
    
document4 = dict.fromkeys(total, 0)
for word in document4:
    document4[word] += 1  
    
    
document5 = dict.fromkeys(total, 0)
for word in document5:
    document5[word] += 1       


# Another problem with the bag of words approach is that it doesn’t account for noise. In other words, certain words are used to formulate sentences but do not add any semantic meaning to the text. For example, the most commonly used word in the english language is the which represents 7% of all words written or spoken. You couldn’t make deduce anything about a text given the fact that it contains the word the. On the other hand, words like good and awesome could be used to determine whether a rating was positive or not.
# 
# In natural language processing, useless words are referred to as stop words. The python natural language toolkit library provides a list of english stop words.

# In[7]:


from nltk.corpus import stopwords
stopwords.words('english')


# # Term Frequency (TF)
# The number of times a word appears in a document divded by the total number of words in the document. Every document has its own term frequency.
# <img src="tf.png">

# In[13]:


def computeTF(wordDict, total):
    tfDict = {}
    bagOfWordsCount = len(total)
    for word, count in wordDict.items():
        tfDict[word] = count / float(bagOfWordsCount)
    return tfDict


# In[28]:


tf0 = computeTF(document0, total)
tf1 = computeTF(document1, total)
tf2 = computeTF(document2, total)
tf3 = computeTF(document3, total)
tf4 = computeTF(document4, total)
tf5 = computeTF(document5, total)
#tfB = computeTF(numOfWordsB, bagOfWordsB)
#print(tf1)

pd.DataFrame([tf0, tf1, tf2, tf3, tf4, tf5])


# In[29]:


tf = pd.DataFrame([tf0, tf1, tf2, tf3, tf4, tf5])

tf.to_csv(r'computeTF.csv', index=False)


# # Inverse Data Frequency (IDF)
# The log of the number of documents divided by the number of documents that contain the word w. Inverse data frequency determines the weight of rare words across all documents in the corpus.
# <img src="idf.png">

# In[31]:


def computeIDF(documents):
    import math
    N = len(documents)
    
    idfDict = dict.fromkeys(documents[0].keys(), 0)
    for document in documents:
        for word, val in document.items():
            if val > 0:
                idfDict[word] += 1
    
    for word, val in idfDict.items():
        idfDict[word] = math.log(N / float(val))
    return idfDict


# In[ ]:





# In[35]:


idfs = computeIDF([tf0, tf1, tf2, tf3, tf4, tf5])
idfs



# Lastly, the TF-IDF is simply the TF multiplied by IDF.
# <img src="tfidf.png">

# In[12]:


def computeTFIDF(tfBagOfWords, idfs):
    tfidf = {}
    for word, val in tfBagOfWords.items():
        tfidf[word] = val * idfs[word]
    return tfidf


# In[38]:


tf0 = computeTF(tf0, total)
tf1 = computeTF(tf1, total)
tf2 = computeTF(tf2, total)
tf3 = computeTF(tf3, total)
tf4 = computeTF(tf4, total)
tf5 = computeTF(tf5, total)

df = pd.DataFrame([tf0, tf1, tf2, tf3, tf4, tf5])
df


# In[39]:


hey = df
hey

hey.to_csv(r'dftf.csv', index=False)


# In[14]:


vectorizer = TfidfVectorizer()
vectors = vectorizer.fit_transform([documentA, documentB])
feature_names = vectorizer.get_feature_names()
dense = vectors.todense()
denselist = dense.tolist()
df = pd.DataFrame(denselist, columns=feature_names)


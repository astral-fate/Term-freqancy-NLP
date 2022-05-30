# Data-mining-and-visualization

We have first implemented a python code, that has 5 documents, and takes query from user that has the following values:


User Query: Best data analytic programming language   
 
Document No.1: The python is the most comment programming language used for data analytics. 
Document No.2 :   Most popular programming languages that use in data science are python and R programming. 
Document No.3:  a lot of users used R programming  
Document No.4 : Best data analytics languages is Python  
Document No.5 : Python is an extremely popular general purpose. 


query = input("User Query: ")
document1 = "The python is the most comment programming language used for data analytics. "
document2 = "Most popular programming languages that use in data science are python and R programming."
document3 = "a lot of users used R programming "
document4 ="Best data analytics languages is Python "
document5 = "Python is an extremely popular general purpose."


For the sake of natural language process, we have converted the following strings into a dictionary, or a matrix, in order to help us applying the 6th requirements of information retravel


query = query.split(' ')
document1 = document1.split(' ')
document2 = document2.split(' ')
document3 = document3.split(' ')
document4 = document4.split(' ')
document5 = document5.split(' ')
total=  query+document1+document2+document3+document4+document5
print(total)




 
The output of printing the total strings will be as follows


 































After that we start to implement the Binary Term-Document Incidence, for the 6th strings   

Binary Term-Document Incidence is when we enter 1 if term occurs, and 0 if term doesn't occur
best	data	analytic	programming	language	the	python	is	most	comment	used	for	analytics	popular	languages	that	use	in	science	are	and	r	a	lot	of	users	an	extremely	general	purpose
1	1	1	1	1	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0
0	1	0	1	1	1	1	1	1	1	1	1	1	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0
0	1	0	1	0	0	1	0	1	0	0	0	0	1	1	1	1	1	1	1	1	1	0	0	0	0	0	0	0	0
0	0	0	1	0	0	0	0	0	0	1	0	0	0	0	0	0	0	0	0	0	1	1	1	1	1	0	0	0	0
1	1	0	0	0	0	1	1	0	0	0	0	1	0	1	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0
0	0	0	0	0	0	1	1	0	0	0	0	0	1	0	0	0	0	0	0	0	0	0	0	0	0	1	1	1	1























Term frequency 
TF = (Number of time the word occurs in the text) / (Total number of words in text) 

string	Best	data	analytic	programming	language	The	python	is	the	most	comment	used	for	analytics.	Most	popular	languages	that	use	in	science	are	and	R	programming.	a	lot	of	users
User 	0	0.019	0	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0	0	0	0	0	0	0	0	0	0	0	0	0	0
Doc1
	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019
Doc2
	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019
Doc3
	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019
Doc4
	0	0.019	0	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0	0	0	0	0	0	0	0	0	0	0	0	0	0
Doc5
	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019	0.019





 


Inverse Document Frequency (IDF)

Best	0.182321557
 data	0
 analytic	0.182321557
 programming	0
 language	0
 The	0
 python	0
 is	0
 the	0
 most	0
 comment	0
 used	0
 for	0
 analytics	0
 Most	0.182321557
 popular	0.182321557
 languages	0.182321557
 that	0.182321557
 use	0.182321557
 in	0.182321557
 science	0.182321557
 are	0.182321557
 and	0.182321557
 R	0.182321557
 programming.	0.182321557
 a	0.182321557
 lot	0.182321557
 of	0.182321557
 users	0.182321557
 analytics	0.182321557
 Python	0.182321557
 an	0.182321557
 extremely	0.182321557
 general	0.182321557
 purpose	0.182321557




 
•	TF-IDF 



Best	data	analytic	programming	language	The	python	is	the	most	comment	used	for	analytics.	 	Most	popular	languages	that	use	in	science	are	and	R	programming.	a	lot	of	users	analytics	Python	an	extremely	general	purpose.
0	6.35E-06	0	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0	0
6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06
6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06
6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06
6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06
6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06	6.35E-06







 
Cosine similarity is the degree between how varied two strings are. 

Bellow we used a function to calculate the ranking of the cosine between the document and the user query, it is 'Best analytical programming language'


import math
import re
from collections import Counter
WORD = re.compile(r"\w+")
def get_cosine(vec1, vec2):
    intersection = set(vec1.keys()) & set(vec2.keys())
    numerator = sum([vec1[x] * vec2[x] for x in intersection])

    sum1 = sum([vec1[x] ** 2 for x in list(vec1.keys())])
    sum2 = sum([vec2[x] ** 2 for x in list(vec2.keys())])
    denominator = math.sqrt(sum1) * math.sqrt(sum2)
    if not denominator:
        return 0.0
    else:
        return float(numerator) / denominator
def text_to_vector(text):
    words = WORD.findall(text)
    return Counter(words)
text1 = input("User query: ")
text2 =  "The python is the most comment programming language used for data analytics. "

vector1 = text_to_vector(text1)
vector2 = text_to_vector(text2)
cosine = get_cosine(vector1, vector2)
print("Cosine:", cosine)



The cosine ranking between the user query and the first document is:  


Cosine: 0.3872983346207417


The cosine ranking between the user query and the second document is: 


Cosine: 0.33541019662496846



The cosine ranking between the user query and the third document is: 


Cosine: 0.16903085094570328



The cosine ranking between the user query and the fourth document is: 


Cosine: 0.3651483716701107



The cosine ranking between the user query and the fifth document is:
 
Cosine: 0.0

The overall cosine ranking between the user query and all fifth document, following the bellow code is 0.0

import math
import re
from collections import Counter

WORD = re.compile(r"\w+")

def get_cosine(vec1, vec2, vec3,vec4, vec5, vec6):
    intersection = set(vec1.keys()) & set(vec2.keys())
    intersection = set(vec1.keys()) & set(vec3.keys()) 
    intersection = set(vec1.keys()) & set(vec4.keys())
    intersection = set(vec1.keys()) & set(vec5.keys())   
    intersection = set(vec1.keys()) & set(vec6.keys())       
    
    
    numerator = sum([vec1[x] * vec2[x] * vec3[x] * vec5[x] * vec5[x] * vec6[x]  for x in intersection])
    sum1 = sum([vec1[x] ** 2 for x in list(vec1.keys())])
    sum2 = sum([vec2[x] ** 2 for x in list(vec2.keys())])
    sum3 = sum([vec3[x] ** 2 for x in list(vec3.keys())])
    sum4 = sum([vec4[x] ** 2 for x in list(vec4.keys())])
    sum5 = sum([vec5[x] ** 2 for x in list(vec5.keys())])
    sum6 = sum([vec6[x] ** 2 for x in list(vec6.keys())])
    
    
    
    denominator = math.sqrt(sum1) * math.sqrt(sum2)
    denominator = math.sqrt(sum1) * math.sqrt(sum3)    
    denominator = math.sqrt(sum1) * math.sqrt(sum4)
    denominator = math.sqrt(sum1) * math.sqrt(sum5) 
    denominator = math.sqrt(sum1) * math.sqrt(sum6)     

    if not denominator:
        return 0.0
    else:
        return float(numerator) / denominator

def text_to_vector(text):
    words = WORD.findall(text)
    return Counter(words)


text1 = input("User query: ")
text2 =  "The python is the most comment programming language used for data analytics. "
text3 = "Most popular programming languages that use in data science are python and R programming."
text4 = "a lot of users used R programming "
text5 ="Best data analytics languages is Python "
text6 = "Python is an extremely popular general purpose."

vector1 = text_to_vector(text1)
vector2 = text_to_vector(text2)
vector3 = text_to_vector(text3)
vector4 = text_to_vector(text4)
vector5 = text_to_vector(text5)
vector6 = text_to_vector(text6)

cosine = get_cosine(vector1, vector2, vector3, vector4, vector5, vector6)

print("Cosine:", cosine)
 




 

Jaccard coefficient
We have used the following python function to calculate Jaccard coefficient

#fist doc
usr = input('user query')
doc_1 = usr
doc_2 = "The python is the most comment programming language used for data analytics."


def Jaccard_Similarity(doc1, doc2): 
    
    # List the unique words in a document
    words_doc1 = set(doc1.lower().split()) 
    words_doc2 = set(doc2.lower().split())
    
    # Find the intersection of words list of doc1 & doc2
    intersection = words_doc1.intersection(words_doc2)

    # Find the union of words list of doc1 & doc2
    union = words_doc1.union(words_doc2)
        
    # Calculate Jaccard similarity score 
    # using length of intersection set divided by length of union set
    return float(len(intersection)) / len(union)

doc_1 = "Best data analytic programming language "
doc_2 = "The python is the most comment programming language used for data analytics."

Jaccard_Similarity(doc_1,doc_2)

The Jaccard coefficient ranking between the user query and the first document is:  

 0.23076923076923078


The Jaccard coefficient ranking between the user query and the second document is:  

0.11764705882352941 




The Jaccard coefficient ranking between the user query and the third document is:  


0.09090909090909091



The Jaccard coefficient ranking between the user query and the fourth document is:  



0.2222222222222222


The Jaccard coefficient ranking between the user query and the fifth document is:  
 

0.0



---
layout: post
title:  "Trip to Prague"
date:   2018-06-01 11:29:08 +0800
categories: ICA NLP
---
#Trip to Prague

The lecture I presented during the conference was a shortened version, whereas I’ve prepared a lot on the technical aspect.
Today I will introduce you with something interesting about the technology I applied to this paper.

##Co-word analysis by word-embeddings
Traditionally, the co-word analysis usually achieved by building matrix. It’s powerful when the dataset is extremely small. Or the content you focus on are merely some specific words(So the others could be ignored). If you want to dig sth out from mass unstructured texts, the co-word matrix building task will become unachievable.Under this circumstance, another path should be developed. 
###From One-Hot to Word Embedding
No matter which approach do you choose , the first step of the computer-based text analysis is always to represent word by numbers.
There are two typical methods to do the word representation. The first one is ‘one hot’ representation. Generally speaking, the co-word matrix could be clustered as a kind of one-hot representation. Unfortunately, this method can not present the structure of texts. It will cause the ‘word gap’ and the ‘curse of dimensionality’. It’s high dimensional and the synonyms within texts couldn’t be presented.
If you want to represent the following sentence:
`	“Python is the most beautiful programming language on Earth.”`
	
Each word in this sentence will be marked by a specific number.
	
	‘Python’: 1000000000
	‘is’:     0100000000
	‘the’:    0010000000
	‘most’:   0001000000
	 ……
	‘Earth’:  0000000001
Imagine you need to analyze texts with millions of words. Definitely disaster isn’t it?
###Distributional Representation
Over the past half century, the statistical based method has become the main stream of the NLP domain.  
In 1954,  the distributional hypothesis was proposed by [Harris](https://www.tandfonline.com/doi/pdf/10.1080/00437956.1954.11659520). He suggested that the word sharing similar contexts may be synonyms.  3 years later, Firth improved this hypothesis, he suggests that ‘a word is characterized by the company it keeps ’. These concepts are the basis of the current statistical based NLP works.
The distributional representation approach believes that the words around the keywords could describe the texts. Each word could be represented by a bunch of  numeric numbers(Data scientists call it word vector or word embedding). 
Assuming we use multiple variables to describe words.
![](word2vec_neurons.png)
And Word2Vec is the most famous DR algorithm.
Word2Vec is a tool training word embeddings. It’s powerful and user friendly.  One of the most famous explanation of word2vec is this:
queen by king is equal to woman by man.
![](word2vec.png)

If we applied this tool dealing with small datasets like what we’ve done in this research, we will get the co-word network. 
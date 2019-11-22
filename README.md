Abstract: Text summarization solves the problem of condensing information into a more compact form,
while maintaining the important information in the text. The methods of automatic text
summarization fall into two primary categories: extractive and abstractive. A common approach
of extractive summarization involves selecting the most representative sentences that best cover
the information expressed by the original text based on a ranking of sentences by relevance. A
popular method of abstractive text summarization is using an encoder-decoder structure, which
generates a latent factor representation of the data and decodes it to generate a summary. The goal of this project is to summarize the news articles of different categories for the research purpose where human subjects are involved to make decision based on the summary of the news.

Approaches and Methodology:

Extractive Summarization: 
For extractive summarization, I used the TextRank algorithm, which is based on Google’s PageRank algorithm. TextRanks works by transforming the text into a graph. It regards words as vertices and the relation between words in phrases or sentences as edges. Each edge also has different weight. When one vertex links to another one, it is basically casting a vote of importance for that vertex. The importance of the vertex also dictates how heavily weighted its votes are. TextRank uses the structure of the text and the known parts of speech for words to assign a score to words that are keywords for the text.

•	The first step would be to concatenate all the text contained in the articles
•	Then split the text into individual sentences
•	In the next step, we will find vector representation (word embeddings) for each and every sentence
•	Similarities between sentence vectors are then calculated and stored in a matrix
•	The similarity matrix is then converted into a graph, with sentences as vertices and similarity scores as edges, for sentence rank calculation
•	Finally, a certain number of top-ranked sentences form the final summary


Abstractive Text Summarization:

First, we need to preprocess the data by constructing an embedding of the text. Embedding
the input converts the text into numbers, a more interpretable numerical representation of the
data for the encoder-decoder network to work with.

The encoder-decoder model is composed of multiple recurrent neural networks, one of
which works as an encoder, and one as a decoder. The encoder converts an input document into a
latent representation (a vector), and the decoder reads the latent input, generating a summary as it
decodes. With encoder decoder structures, issues to consider include determining how to set the
focus on the import sentences and keywords, how to handle novel or rare words in the document,
how to handle incredibly long documents, and how to make summaries readable and flexible
with a large vocabulary.


References:
1.	https://arxiv.org/abs/1908.08345v2
2.	https://arxiv.org/abs/1905.03197v3
3.	https://dl.acm.org/citation.cfm?id=1599168
4.	https://www.aclweb.org/anthology/E99-1011/
5.	https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&ved=2ahUKEwid3vbqkf3lAhUHQ60KHdruDjYQFjAAegQIBBAC&url=https%3A%2F%2Fcyberleninka.org%2Farticle%2Fn%2F1210912.pdf&usg=AOvVaw1bgbfEqCT1AbRI2WhNOtAX
6.	http://www.rgnpublications.com/journals/index.php/jims/article/view/760

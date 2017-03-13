# Amazon-Review-Classification-with-KNN
Nearest Neighbor Classification algorithm

###Approach 1:###
Accuracy: 0.5434
Libraries used:​ numpy, scipy, nltk, heapq, string, collections
Method of choice:
Cosine_similarity with ​ CSR matrix​ for Training and Test data
Number of features considered: ​ 6357

Training data: [nrows 18506, ncols 6357, nnz 741757]
Test data: [nrows 18506, ncols 6357, nnz 739621]

Steps:
1. Read files train.dat, test.dat: we create a linesOfTrainData and linesOfTestData
2. After that we cleaned the data,
	a. With Lower case conversion
	b. Removing stem words
	c. Remove punctuation
	d. Removing numbers
3. After that calculation for featureList is done: intersection of unique words from linesOfTrainData and unique words from linesOfTestData is Considered for this.
4. Now we calculated the CSR matrix from both linesOfTestData and linesOfTrainData based on feature list.
5. L2 norms are calculated for the CSR matrices
6. cosineSimilarityValue is calculated with, function cosine_similarity(vt,vs).
7. For given number of K, we identified the nearest neighbours.
8. And for those index values we checked if we have +1 or -1 in given list of training data.
9. And average of max(count(+1), count(-1)) is written on format.dat


###Approach 2:###
Accuracy: 0.7459
Libraries used:​ sklearn, numpy, scipy, nltk, heapq, string, collections
Method of choice:
Cosine_similarity with ​ CountVectorizer​ for Training and Test data
Number of features considered: ​ 23398
Steps:
1. Read files train.dat, test.dat: we create a linesOfTrainData and linesOfTestData
2. Initialize CountVectorizer(analyzer='word', lowercase = True, stop_words='english')
3. Fit_transform linesOfTrainData
4. Transform linesOfTestData
5. cosineSimilarityValue is calculated with, function cosine_similarity(vt,vs).
6. For given number of K, we identified the nearest neighbours.
7. And for those index values we checked if we have +1 or -1 in given list of training data.
8. And average of max(count(+1), count(-1)) is written on format.dat

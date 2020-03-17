#                          Deep Mixture of Variational Auto Encoder for Modeling Text
authors are removed for double blind review 
***

In this repository we present DLVMM(Deep Latent Variational Mixture Model),  a new unsupervised framework based on a mixture of deep latent graphical models to represents texts
### Requirements
1. Python 2.7
2. Numpy 1.65


### Datasets already used for text representation 

|name | task | vocabulary | size | classes  |
|----------	|------------------------------	|-----------:|----------:|:-----------:|
|[CR](https://github.com/davidsbatista/Aspect-Based-Sentiment-Analysis/tree/master/datasets/CR)  | User review polarity | 5176 | small | 2 |
|[HSTW](https://github.com/zeerakw/hatespeech)  | Hate speech detect| 23739 | large |3  |
|[PO](https://www.cs.cornell.edu/people/pabo/movie-review-data/rt-polaritydata.tar.gz)| Sentece polarity | 18179| large |  2 |
|[SIM](https://github.com/hallr/DAT_SF_19/blob/master/data/yelp_labelled.txt)  | Movie and TV Review | 1000 | small|  2|
|[YR](https://github.com/hallr/DAT_SF_19/blob/master/data/yelp_labelled.txt)  | Food review polarity | 1000| small| 2|
|[SUBJ](http://www.cs.cornell.edu/people/pabo/movie-review-data/rotten_imdb.tar.gz) | Subjectivity and objectivity | 18179 | large | 2 |
|[AR](https://github.com/hallr/DAT_SF_19/blob/master/data/yelp_labelled.txt)  | User product review  | 1000| small | 2  |
|[QTS](http://cogcomp.org/Data/QA/QC/)  | Question Answering  | 16504 | small | 6  |
|[IM](https://drive.google.com/file/d/0B8yp1gOBCztyN0JaMDVoeXhHWm8/)  | Movie and TV Review | 74337| large| 2 | 

### Input Data
DLVMM receive as input any sequence of strings(sentences), each string of trainning corpus will be map to a vector.
Each file should have one sentence per line as follows (space delimited): \
`...`\
`weaknesses minor feel layout remote control show complete file names mp3s`\
`normal size sorry ignorant way get back 1x quickly` \
`many disney movies n play dvd player` \
`...`


###  Performance of classifiers with trained embeddings
We compare the quality of the embeddings obtained with DLVMM to the following word embeddings baseline techniques: Word2Vec, Glove, Bayesian SkipGram and FastText. The embeddings were trained on the specific dataset whose sentences we want to classify.

IM             |  CR|  HSTW
:-------------------------:|:-------------------------:|:-------------------------:
![Figure 1 ](https://github.com/DiVeWord/DLVMM/blob/master/figs/q6.eps  "Title") |  ![Figure 1 ](https://github.com/DiVeWord/DLVMM/blob/master/figs/q5.eps  "Title")|![Figure 1 ](https://github.com/DiVeWord/DLVMM/blob/master/figs/q4.eps "Title")
PO             |  YR|  QS
![Figure 1 ](https://github.com/DiVeWord/DLVMM/blob/master/figs/q2.eps "Title") |![Figure 1 ](https://github.com/DiVeWord/DLVMM/figs/q3.eps "Title")|![Figure 1 ](https://github.com/DiVeWord/DLVMM/figs/q6.eps "Title")

(



![Figure2](https://github.com/DiVeWord/DLVMM/blob/master/figs/q2.png"Title")

![Figure4](https://github.com/DiVeWord/DLVMM/blob/master/figs/q6.eps)
Our results showed that DiVe overcome four popular word embedding, namely Word2Vec, Glove, FastText e Bayesian Skip Gram, and more than 9 datasets.

In addition, we conducted a hypothesis test on whether DiVe’s model is in fact different from others, based on McNemar’s test to know more about this test check https://towardsdatascience.com/statistical-tests-for-comparing-machine-learning-and-baseline-performance-4dfc9402e46f and https://machinelearningmastery.com/statistical-significance-tests-for-comparing-machine-learning-algorithms/. In next figures we show the heat maps of p-values for all combinations of DiVe and classifiers and Word2Vec or Glove and classifiers, respectively, in the PO
dataset. Comparing the two heat maps, we observe that there are a lot of values < 0.05 that deny the null hypothesis, besides that, we plot the p-values from McNemar’s test as a CDF for all word embeddings, separated by dataset. We
can see that 2 out of 9 datasets (AR and YR) have < 40% of p-values < 0.05. In the remaining datasets, there are ≥ 60%
of p-values < 0.05.

Glove             |  Word2Vec|  All baselines for all datasets
:-------------------------:|:-------------------------:|:-------------------------:
![Figure 1 ](https://github.com/DiVeWord/DLVMM/blob/master/figs/heatglove.png  "Title") |  ![Figure 1 ](https://github.com/DiVeWord/DLVMM/blob/master/figs/heatw2v.png  "Title")|![Figure 1 ](https://github.com/DiVeWord/DLVMM/blob/master/figs/cdfs.png "Title")

### Reference

Please make sure to cite the papers when its use for represents word similarity by word embedding.

Please cite the following paper if you use this implementation:\
`
@InProceedings{?,`\
  `author    = {removed for double blind review},`\
  `title     = {Deep Mixture of Variational Auto Encoder for Modeling Text},`\
  `booktitle = {ACL'20},`\
  `year      = {2020} }`

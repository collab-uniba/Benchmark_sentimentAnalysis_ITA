# Benchmark_sentimentAnalysis_ITA

This repository contains the notebooks useful for carrying out the Sentiment Analysis task on tweets in Italian using two approaches: Lexicon-based and BERT-based.
The objective of this project is to compare the two approaches and benchmark their performance to understand in which contexts they can be best used.

Notebooks cover the following steps:

- Data extraction
- Creation of the gold standard
- Explorative Data Analysis
- Creation of the reference lexicon
- Implementation of the Lexicon-based approach
- Implementation of the BERT-based approach

The first dataset useful for this project was obtained through the Twitter API and amount to almost 2k tweets relating to the public administration. The second dataset, SentiPolc, can be found [here](http://www.di.unito.it/~tutreeb/sentipolc-evalita16/data.html) together with all useful informations.

In the data/processed folder there are two files relating to the gold standard, one of the two is deprived of the columns associated with the text of the tweets so that it can also be used in contexts where the diffusion of this type of textual data is limited.

Each notebook in this repository can be reproduced individually using cloud computing platforms such as Google Colab, the direct links to the notebooks and a brief description of them are defined below:

- [Twitter](https://colab.research.google.com/drive/1EpQHIuFtSFtjQ06WTFhQMlRGqTyzbtnL?usp=sharing)

The notebook allows, after submitting a token enabled by Twitter for access for academic research, to submit a query to the Twitter Full-Archive Search endpoint and to save the result in a csv file.
This result represents the raw data on which this project lays its foundations. The notebook provides further information on how to obtain this type of token and, in the event that a token not enabled to access the endpoint of interest is entered, the notebook terminates by not returning any tweets.

- [Datasets](https://colab.research.google.com/drive/1q8Fa1Nh1q6fbbgptrrY5euzc2DSC_ReE?usp=sharing)

The notebook takes care of importing the raw data produced by the queries made to the Twitter endpoint and carrying out an initial analysis and cleaning by removing the retweets, useless for the purposes of computation. Two emoji lists, positive and negative, are then defined and the tweets are silver labeled. Taking note that the neutral tweets represent the majority class, an undersampling of this class is carried out to balance the dataset. Finally, for the purposes of the manual annotation phase, we proceed to create two samples of the final dataset to be submitted to the annotators.

- [Annotation_Utility](https://colab.research.google.com/drive/10AWvfdWDYz6nGSyKuzmD8c3EeidZqOnT?usp=sharing)

This notebook is useful for understanding the progress of the two annotation steps. The metrics used are the Cohen's kappa and the observed agreement.

- [EDA](https://colab.research.google.com/drive/1jj8m46xeX9WtatzExj9NRkCiqZVMLr1z?usp=sharing)

In this notebook we are concerned with data exploration. For this purpose, the temporal information relating to manually annotated tweets was integrated and the text of the tweets was subjected to a cleaning phase. These operations made it possible to extract ngrams (bigrams and trigrams) and to visualize the distribution of tweets relating to the different sentiment classes over the months.

- [Lexicon](https://colab.research.google.com/drive/1gGnxrbE-dRtNPEgEoaeaHu4c_5WnK8Yr?usp=sharing)

This notebook allows you to import the lexical resource chosen within this project, Sentix, and to make some modifications useful for computational purposes. In this regard, a new polarity value was defined, the polysemic lemmas were managed and finally a mapping of the polarity of the lemmas was carried out to obtain values that can be submitted to the SentiStrenght tool. These operations made it possible to create a custom version of Sentix..

- [SentiStrenght-it](https://colab.research.google.com/drive/15THF6nvL6H_gLpIs7HaRixHI5AIztS4d?usp=sharing)

This notebook, after importing the custom lexicon built in the previous notebook, allows you to modify and integrate the SentiStrenght support files. Subsequently the text of the tweets belonging to the two datasets considered is processed with SpaCy in order to extract for each token its basic lemma and its POS tag in order to find a correspondence in the custom lexicon. Once this preparation phase has been completed, the tweets are submitted to SentiStrenght and the results are extracted.

- [SentiStrenght-eng](https://colab.research.google.com/drive/1nffasyDnP_433ey9QH52MfgnCinpetrA?usp=sharing)

This notebook takes care of importing the translated versions in English of the two considered datasets and cleaning up the tweets. Once this preparation phase has been completed, the tweets are submitted to SentiStrenght in its original version (based on the support files for the English language) and the results are obtained.

- [Bert](https://colab.research.google.com/drive/104Y1bUG1ZxCFlWNoamNJzrtR6oIIjVBl?usp=sharing)

This notebook allows you to extract, from the two reference datasets, information relating to the presence or absence of each sentiment in order to train a binary classifier, in order to be able to compare its performance with those obtained through SentiStrenght. Once the data has been reported in the desired format, they have been converted into the .spacy format useful for the execution of the pipeline. Finally, the configuration file was defined, which is useful for setting the hyperparameters and for the actual training of the chosen model.

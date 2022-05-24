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

The first dataset useful for this project was obtained through the Twitter API and amount to almost 2k tweets relating to the public administration. The second dataset, SentiPolc, can be found [here](http://www.di.unito.it/~tutreeb/sentipolc-evalita16/data.html) together with all useful information.

In the data/processed folder there are two files relating to the gold standard, one of the two is deprived of the columns associated with the text of the tweets so that it can also be used in contexts where the diffusion of this type of textual data is limited.

Each notebook in this repository can be reproduced individually using cloud computing platforms such as Google Colab, direct links to notebooks are defined below:

- [Twitter](https://colab.research.google.com/drive/1EpQHIuFtSFtjQ06WTFhQMlRGqTyzbtnL?usp=sharing)
- [Datasets](https://colab.research.google.com/drive/1q8Fa1Nh1q6fbbgptrrY5euzc2DSC_ReE?usp=sharing)
- [Annotation_Utility](https://colab.research.google.com/drive/10AWvfdWDYz6nGSyKuzmD8c3EeidZqOnT?usp=sharing)
- [EDA](https://colab.research.google.com/drive/1jj8m46xeX9WtatzExj9NRkCiqZVMLr1z?usp=sharing)
- [Lexicon](https://colab.research.google.com/drive/1gGnxrbE-dRtNPEgEoaeaHu4c_5WnK8Yr?usp=sharing)
- [SentiStrenght-it](https://colab.research.google.com/drive/15THF6nvL6H_gLpIs7HaRixHI5AIztS4d?usp=sharing)
- [SentiStrenght-eng](https://colab.research.google.com/drive/1nffasyDnP_433ey9QH52MfgnCinpetrA?usp=sharing)
- [Bert](https://colab.research.google.com/drive/104Y1bUG1ZxCFlWNoamNJzrtR6oIIjVBl?usp=sharing)

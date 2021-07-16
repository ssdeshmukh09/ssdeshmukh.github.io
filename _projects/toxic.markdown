---
layout: page
title: Making internet safer
description: Detecting toxicity in social media platforms
img: /assets/img/capsuleintro.jpg
importance: 1
category: language
---
<img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/capsuleintro.jpg' | relative_url }}" alt="" title="example image"/>
<div class="caption">
    Social media
</div>

Internet has enabled people to communicate and learn from each other. Learning from others and at the same time expressing ones feeling and opinions to others requires a consoling and comforting environment. Online hate, abuse, toxicity shuns people from opening up and taking full advantage of the opportunities that online communication provides. This is observable on social media platforms like Facebook, Twitter and even Quora. A subtle form of toxicity in observed on Quora in the form of insincere questions. Insincere questions are those founded upon false premises, or that intend to make a statement rather than look for helpful answers.

With respect to label taxonomy, each comment can be classified into buckets:
- safe
- insincere
- toxic
- severe toxic
- obscene
- threat
- insult
- identity hate

Kaggle hosted two challenges for detecting online toxicity. The first one in 2018 was organised by [Jigsaw, Google](https://jigsaw.google.com/) and the second in 2019 was organised by [Quora](https://www.quora.com/about). I participated in both of the challenges, and it generated some great solutions. Competitions links: [Google](https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge), [Quora](https://www.kaggle.com/c/quora-insincere-questions-classification).

In brief, the solution generally involved combination of LSTM/GRU/CNN/Boosting architectures with GLoVe/FastText/Paragram/BPE embeddings and variety of learning strategies. The main challenges were the text length, slangs being used, with misspelling, special characters, and innuendos. Hence a lot of effort went into preprocessing the data. I recommend checking out the challenge pages for the solution descriptions. 

The solution we developed was a combination of all of the above. A interesting model we developed was [Recurrent Capsule Networks](https://ieeexplore.ieee.org/abstract/document/8722433). It was the best performing single model across the competition. Our insight was, internal data representation of a CNN does not take into account important spatial hierarchies between simple and complex objects which in NLP implies that a presence of word will have more impact on the classification rather than their relative orientation to each other. Its based on [capsule networks](https://arxiv.org/pdf/1710.09829.pdf) introduced by Hinton in 2017 for computer vision tasks. We found integrating RNN with capsule networks works very well to detect toxic sarcasm and innuedos. 

We tested the architecture on standard benchmark datasets which cover various text classification tasks such as news categorization and sentiment analysis, to demonstrate the generalizability of the model irrespective of the domain.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/capsuletable.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/capsuletable2.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    On the left shows datasets used for model evaluate. On the right, are the results on standard datasets. All numbers are AUC ROC scores.
</div>

Recently there have been challenges to tackle social media toxicity in multimodal data. If this area interests you, this dataset is a good place to start: [facebook hateful memes challenge](https://ai.facebook.com/blog/hateful-memes-challenge-and-data-set/)



## References
[1] "Tackling Toxic Online Communication with Recurrent Capsule Networks", Soham Deshmukh, Rahul Rade- CICT 2018 <br>

---
layout: post
date: 2018-04-17 00:00
thumbnail:
title: Practical Considerations of Decentralized Training
---

## What is Decentralized Training?
A variety of modern AI products are powered by cutting-edge machine learning (ML)
technologies, which range from face detection and language translation installed
on smartphones to voice recognition and speech synthesis used in virtual
assistants such as Amazon Alexa and Google Home. Therefore, the development of such AI
products typically necessitates a large-scale data which are essential to train
high-performance ML models like a deep neural network. One
common way to collect large-scale data is crowdsourcing, namely, asking people
in the world to provide own data. However, crowd-sourcing is not always useful
when we are interested in collecting human activity data like [first-person
videos](/fpv_overview.html) and other life-logging videos; such data often
include private moments of people in their everyday life and could be used to
compromise their privacy.

So how can we leverage a large amount of distributed (and private) data for machine
learning? A <i>decentralized training</i> is arguably one of the most promising
solutions. Unlike a standard centralized training that stores all training data
on a single server or multiple well-organized servers, the decentralized
training asks people having data to download a trainable model, update it using
own data, and upload the new model parameters to a server. The server then
aggregates updates sent from the people to obtain a better trained model. By
iterating this training cycle one can obtain a high-performance model that has
been trained on a very-large and distributed data. One of the emerging
frameworks to enable the decentralized training is [Federated
Learning](https://research.googleblog.com/2017/04/federated-learning-collaborative.html)
that allows one to train a deep neural network using tailored update techniques
called Federated Averaging.

We are interested in how to make decentralized training frameworks more
practical. In particular, we are interested in the model upload procedure in 
Federated Learning frameworks and studying how it can be more secure and
efficient.





## Our Projects

### Privacy-Preserving Training with Homomorhic Encryption (ICCV'17)
<img class="img-responsive" src="/images/ybks-arxiv2017.png">
We propose a privacy-preserving framework for learning visual classifiers by
leveraging distributed private image data. This framework is designed to
aggregate multiple classifiers updated locally using private data and to ensure
that no private information about the data is exposed during its learning
procedure. We utilize a homomorphic cryptosystem that can aggregate the local
classifiers while they are encrypted and thus kept secret. To overcome the high
computational cost of homomorphic encryption of high-dimensional classifiers, we
(1) impose sparsity constraints on local classifier updates and (2) propose a
novel efficient encryption scheme named doubly-permuted homomorphic encryption
(DPHE) which is tailored to sparse high-dimensional data. DPHE (i) decomposes
sparse data into its constituent non-zero values and their corresponding support
indices, (ii) applies homomorphic encryption only to the non-zero values, and
(iii) employs double permutations on the support indices to make them secret.
Our experimental evaluation on several public datasets demonstrates that the
proposed approach significantly outperforms other privacy-preserving methods and
achieves comparable performance against state-of-the-art visual recognition
methods without privacy preservation.

- Ryo Yonetani, Vishnu Naresh Boddeti, Kris M. Kitani, Yoichi Sato: "Privacy-Preserving Visual Learning Using Doubly Permuted Homomorphic Encryption", International Conference on Computer Vision **(ICCV)**, 2017 [[cvf page]](http://openaccess.thecvf.com/content_iccv_2017/html/Yonetani_Privacy-Preserving_Visual_Learning_ICCV_2017_paper.html) [[DPHE Demo]](https://github.com/yonetaniryo/DPHE-demo)

### Federated Learning for Resource-Constrained Clients in Mobile Edge
<img class="img-responsive" src="/images/ny_fl.png">
This work aims to extend Federated Learning (FL) to work with heterogeneous
clients in a practical cellular network. The FL protocol iteratively asks random
clients to download a trainable model from a server, update it with own data,
and upload the updated model to the server, while asking the server to aggregate
multiple client updates to further improve the model. While clients in this
protocol are free from disclosing own private data, the overall training process
can become inefficient when some clients are with limited computational
resources (i.e., requiring longer update time) or under poor wireless channel
conditions (longer upload time). Our new FL protocol, which we refer to as
FedCS, mitigates this problem and performs FL efficiently while actively
managing clients based on their resource conditions. Specifically, FedCS solves
a client selection problem with resource constraints, which selects the maximum
possible number of clients who can complete the FL's download, update, and
upload steps within a certain deadline. This selection strategy results in the
server aggregating as many client updates as possible and accelerating
performance improvement in ML models (e.g., classification accuracy.) We
conducted an experimental evaluation using publicly-available large-scale image
datasets to train deep neural networks on MEC environment simulations.  The
experimental results show that FedCS is able to complete its training process in
a significantly shorter time compared to the original FL protocol. 

- Takayuki Nishio and Ryo Yonetani: "Client Selection for Federated Learning with Heterogeneous Resources in Mobile Edge", arXiv:1804.08333, 2018 [[arXiv preprint]](https://arxiv.org/abs/1804.08333)

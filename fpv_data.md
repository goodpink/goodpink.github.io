---
layout: post
date: 2018-04-17 00:00
thumbnail:
title: Codes and Datasets for First-Person Vision
---

In order to promote future research on first-person vision, we have released a part of codes and datasets used in our work.

<!--more-->

## Ego-Surf Dataset (CVPR'15, TPAMI'18)

### [>> LINK (42.7 MB)](https://www.dropbox.com/s/onx530l5doqbrsb/yks_cvpr2015.zip?dl=0)

<img class="img-responsive" src="/images/yks-cvpr2015.png">

```
This dataset contains first-person videos recorded by a group of people during face to face communications.
Videos were taken under 8 different (4 indoors, 4 outdoors) scenes by two or three people.

Each video has the name in the form of: [I|O (indoor or outdoor)][0|1|2|3 (sequence id)]_[0|1(|2) (person id)].mp4.
```

## Paired Ego-Video (PEV) Dataset (CVPR'16)

### [>> LINK (201.5 MB, LAST UPDATE: 2018/04/17)](https://www.dropbox.com/s/ihy5qdoliktfozx/yks_cvpr2016_release.zip?dl=0)

<img class="img-responsive" src="/images/yks-cvpr2016.png">

```
This dataset contains 1226 pairs of videos recorded by wearable cameras during dyadic conversations.
Make sure that the annotations of class labels are slightly different from those shown in the original CVPR paper.
Please refer to yks-cvpr2016.pdf in this folder to see the latest results.

- */*****_[f/s].mp4: [first-person/second-person] points-of-view videos. Each video contains 90 frames.
- */pid.txt: person ids ranging from 0 to 5. Persons 0 and 1, 2 and 3, 4 and 5 were doing conversations.
```

## UTokyo Navigation Dataset (ECCV'16)

### [>> LINK (10.82 GB, LAST UPDATE: 2018/04/17)](https://www.dropbox.com/s/jt8d0ru2l2atvm0/yks_eccv2016_release.zip?dl=0)

<img class="img-responsive" src="/images/yks-eccv2016.png">

```
This dataset contains some features and ground-truth data we used in our ECCV work (we cannot publish original videos due to privacy concerns.)
Each of s* directories has the following structure:

- feat/deepfeat/*.npy: features extracted using the pre-trained Places network.
- feat/sift_fv/*.npy: Fisher vectors with dense root SIFT.
- feat/mofeat/*.npy: Motion features used for detecting egocentric attentional cues.
- feat/gmprob/*.npy: Output of trained attention cue detector

- gt/*.npy: ground truth data in the form of 1-d vector.
Values >= 1: the video recorder attended the pre-defined [value]-th visual motif.
Values == 0: the video recorder did not attend any pre-defined visual motifs.
values == -1: the video recorder attended something but not pre-defined visual motifs.
```

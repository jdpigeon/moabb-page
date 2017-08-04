---
layout:     post
title:      Architecture and Main Concepts
author:     Alexandre Barachant
tags: 		post
subtitle:  	An introduction to the basic concepts of the MOABB
category:  info
---
<!-- Start Writing Below in Markdown -->

# Architecture and main concepts

There are 3 main concepts in the MOABB: the datasets, the context and the pipelines.

### Datasets

A dataset handle and abstract low level access to the data. the dataset will takes data stored locally, in the format in which they have been downloaded, and will convert them into a MNE raw object.

### Contexts

A context define how the raw data will be converted to trials ready to be processed by a decoding algorithm. The context also define how performances are evaluates, i.e. define the cross-validation procedure and the metric used.
A single dataset can lead to multiple context. For example, a multi-class dataset can be evaluated as a multi-class problem, or as multiples binary classification problem. Similarly, we can have a within subject evaluation context or a cross-subject evaluation.

### Pipelines

Pipeline defines all steps required by an algorithm to obtain predictions. Pipelines are typically a chain of sklearn compatible transformers and end with an sklearn compatible estimator.
See [Pipelines](http://scikit-learn.org/stable/modules/generated/sklearn.pipeline.Pipeline.html) for more info.

![archi](../../../../../img/architecture.png)

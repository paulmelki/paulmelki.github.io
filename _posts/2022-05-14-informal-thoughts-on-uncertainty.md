---
title: "Informal Thoughts on Uncertainty"
output:
  md_document:
    variant: gfm
    preserve_yaml: TRUE
knit: (function(inputFile, encoding) {
   rmarkdown::render(inputFile, encoding = encoding, output_dir = "../_posts") })
author: "Paul"
date: '2022-05-14'
excerpt: "Part 1: Origins"
layout: post
categories:
  - Technicals
  - Theory
  - Uncertainty
---

<style>body {text-align: justify}</style>


*Bordeaux, France*

&nbsp;

## **Introduction**

The goal of machine learning models is to learn a model from the data. In Logic, this is called *induction*: given a certain set of observations, I try to derive a general rule about the truth. Generally speaking, this type of thinking or learning, whether followed by humans or by machines, always includes a certain uncertainty about the conclusions reached, especially since the learner can (almost) *never* see *all* the possible observations in the world. As such, we can never be sure that there is not at least *one* observation that does not conform with our conclusion. That is, there will always be uncertainty in our generalisations about unseen observations. How can this be translated in the context of machine learning, and why is it important? 


## **Why Uncertainty Matters**

As machine learning models start to be applied concretely in industrial settings to automate tasks in the real-world, the bright days of great lab results are starting to fade away as teams hit the "generalisation wall" which prevents the great research models from generalising (at least to a certain acceptable level) to new unseen real-world data. One possible explanation is related to the high uncertainty produced by the models: after all, most models produce only *point estimates*, without any type of confidence measures. And even if we were able to generate measures of confidence, these are usually aggregate measures over a set of points, rather than measures of the model's confidence in one particular observation (or, inversely, its uncertainty about it). However, reasoning about uncertainty is a relatively complex task (even for humans), for it represents reasoning about the unknown. 

## **Two Types of Uncertainty**
One way to think about uncertainty, and possibly better understand it and even quantify it, is to divide into two parts: *aleatoric* and *epistemic* uncertainty. An easy way to distinguish the two to is to define aleatoric uncertainty as the part of uncertainty that cannot be reduced, while the epistemic as being the one that can be reduced (if only...) we had more data (or knowledge about the world). One should be careful, however, with such definitions for they are in themselves blurry and informal and can represent different aspects of the learning task environment depending on the context. But, this is the best that we humans could come up with for now.



{% include image.html url="/images/uncertainty.png" width=800 align="center" caption="Simple representations of the two types of uncertainty. First, how do we classify the points in the region with interrogation mark? High aleatoric uncertainty (related to the data). Second, many models would fit the data well but which one is the best? High epistemic uncertainty. Source [3]." %}


### ***Aleatoric Uncertainty***
As previously said, this can be thought of as the irreducible part of uncertainty. And it is irreducible, well, simply because the world is highly non-deterministic. That is, even if we had access to the *real* stochastic process generating the data, we may still be uncertain about the predictions we are making. The reason lies perhaps in the fact that the relationship between the observations and the quantity we are interested in is never in itself a deterministic relationship. A simple example is the coin toss process, where even though we know perfectly well that only two possible outcomes are possible (heads or tails), the best we can do is give a probability for each outcome, but we can never *know* the outcome of a certain toss before seeing the results.

### ***Epistemic Uncertainty***


The adjective "epistemic" comes from the Ancient Greek word *episteme*, which roughly means "science" or "knowledge" -- more particularly, *proven* or *provable* knowledge. As such, it is quite ironic to talk about *epistemic uncertainty*. However, this uncertainty can be understood as the uncertainty about the model. Since the true model of knowledge that we are looking for is unknown, we usually try to approximate it inside a certain space (which more or less, depending on our choice, can be mathematically nice and knowable, or not). However, how can we know that this "space" we have chosen is a good one? Perhaps it is not and does not even include the true model (and perhaps is even very far away from it!) even though we obtain nice results on the dataset we have. Usually, as we have more knowledge, whether in the form of more data, or better domain knowledge, we can reduce this uncertainty by better approaching the true model.


## **Conclusion**
The study of uncertainty in machine learning is an ongoing field of research in which a lot still needs to be explored and developed. More important than simply understanding uncertainty is being able to account for it and generalise in spite of it, which is something that we still do not really know how to do. So, let us not rush into conclusions about the validity or the quality of our models, and let us not be tempted in the media by those who claim that we are close to achieving some scary type of all-knowing AI. 

&nbsp;


### **References**

1. Amini, A., Schwarting, W., Soleimany, A., & Rus, D. (2020). Deep Evidential Regression. *Proceedings of the 34th Conference on Neural Information Processing Systems* (NeurIPS 2020), Vancouver, Canada.

2. Arjovsky, M. (2019). *Out of Distribution Generalization in Machine Learning*. PhD Thesis, Courant Institute of Mathematical Sciences, New York University. 

3. Hüllermeier, E. & Waegeman, W. (2021). Aleatoric and Epistemic Uncertainty in Machine Learning: An Introduction to Concepts and Methods, *Machine Learning*, 110(3) pp.457-506. DOI: 10.1007/s10994-021-05946-3.

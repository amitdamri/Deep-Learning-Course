# The purpose of the assignment
Enabling students to experiment with creating two generative architectures: a) standard GAN, and; b) a
modified GAN architecture. We will work on real-world data and challenges.

---
## Introduction
Generative models are among the most exciting architecture in the field of deep learning today. Their
ability to generate high-quality data with little-to-no interaction or knowledge with the existing data
enables us to accomplish tasks thought impossible not long ago. In this assignment we will implement
two generative models, each dealing with a different scenario. The first generative model is a simple GAN,
which we will implement on two tabular datasets (we will not use image datasets as the running times
are significantly longer). The second GAN model offers in interesting “twist” in the sense that we will NOT
have access to any “real” data.

---
## Instructions
---
### Part 1 – Generative Adversarial Networks
---

In this part we will implement a simple GAN model for tabular data.
We used two datasets: German_credit and diabetes.

1. For each of these two datasets, we trained a GAN capable of generating samples from the original dataset.
We trained the model until it reaches convergence.

The report includes:
a. Several samples that “fooled” the detector and several that did not. Using basic
measures (e.g., Euclidean distance, basic visualization) we determined whether the samples
that fooled the detector are indeed similar to some of the original data
c. A graph describing the loss of the generator and the discriminator.

---
### Part 2 – Generative model for sample generation
---

In this part we will implement a GAN architecture “with a twist”. The goal of this architecture is inferring
the inner-working of a black-box model. Assume a black-box (BB) ML model (a model trained on some data of which you have no access). Our
goal is to generate some data that is likely similar to the data used to train the model. Since there is no
way for our model to know for sure, we will use the confidence scores (i.e., classification) produced by
the black-box model as indication. 

For each of the two datasets described above, we trained a RandomForest model. This model is the “blackbox”
we’ll use in this assignment. We used a random 70%/30% split so we can report the performance of
the classifier.

The training process is as follows:

1. For each generated sample, the generator will receive two inputs: a vector of random noise Z
and a desired confidence score (a scalar value) C.

2. The generator will generate a sample and send it to the discriminator.

3.  Instead of a “real” sample (to which we have no access) the discriminator will receive two
scalars: a) C (the same one given to the generator); b) Y – the output of the black-box model
we trained on the generated sample.

4. The goal of the discriminator is to determine which of the two values – C or Y – is the true
classification produced by the black-box model. The output of the discriminator, denoted by
𝑦", will be used for the calculation of the loss in the standard fashion.

<p align="center">
  <img src="https://user-images.githubusercontent.com/49988048/131302697-2b12ddd1-6f79-4f65-afed-d2f64df6a939.JPG">
</p>

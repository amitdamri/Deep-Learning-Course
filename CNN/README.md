# The purpose of the assignment
Enabling students to experiment with building a convolutional neural net and using it on a real-world dataset and problem. In addition to practical knowledge in the “how to” of building the network, an additional goal is the integration of useful logging tools for gaining better insight into the training process. Finally, the students are expected to read, understand and (loosely) implement a scientific paper.

<p align="center">
  <img src="https://user-images.githubusercontent.com/49988048/131228133-5aade889-1262-416d-98de-26e5691c31ae.png">
</p>


## Introduction

In this assignment, we will use convolutional neural networks (CNNs) to carry out the task of facial recognition. CNNs are the current state-of-the-art approach for analyzing image-based datasets. More specifically, we will implement a one-shot classification solution. Wikipedia defines one-shot learning as follows: 
"...an object categorization problem, found mostly in computer vision. Whereas most machine learning based object categorization algorithms require training on hundreds or thousands of samples/images and very large datasets, one-shot learning aims to learn information about object categories from one, or only a few, training samples/images..."

</br>The work is based on the paper Siamese Neural Networks for One-shot Image Recognition . Our goal, like that of the paper, is to successfully execute a one-shot learning task for previously unseen objects. Given two facial images of previously unseen persons, our architecture will have to successfully determine whether they are the same person.

## Instructions
We used the following dataset [Labeled Faces in the Wild](http://vis-www.cs.umass.edu/lfw/index.html).
* The following train and test sets were used: [Train](http://vis-www.cs.umass.edu/lfw/pairsDevTrain.txt) / [Test](http://vis-www.cs.umass.edu/lfw/pairsDevTest.txt). 
This division is set up so that no subject from test set is included in the train set
* Our report includes an analysis of the dataset (size, number of examples – in total and per class – for the train and test sets, etc).
Also we provided the full experimental setup we used – batch sizes, the various parameters of your architecture, stopping criteria and any other relevant information.

## Siamese Network Implementation
* The report includes a complete description of our architecture: number of layers, dimensions, filters, learning rates, optimization and regularization methods.
* In addiotion, our report includes an analysis of our architecture’s performance:
  * Convergence times, final loss and accuracy on the test set and holdout set
  * Graphs describing the loss on the training set throughout the training process
  * Performance when experimenting with the various parameters
  *	Examples of accurate and misclassifications. We tried to determine why our model was not successful.

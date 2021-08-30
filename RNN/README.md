# The purpose of the assignment
Enabling students to experiment with building a recurrent neural net and using it on a real-world dataset.
In addition to practical knowledge in the “how to” of building the network, an additional goal is introducing the students
to the challenge of integrating different sources of information into a single framework.

<p align="center">
  <img src="https://user-images.githubusercontent.com/49988048/131303493-9cbea9fe-661c-4fdf-a226-fa08352df4f2.png">
</p>

---
## Introduction
---

In class we covered the topic of automatic sentence completion/generation. In addition to the completion of “regular” sentences,
this technique can also be applied to other domains such as lyrics and melodies generation (a nice example is BachBot).
In this task we will train a neural net to generate lyrics based on the provided melody.

During the training of the model we will have access both to the lyrics of a song and its melody.
The melodies are stored in .mid (MIDI files) and contain various types of information – notes, the instruments used etc. 
During the test phase, we are required to automatically generate lyrics for a provided melody.

---
## Instructions
---
1.  We used the Pretty_Midi python library for the analysis of MIDI files.
2.  We implemented a recurrent neural net (LSTM) to carry out the task described in the introduction.
3.	During each step of the training phase, our architecture receive as input one word of the lyrics. Words are to represented using the Word2Vec representation
    that can be found online (300 entries per term).
4.	The task of the network is to predict the next word of the song’s lyrics.
5.	In addition to this textual information, we included information extracted from the MIDI file. One of the more simplistic options – inserting the entire melody representation at each step. 
6.	Note that your mechanism for selecting the next word should not be deterministic (i.e., always select the word with the highest probability) but rather be sampling-based. The likelihood of a term to be selected by the sampling should be proportional to its probability.

We evaluated two approaches based on the notes and instruments.
Ther report includes the chosen architecture ot the model, description of our approach(s) for integrating the melody information together with the lyrics,
and TensorBoard graphs showing the training and validation loss of our model.

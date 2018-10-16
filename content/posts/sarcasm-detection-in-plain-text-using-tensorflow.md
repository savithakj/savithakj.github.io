---
title: "Sarcasm Detection in Plain Text Using Tensorflow"
date: 2017-06-16T09:33:30-07:00
draft: false
---

What is Sarcasm? Sarcasm is the use of words that mean the opposite of what you want to say especially to insult someone, to show irritation, or to be funny. Lets see how we can identify sarcasm in plain text and may be later extended to voice inputs.

#### Feature Extraction:
Feature extraction is a crucial and time-consuming step when it comes to NLP projects. As
the input is in text form, which cannot be directly given to the neural network as an input
hence we need to extract features from the sentence. The base project has extracted multiple
features from a sentence like n-grams, polarity using SentiNet and TextBlob, and the topic
of the sentence using gensim.

#### Model :

The model with three hidden layers and one output layer was built. Each hidden layer has 100 neurons, and output layer has two neurons, one for each class, namely Sarcastic and Regular. One output neuron should be sufficient for a binary classifer, but the model has two so that the output is in the form of one hot encoded array. One hot encoded array is easy to extract and compare results. One hot encoded array is the type of encoding in which the index corresponding to the class is 1 in the array, and the other values are 0.

![model](/images/model.png)

### Results:
The confusion matrix is as follows:

|   | sarcastic | regular |
|---|---|---|
| sarcastic | 3240 | 4273 |
| regular | 2422 | 6481 |


From the observations, it is evident that the project was able to obtain similar performances with the same dataset using TensorFlow with minor features. The performance would improve if more features were included. The dataset had very fewer instances. If the model were trained with more instances, then it would result in a better performance.



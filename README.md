This is a summary of my Natural Language Processing project.

This is a NLP project in TensorFlow that utilizes transfer learning, convulutional neural networks and embbeding.

## Table of Contents 
* [Motivation](#motivation)
* [Summary of approach](#summary-of-approach)
* [Results](#results)
* [Insights](#insights)
* [What I learned](#what-i-learned)
* [How to use this repository](#how-to-use-this-repository)

## Motivation
I wanted to create a NLP project that classifies infromation as important or not. I found and paper on PubMed 200k RCT and decided to replicate it.
![alt text](https://github.com/Vybavnag/SkimLit/blob/main/images/reaserch_paper.jpg)


## Summary of approach
For this project, I decided to first create a baseline with as few parameters as possible so I strated of with a sklearn model. The evaluation results are here:


**{'accuracy': 72.1832384482987,


 'precision': 0.7186466952323352,**

 
 'recall': 0.7218323844829869,**

 
 'f1': 0.6989250353450294}**

I decided to start of with a CNN and decided to use Conv1D. The evaluation results are here: 


{'accuracy': 78.58797828677346,


 'precision': 0.7827518301065423,

 
 'recall': 0.7858797828677346,

 
 'f1': 0.7833516949290332}
 
It did better than base line but to get a better accuracy I decided to use transfer learning.

I decided to use Universal Sentence encoder model and then freeze the layers for feature extraction. The evaluation results are here:


{'accuracy': 71.42195154243348,


 'precision': 0.7147923729993135,
 
 'recall': 0.7142195154243347,

 
 'f1': 0.7111170978995865}
 
It looks like our model is performing worse. I decided to combine token and character embeddings for the next model.

The evaluation results are here:


{'accuracy': 73.44101681451079,


 'precision': 0.7325737363374634,

 
 'recall': 0.734410168145108,

 
 'f1': 0.7309116046721511}
 
Still isnt beating Conv1D model so i decided to add positional embedings as well. Here is a flowchart of what my model looks like.


![alt text](https://github.com/Vybavnag/SkimLit/blob/main/images/model_5.jpg)


## Results
{'accuracy': 83.1689394942407,


 'precision': 0.830717467271507,

 
 'recall': 0.831689394942407,

 
 'f1': 0.8307929631853365}
 
 ![alt text](https://github.com/Vybavnag/SkimLit/blob/main/images/all_model_metrics.jpg)

 ![alt text](https://github.com/Vybavnag/SkimLit/blob/main/images/f1-scores.jpg)


## Insights
Going through the reaserch paper and trying to emmulate it proved difficult. However I decied to use Transfer learning Conv1D and embeddings to try and acchive the same results they did. I ended up with an accuracy of 83% which is close to what they got. I also realised that it is best to add different types of embeddings to the text in the data for better resutls in the models.

## What I learned
* Planning ahead is important. Decide what data you want to input and get out of your model before you start.
* What are embeddings and how to embed text data.
* How to use CNN's and RNN's to acchive my results.
* Universal sentence encoder and how it works.
  


## How to use this repository
Open the ipynb file in Google Colab or Jupyter Notebook and run. Make sure there is a GPU with high RAM.

---
layout: page
title: Fed-Platform
description: A light-weighted federated learning platform based on browser
img: assets/img/Alice.jpg
importance: 1
category: work
---
<!-- <div style="text-align: justify">
</div> -->
__FedPlatform__ is a web-based federated learning platform for cross-silo privacy-preserving machine learning. Current federated learning algorithms required intense computational skills for implementation and deploying the correct dependencies is often-time a nightmare. Thus, I proposed a web-based federated machine-learning platform which is based on a communication tool [socket](https://docs.python.org/3/library/socket.html) and WebAssembly [pyodide](https://pyodide.org/en/stable/). By providing a well-defined python environment with packages in the front-end, __FedPlatform__ can free users/trainers from configuring the deployment.

> Outline
1. [Fire up the central aggregator](#fire-up-the-central-aggregator)
2. [Create two trainers Alice and Bob](#create-two-trainers-alice-and-bob)
3. [Platform interface](#platform-interface)
4. [Federated Learning](#federated-Learning)
5. [Roadmap](#roadmap)
6. [Github Repo](#github-repo)

## Fire up the central aggregator
First we fire up the server with node.js, and then we go to port 2333 of Localhost.
<p align="center">
    <img src="/assets/img/server_start.jpg"  width="60%" height="80%">
</p>

## Create two trainers Alice and Bob
Now, Alice and Bob are interested in doing some training in __FedPlatform__. So, they open the browser and enter the *Linear Regression* project.
<p align="center">
    <img src="/assets/img/Alice.jpg"  width="70%" height="80%">
    <img src="/assets/img/Bob.jpg"  width="70%" height="80%">
</p>

## Platform interface
This is what Alice sees in the __FedPlatform__ interface. She can even talk to Bob in the chat!
<p align="center">
    <img src="/assets/img/alice_2.jpg"  width="70%" height="80%">
</p>

## Federated Learning
### *Initiating a federated training task*
To initiate a federated learning task with data, user/trainer should upload or drag the data file to the left menu, then hit the **Start Training** button. Notice that, data is only uploaded to the local browser and it never leaves your device! (refreshing the page will lose your uploaded data). 

After Alice **Uploaded** data and hit the **Start Training** button, the system will pop up a window for confirmation. Here, I used [Breast Cancer Wisconsin (Diagnostic) Data Set](https://archive.ics.uci.edu/ml/datasets/breast+cancer+wisconsin+(diagnostic)) from the UCI Machine Learning Repository. And I horizontally split the dataset into two parts for *Alice* and *Bob*.
<p align="center">
    <img src="/assets/img/alice_3.jpg"  width="70%" height="80%">
</p>

### *Selecting the label for training*
It is essential to agree on the same target label with your trainees in advance. Now, assumes Alice and Bob decided to use the label *Diagnosis_M* as the training target.
<p align="center">
    <img src="/assets/img/alice_4.jpg"  width="70%" height="80%">
    <img src="/assets/img/alice_5.jpg"  width="70%" height="80%">
</p>

### *Training result*
After __FedPlatform__ received the same training labels from all users/trainers, the central aggregator will start checking the alignment of variables and nans in the dataset. For now, __FedPlatform__ will just simply remove the entries with missing values. Here shows the results from the training.
<p align="center">
    <img src="/assets/img/alice_6.jpg"  width="70%" height="80%">
</p>

And of course the result is lossless compared with a centralized linear regression.

## Roadmap
- Develop a dashboard web page
- Include more statistical model
- Migrate to tensorflow.js for deep learning model
- Develop a Knowledge Distillation model

## Github Repo
[FedPlatform](https://github.com/Li-Wentao/FedPlaform)
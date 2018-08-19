# Hacker Earth - Deep Learning - Identify the Animal

## Overview
This is my model for the beginner deep learning challaege on [Hackerearth](https://www.hackerearth.com/problem/machine-learning/predict-the-energy-used-612632a9-9de79188/).

The goal is to tag each picture with what animal it contains.

I was doing the [Fast AI](http://course.fast.ai) deep learning course when I saw that this competition was live and so it turned out to be  great opportunity to practice what I had learnt.

## The Challenge
13,000 training images  
6,000 test images  
30 possible animal classes

Evaluation metric is stated to be multi class log loss but the leader board is actually based on **accuracy**.

## Requirements
My solution uses the fast ai deep learning library. It's essentially an abstraction layer on top of Pytorch that intends to make some of the newer developments in deep learning more widely accessible.

You can get the library from [here](https://github.com/fastai/fastai)

## Structure
Training images in a **train** folder  
Test images in a **test** folder  
Filenames and tags for training images in **test.csv**


## Approach
-Explore the dataset  
-Explore the images  
-Create a data model with augmentations  

-Train last layer  
-Unfreeze previous layers and train with smaller learning rates  
*Used resnet101 with dropout and differential learning rates*  
-Do this 3 times (small, medium and large image sizes)  

-Get predictions using test time augmentation
-Take the class with the largest probability figure


## Outcome
This model returned a cross validation accuracy of around **96.7%** and a leaderboard accuracy of **94%**. This was good enough to get 11th when the competition finished.


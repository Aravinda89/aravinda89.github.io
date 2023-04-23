---
layout: post
title: How to split image dataset into train, validation and test set?
---

Splitting image data into train, validation, and test sets is a crucial step in machine learning model development. It helps to prevent over-fitting, evaluate model performance, and ensure that the model generalizes well to new, unseen data.
It's useful to have code that can quickly separate image data into training, validation, and testing datasets.
The folder structure would look something like this:

data/
    train/
        img_00.jpg
        ...
        img_69.jpg
    val/
        img_70.jpg
        ...
        img_85.jpg
    test/
        img_86.jpg
        ...
        img_100.jpg
        
Obtain the image data Retrieve all the images located in the designated folder.

'''pyhon'''

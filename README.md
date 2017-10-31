# Deep Learning projects 

This repository contains rojects for Udacity's Artificial Intelligence Nanodegree term 2.

## Environment Setup

The projects are run in an environment with Python 3 and all necessary packages installed. The environment can be created and configured by following the steps below:

1. `conda env create -f aind-environment-osx.yml to create the environment` (for OSX)  
2. `source activate aind to enter environment`  
3. `pip install git+https://github.com/hmmlearn/hmmlearn.git to install the development version of hmmlearn 0.2.1`  

## Project 1: Build Dog Breed Classification App  

In this project, CNN models are created to classify dog breeds. Given an image of a dog, the algorithms will identify an estimate of the dog’s breed. If supplied an image of a human, the models will identify the resembling dog breed.   

CNN models built from scratch as well as from transfer learning are compared. For CNN transfer learning, two different pre-trained models serving as the fixed feature extractor are compared. The CNN model with ResNet-50 achieved a test accuracy over 79% whereas the one with VGG-16 obtains a test accuracy around 46% after 20 epochs. 

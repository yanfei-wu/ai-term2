[//]: # (Image References)

[image1]: ./images/sample_dog_output.png "Sample Output"
[image2]: ./images/sample_human_output.png "Sample Output human"
[image3]: ./images/vgg16_model.png "VGG-16 Model Keras Layers"
[image4]: ./images/vgg16_model_draw.png "VGG16 Model Figure"

# Dog Breed Classifier with CNN 

## Project Overview

In this project, a pipeline is built that can be used within a web or mobile app to process real-world, user-supplied images. Given an image of a dog, the algorithm will identify an estimate of the canine’s breed. If supplied an image of a human, the code will identify the resembling dog breed.  

![Sample Output][image1]


![Sample Output human][image2]


## Models  

OpenCV's implementation of Haar feature-based cascade classifiers is used to detect human faces in images. A pre-trained ResNet-50 model is used to detect dogs in images. The ResNet-50 model along with weights that have been trained on ImageNet is downloaded. ImageNet contains over 10 million URLs, each linking to an image containing an object from one of 1000 categories. Given an image, this pre-trained ResNet-50 model returns a prediction (derived from the available categories in ImageNet) for the object that is contained in the image.  

A standard CNN architecture is designed to classify dog breed from scratch. It consists of 3 convolutional layers with spatial reduction via pooling. I also added batch normalization after each max pooling layer to boost the speed and increase accuracy. A fully connected layer is attached to the end of the network to make the final output predictions using learnings from the previous convolutional layers. The softmax activation used in this layer allows the output of probability for each breed. The model achieves a test accuracy around 4% with epoch of 5.  

To reduce training time without sacrificing accuracy, we can train a CNN using transfer learning. Two different pre-trained models are used, VGG-16 and ResNet-50. With one of them serving as as a fixed feature extractor, the last convolutional output is fed as input to a global average pooling layer and a fully connected layer, where the latter contains one node for each dog category and is equipped with a softmax. The transfer learning model with ResNet-50 bottleneck features perform much better (test accuracy over 79%) than the one with VGG-16 (around 46% test accuracy) with 20 epochs.  


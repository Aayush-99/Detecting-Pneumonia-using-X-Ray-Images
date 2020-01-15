# DETECTING PNEUMONIA FROM X-RAY IMAGES

The aim of this project is to identify whether a patient is is suffering from pneumonia or not by looking at chest X-ray images.

## NORMAL
![NORMAL](https://github.com/Aayush-99/Detecting-Pneumonia-using-X-Ray-Images/blob/master/NORMAL_sample.jpeg)
## PNEUMONIA
![PNEUMONIA](https://github.com/Aayush-99/Detecting-Pneumonia-using-X-Ray-Images/blob/master/PNEUMONIA_sample.jpeg)

To the human eye it is really difficult to spot the difference between the two. Here AI comes in providing accurate and fast diagnosis

## Table of Contents
* [General Info](#generalinfo)
* [Environemnt & Tools](#technology)
* [Data Augmentation](#augmentation)
* [Model Building](#cnn)
* [Conclusion](#conclusion)

## General Info
The risk of pneumonia is immense for many, especially in developing nations where billions face energy poverty and rely on polluting forms of energy. Over 150 million people get infected with pneumonia on an annual basis especially children under 5 years old. In such regions, the problem can be further aggravated due to the dearth of medical resources and personnel. AI can guarantee timely access to treatment and save much needed time and money for those already experiencing poverty.

## Environemnt & Tools
* Keras
* Numpy
* Pandas
* Matplotlib
* PIL
* Tensorflow

## Data Augmentation
The practice of data augmentation is an effective way to increase the size of the training set. Augmenting the training examples allow the network to "see" more diversified, but still representative, data points during training.

A couple of data generators are defined: one for training data, and the other for validation data. A data generator is capable of loading the required amount of data directly from the source folder, convert them into training data and training targets.

## Model Building
The next step is to build the model. This can be described in the following 5 steps:
1. 5 convolutional blocks comprised of convolutional layer, max-pooling and batch-normalization are deployed.
2. A flatten layer is used followed by four fully connected layers.
3. Dropouts have been used in between to reduce over-fitting.
4. Activation function was ReLU throughout except for the last layer where it was Sigmoid as this is a binary classification problem.
5. Adam is used as optimizer and cross-entropy as the loss.

Callbacks are also defined:
* ModelCheckpoint: saves a copy of the best performing model only when an epoch that improves the metrics ends.

* Early Stopping: It is an efficient solution to stop training when the generalization gap (difference between training and validation error) is getting worse.

## Conclusion
There is huge scope of improvement in this project. The hyperparameters can be tuned and batch_size can be increased, the image dimensions can be increased too. 
The model was made from scratch, which separates it from the other methods that rely heavily on transfer learning approach. In the future this work could be extended to detect and classify X-ray images consisting of lung cancer and pneumonia.

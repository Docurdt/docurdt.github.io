---
title: Elegant way of using deep learning on AMD Mac
date: 2018-11-12 8:38:09 +1000
categories: [Research, Deep learning]
tags: [computational configuration]     # TAG names should always be lowercase
---

> Fabrice's blog [Deep Learning on a Mac with AMD GPU](https://medium.com/@danbrice.datascience/deep-learning-on-a-mac-with-amd-gpu-4be1f18944a)

## An elegant solution for Deep Learning --- [PlaidML](https://vertexai-plaidml.readthedocs-hosted.com/en/latest/installing.html)

Mainstream deep learning frameworks, such as Tensorflow, PyTorch, and Caffe 2, are not so friendly for AMD Mac.
Among the solutions introduced in Fabrice's blog, PlaidML is an elegant one to me.
The installation and configuration of PlaidML can be found in the documentation of [PlaidML](https://vertexai-plaidml.readthedocs-hosted.com/en/latest/installing.html).
The source code shown below is a quick guide for beginner, which is based on PlaidML + Keras:

``` python
#import the following two lines first!
import plaidml.keras
plaidml.keras.install_backend()

#Import libraries and modules
import numpy as np
np.random.seed(123)  # for reproducibility

from keras.models import Sequential
from keras.layers import Dense, Dropout, Activation, Flatten
from keras.layers import Convolution2D, MaxPooling2D
from keras.utils import np_utils
from keras.datasets import mnist

#Load pre-shuffled MNIST data into train and test sets
(X_train, y_train), (X_test, y_test) = mnist.load_data()

#Preprocess input data
X_train = X_train.reshape(X_train.shape[0], 28, 28, 1)
X_test = X_test.reshape(X_test.shape[0], 28, 28, 1)
X_train = X_train.astype('float32')
X_test = X_test.astype('float32')
X_train /= 255
X_test /= 255

#Preprocess class labels
Y_train = np_utils.to_categorical(y_train, 10)
Y_test = np_utils.to_categorical(y_test, 10)

#Define model architecture
model = Sequential()

model.add(Convolution2D(32, (3, 3), activation='relu', input_shape=(28,28,1)))
model.add(Convolution2D(32, (3, 3), activation='relu'))
model.add(MaxPooling2D(pool_size=(2,2)))
model.add(Dropout(0.25))

model.add(Flatten())
model.add(Dense(128, activation='relu'))
model.add(Dropout(0.5))
model.add(Dense(10, activation='softmax'))

#Compile model
model.compile(loss='categorical_crossentropy',
              optimizer='adam',
              metrics=['accuracy'])

#Fit model on training data
model.fit(X_train, Y_train,
          batch_size=32, nb_epoch=10, verbose=1)

#Evaluate model on test data
score = model.evaluate(X_test, Y_test, verbose=0)

print(score)
```

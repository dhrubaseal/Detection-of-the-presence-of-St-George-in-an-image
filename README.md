# Detection of the presence of St. George in an image

Detecting the presence of St. George in an image with Machine Learning Model

## Table of Contents
- [Overview](#overview)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
  - [Dataset Preparation](#dataset-preparation)
  - [Training](#training)
  - [Inference](#inference)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Overview

A project for training a Convolutional Neural Network (CNN) model to classify images with and without St. George.

## Getting Started

Provide information on how to set up and run your project.

### Prerequisites

    - Python 3.x
    - TensorFlow
    - Numpy
    - Matplotlib
    - Pillow
    - Shutil

### Installation

Installed the required packages.

NumPy, Pillow, TensorFlow, Pathlib, Hashlib, Shutil, OpenCV

## Usage

The project can be used for image classification of 2 classes.

### Dataset Preparation

The Dataset is downloaded from the given source, and stored in a seperate location.
The Directories are classified in the below format.

    ├── Selected/
        ├── Dataset/
            ├── george/
            │   ├── image1.jpg
            │   ├── image2.jpg
            │   └── ...
            └── no_george/
                ├── image1.jpg
                ├── image2.jpg
                └── ...

Duplicate files are removed from each directory.

#The images are segrigated for train, validation, test and stored in different directories.

Training dataset are stored in the below format,

    ├── Selected/
       ├── Train/
            ├── george/
            │   ├── image1.jpg
            │   ├── image2.jpg
            │   └── ...
            └── no_george/
                ├── image1.jpg
                ├── image2.jpg
                └── ...

Validation dataset are stored in the below format,

    ├── Selected/
        ├── Validation/
            ├── george/
            │   ├── image1.jpg
            │   ├── image2.jpg
            │   └── ...
            └── no_george/
                ├── image1.jpg
                ├── image2.jpg
                └── ...

Testing dataset are stored in the below format,

    ├── Selected/
        ├── Test/
            ├── george/
            │   ├── image1.jpg
            │   ├── image2.jpg
            │   └── ...
            └── no_george/
                ├── image1.jpg
                ├── image2.jpg
                └── ...               

### Labeling

The Data is label according to their directories.

Number of classes: 2
Class labels: {'george': 0, 'no_george': 1}

Labelled data is normalised

### Training

The Convolutional Neural Network is used to train the Machine Learing model.

    Model: "sequential_1"
    _________________________________________________________________
     Layer (type)                Output Shape              Param #   
    =================================================================
     conv2d_3 (Conv2D)           (None, 254, 254, 32)      896       
                                                                     
     batch_normalization_3 (Bat  (None, 254, 254, 32)      128       
     chNormalization)                                                
                                                                     
     max_pooling2d_3 (MaxPoolin  (None, 127, 127, 32)      0         
     g2D)                                                            
                                                                     
     conv2d_4 (Conv2D)           (None, 125, 125, 64)      18496     
                                                                     
     batch_normalization_4 (Bat  (None, 125, 125, 64)      256       
     chNormalization)                                                
                                                                     
     max_pooling2d_4 (MaxPoolin  (None, 62, 62, 64)        0         
     g2D)                                                            
                                                                     
     conv2d_5 (Conv2D)           (None, 60, 60, 128)       73856     
                                                                     
     batch_normalization_5 (Bat  (None, 60, 60, 128)       512       
     chNormalization)                                                
                                                                     
    Total params: 14848193 (56.64 MB)
    Trainable params: 14847745 (56.64 MB)
    Non-trainable params: 448 (1.75 KB)

    Optimizer = adam
    Loss = binary_crossentropy
    Metrics = accuracy
    Epochs = 10

## Results

If you have achieved any notable results or metrics, showcase them in this section. This could include accuracy, loss plots, and sample predictions.

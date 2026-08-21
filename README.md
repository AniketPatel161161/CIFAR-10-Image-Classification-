# CIFAR10 Image Classification using a Convolutional Neural Network (CNN)

A PyTorch project that trains a Convolutional Neural Network from scratch to classify images from the CIFAR10 dataset into 10 categories.

## 📌 Project Overview
This project builds and trains a CNN on the CIFAR10 dataset and reaches good accuracy without using any pretrained weights. It is a simple, complete example of a deep learning pipeline: loading data, building a model, training it, and testing it.

## 🗂️ Dataset
CIFAR10 is a dataset of 60,000 small color images, each 32x32 pixels, split into 10 classes (airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck):
* 50,000 training images
* 10,000 test images

The dataset downloads automatically using torchvision.datasets.CIFAR10 the first time you run the notebook. You do not need to download it yourself.

## 🏗️ Model Architecture
The CNN has 3 convolution blocks followed by 2 fully connected layers:

| Layer | Details |
|---|---|
| Conv Block 1 | Conv2d(3 to 32, 3x3) then ReLU then MaxPool(2x2) |
| Conv Block 2 | Conv2d(32 to 64, 3x3) then ReLU then MaxPool(2x2) |
| Conv Block 3 | Conv2d(64 to 128, 3x3) then ReLU then MaxPool(2x2) |
| FC Layer 1 | Linear(2048 to 256) then ReLU |
| FC Layer 2 | Linear(256 to 10) |

## Training Setup
* Loss Function: Cross Entropy Loss
* Optimizer: Adam (default learning rate)
* Batch Size: 64
* Epochs: 10

## 📊 Results
The model reached about 75.6% test accuracy after 10 epochs of training.

| Epoch | Loss |
|---|---|
| 1 | 1.382 |
| 2 | 0.942 |
| 3 | 0.755 |
| 4 | 0.623 |
| 5 | 0.518 |
| 6 | 0.430 |
| 7 | 0.350 |
| 8 | 0.272 |
| 9 | 0.214 |
| 10 | 0.174 |

## Tools Used
* Python
* PyTorch and Torchvision

## Project Files
```
.
├── CNN_CIFAR10.ipynb   Main notebook: data loading, model, training, testing
├── README.md           This file
└── data/                CIFAR10 dataset files (downloaded automatically, not stored in git)
```

## 🚀 How to Run
1. Clone this repository
   ```bash
   git clone <your repo url>
   cd <your repo name>
   ```
2. Install the required packages
   ```bash
   pip install torch torchvision
   ```
3. Open and run the notebook
   ```bash
   jupyter notebook CNN_CIFAR10.ipynb
   ```
   The CIFAR10 dataset will download automatically into the data folder the first time you run it.

## Ideas for Improvement
* Add data augmentation (random crop, horizontal flip) to reduce overfitting
* Add Batch Normalization after the convolution layers for faster, more stable training
* Add Dropout in the fully connected layers
* Use a learning rate scheduler
* Try a deeper model or transfer learning
* Track accuracy per epoch and plot the loss to see progress more clearly

## 📄 License
This project is open source under the MIT License.

---
Built as a minor project to show a complete PyTorch deep learning pipeline: loading data, building a model, training it, and testing it.

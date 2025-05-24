
>[!tip]
>Deep Convolutional Neural Network

## Characteristics
- translation invariant
- spatial hierarchy

## Core
- [[Feature Map]]: Rank-3 [[Tensor]]
- [[Convolution Kernel]]

## Model Architecture
- [[Residual Connection]]
- [[Batch Normalization]]
- [[Depthwise Separable Convolution]]

## Architecture Principles
- Model should consist of repeating block of layers; a block is composed of multiple convolution layers and max pooling layers
- as the spactial direction width of feature map reduces, the number of filter in layer should increase
- deep, narrow architecture is better than wide and shallow one
- adding residual connection layer to the layer block can help training deep network
- adding batch normalization layer next to convolution layer can help
- replacing Conv2D layer to paramer-wise effective SeparableConv2D layer can help

## Model Interpretability
- Hitmap
- [[Class Activation Map]]

## Terms
---
- padding
- stride
- [[Average Pooling]]
- [[Data Augmentation]]
- feature extraction
- fine tuning

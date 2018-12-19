---
layout: post
author: Docurdt
date: 2018-11-04
---
Briefly introduce the development of hardwares for deep learning.

## Backgrounds
As the scale of data size and the complexity of the deep learning network architectures continues to grow, the hardware requirements for training deep learning models are becoming higher and higher. Unlike traditional machine learning algorithms, deep learning tends to use GPUs instead of CPUs for model training. Compared to CPUs, GPUs can speed up the training process by hundreds or even thousands of times. To further accelerate DL model training, multi-GPU or GPU-Grid computing architectures have become commonplace in the past few years. There is always no limit to the pursuit of faster and more powerful performance. Tensor Processing Unit (TPU) was announced by Google in 2016 at Google/IO, which is a customised ASICS that has been specifically designed and optimised for Google's Tensorflow framework. In which, Tensorflow is an open-sourced symbolic math library for deep learning, including many kinds of neural networks and recurrent neural networks, and was proposed by Google in November of 2015. And since then, TPU was used inside Google in the Data Center.

## From CPUs to GPU and GPUs
In the forepart of Deep Learning, CPUs were as the main power for the model training. The large-scale dataset which is the highly required for the deep models made the training processing unacceptable even on the CPU grid in a very short time. GPU and the support libraries were quickly developed and optimised for the model training, and GPU grid turned to be the main computational source in the subsequent years. With the well-supported library, Nvidia occupied the mainstream position in Deep Learning. Along with the change from CPU to GPU, the calculation was accelerated by 10 or 20 times. Among the GPUs, P100 is the highly recommended device.

## TPU --- What is currently standing at the top of the DL-ASIC.
Tensor as the fundamental unit of Tensorflow, Google customised the specific chip for the tensor calculation in 2016, which is Tensor Processing Unit (TPU). Without consider the expensive price, TPU is the most highly recommended device for Deep Learning model training. The current widely used TPU is V100 which is produced by NVIDIA, with an amazing price of AUD 17000. As for the performance, a TPU is 3 times faster than P100, and almost 70 times than CPU.


As far as I known, Google and NVIDIA are the two companies who have dramatically contributed to the development of Deep Learning.

[back](../../../blog.html)

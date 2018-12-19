---
layout: post
author: Docurdt
date: 2018-11-04
---
A tutorial for TFRecord.

When we handle the deep learning related work, we could use the image / text / sequence dataset directly during the network designing. We can easily read and data as well as the annotation into the model and starting the model training. But the situation become complex along with the dataset scale increase, especially for that dataset with millions samples. Quite a lot time will be consumed by the data loading from the HDD or SSD to the RAM. And sometimes even worse when we don't have enough RAM space, not even for the model training.

Google has proposed their own binary storage file format to tackle this embarrassing problem, which is TFRecord. During this process, we will use part of the functions or modules of Tensorflow to convert the raw data to TFRecord format and save to your local file system. And all the data and labels will be stored together and the dataset will split into separated files in an acceptable size. The TFRecord file takes up less space on disk, takes less time to copy and can be read much more efficiently from disk. We could load the TFRecord file directly for the model training in a fast and elegant way without worried about the limitation of the RAM.

_yay_

[back](../../../blog.html)

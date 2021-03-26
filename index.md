---
layout: default
title: The surprising impact of mask-head architecture <br/>on novel class segmentation
description: Vighnesh Birodkar, Zhichao Lu, Siyang Li, Vivek Rathod, Jonathan Huang</br>Google
---


We tackle the problem of partially supervised instance segmentation in which we
are given box annotations for all classes, but masks for only a subset of
classes. We show that the architecture of the mask head plays a surprisingly
important role in generalizing to masks of unseen classes. The figure below
shows improved mask predictions for unseen classes as we use better mask-head
architectures.

![My Image]({{site.url}}/{{site.baseurl}}/assets/mask_improvement.png){: .center-image-narrow}

Just by using better mask-head architectures (no extra losses or modules) we
achieve state-of-the-art performance in the partially supervised instance
segmentation task. We call our model **DeepMAC**, which is short for Deep
mask-heads above CenterNet.

## Code

*   [**Colab**](https://github.com/tensorflow/models/tree/master/research/object_detection/colab_tutorials/deepmac_colab.ipynb)
    for interactively trying out a pre-trained model.
*   [**DeepMAC code**](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/deepmac.md) -
    Used for most experiments with the
    [CenterNet](https://arxiv.org/abs/1904.07850) architecture.
*   [**Mask-RCNN code**](https://github.com/tensorflow/models/tree/master/official/vision/beta/projects/deepmac_maskrcnn) -
    Used for Mask-RCNN based ablations.

## Main Results

In this table (X/Y) indicates that we train on masks from 'X' classes and
evaluate with masks from 'Y' classes. These experiments are done on the COCO
dataset. The VOC split contains 20 classes and the non-VOC split contains 60
classes. Bounding boxes are provided for all classes.

### DeepMAC

| Train/Eval | mAP | Config |
|:-----------| --:| --------:| 
| VOC / Non-VOC | 35.5|[Link]() |
| Non-VOC / VOC | 39.1|[Link]() |

### Mask-RCNN

| Train/Eval      | mAP       | Config                                                       |
|:---------------:| :--------:|:------------------------------------------------------------:|
| VOC / Non-VOC | 34.4|[Link]() |

## Checkpoints

*   [COCO pre-trained checkpoint]() used in the colab (image + box input).

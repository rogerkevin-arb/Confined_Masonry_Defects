# Codes_Masonry
This repository contains the main codes used for crack semantic segmentation, brick type classification, and detection of spalling regions.

Pioneering study on the detection of diverse defects in real confined masonry structures with irregular surfaces (model capable of detecting cracks crossing three different materials). In addition, it includes the automatic estimation of crack widths using HSV-based filters for the detection of square templates, without the need for training from scratch.

![Architecture Overview](images/Cmasonry.png)

## Table of Contents
- [Description](#description)
- [Models](#models)
- [How to Run the Models](#how-to-run-the-models)
- [Dataset](#dataset)
- [References](#references)


## Description
This repository contains the main architectures developed for multiple computer vision tasks, including scale frame detection using HSV filters, semantic segmentation, skeletonization, brick type classification, and spalling region detection. It also includes the original dataset used for training and evaluation.



<p align="center">
  <img src="images/visualirr.png" width="700">
</p>

## Models
The proposed model for the crack semantic segmentation task is based on the UNet MobileNet architecture. Attention modules and residual blocks were incorporated as enhancements, along with a reduction in the number of parameters and an input adaptation for 512×512 pixel images. This results in the model we call Attention Res UNet MobileNet.



<p align="center">
  <img src="images/Arq.jpg" width="700">
</p>

In addition, the proposed algorithm for brick classification consists of two stages. The first involves preprocessing the 512×512 image before feeding it into the CNN model, which corresponds to the second stage.

<p align="center">
  <img src="images/Cla.png" width="700">
</p>

The convolutional layers helped identify patterns, which was further enhanced through transfer learning.

<p align="center">
  <img src="images/Conv2D.png" width="500">
</p>


## How to Run the Models

To run the code, you must have the training and validation images and masks ready. These should meet the orthogonality recommendations and have an approximate resolution of 5 pixels/mm for the crack semantic segmentation task. These characteristics are not required for the other tasks involving classification and bounding box detection.

![Architecture Overview](images/visualirr2.png)

The validation dataset for the brick type classification task undergoes pixel reduction through resizing and grayscale conversion, which helps decrease information load while maintaining good accuracy in predicting the corresponding class.

<p align="center">
  <img src="images/clasL.png" width="600">
</p>

For spalling region detection, by providing high-quality data, the YOLOv11 architecture successfully detected spalling in bricks, mortar, and confinement elements.

<p align="center">
  <img src="images/EjeSpa.png" width="600">
</p>

It is recommended to use Google Colab, separating the code blocks marked with “#----” into individual cells. If you want to test the pre-trained models for confined masonry with irregular surfaces, you can download the .h5 files and run them using the validation images.


<p align="center">
  <img src="images/escalaHsv.png" width="800">
</p>


<p align="center">
  <img src="images/esque.png" width="800">
</p>

## Dataset

The Dataset folder contains the data used for training and testing the models.

## References

El modelo propuesto para la tarea de segmentación surge apartir del modelo propuesto en el estudio de Dais et .al [1]. Asimismo se referencian otras fuentes que se usaron.  

1. D. Dais, İ. E. Bal, E. Smyrou, V. Sarhosis, *Automatic crack classification and segmentation on masonry surfaces using convolutional neural networks and transfer learning*, **Automation in Construction**, 125 (2021), 103606. [https://doi.org/10.1016/j.autcon.2021.103606](https://doi.org/10.1016/j.autcon.2021.103606)

2. O. Oktay, J. Schlemper, L. L. Folgoc, M. Lee, M. Heinrich, K. Misawa, K. Mori, S. McDonagh, N. Y. Hammerla, B. Kainz, B. Glocker, D. Rueckert, *Attention U-Net: Learning where to look for the pancreas*, **arXiv preprint**, arXiv:1804.03999 (2018). [https://arxiv.org/abs/1804.03999](https://arxiv.org/abs/1804.03999)

3. K. He, X. Zhang, S. Ren, J. Sun, *Deep residual learning for image recognition*, in: **Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR)**, 2016, pp. 770–778.








# UNet++
A PyTorch implementation of [UNet++: A Nested U-Net Architecture for Medical Image Segmentation](https://arxiv.org/abs/1807.10165) trained with CelebAMask

<p align="center">
  <img src="./images/elon-combined.gif" width="400"/>
</p>

## Dataset: CelebAMask
I made new datasets in Kaggle after pre-processing.  
1. Use only background for mask images
2. Downsize to [128x128](https://www.kaggle.com/datasets/kimjiyeop/celeba-128-onlybg) & [256x256](https://www.kaggle.com/datasets/kimjiyeop/celeba-256-onlybg)  

## Implementation Details
```
optimizer: Adam
learning rate: 3e-4 (without scheduler)
image size: 128x128
epoch: 100
batch size: 12

train loss: 0.5 * binary cross entrophy + dice coefficient loss
validation & test metric: IoU (Intersection over Union)
```

## Output of test images
<p align="center">
  <img src="./images/result.png?raw=true" style="width:500px;"/>
</p>

Some outputs are even better than target images in the dataset. 

## Train Loss
<p align="center">
  <img src="./images/loss.png" style="width:500px;"/>
</p>

## IoU
||Train|Valid|Test|
|:---:|:---:|:---:|:---:|
|# of images|27000|2500|500|
|IoU|0.9892</br>(Epoch 100)|0.9616</br>(Epoch 93)|0.9618|

<p align="center">
  <img src="./images/iou.png" style="width:500px;"/>
</p>

## Convert GIFs
<p align="center">
  <img src="./images/iu-combined.gif" width="400"/>
  <img src="./images/elon-combined.gif" width="400"/>
</p>

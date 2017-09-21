This repository contains my personal code for the Kaggle competition - [Carvana Image Masking Challenge](https://www.kaggle.com/c/carvana-image-masking-challenge).

| NBViewer Link | Description | Train set loss / dice coeff | Validation set loss / dice coeff | Kaggle Public LB Dice coeff |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|----------------------------------|-----------------------------|
| [01-unet-128x128.ipynb](https://nbviewer.jupyter.org/github/sainathadapa/kaggle-carvana-image-masking-challenge/blob/master/01-unet-128x128.ipynb) | U-Net; 128x128; Contracting path filter sizes: 64, 128, 256, 512, 1024 |  |  | 0.9908 |
| [02-unet-256x256.ipynb](https://nbviewer.jupyter.org/github/sainathadapa/kaggle-carvana-image-masking-challenge/blob/master/02-unet-256x256.ipynb) | U-Net; 256x256; Contracting path filter sizes: 32, 64, 128, 256, 512, 1024 |  |  | 0.9942 |
| [03-unet-512x512.ipynb](https://nbviewer.jupyter.org/github/sainathadapa/kaggle-carvana-image-masking-challenge/blob/master/03-unet-512x512.ipynb) | U-Net; 512x512; Contracting path filter sizes: 16, 32, 64, 128, 256, 512, 1024 |  |  | 0.9958 |
| [04-unet-1024x1024.ipynb](https://nbviewer.jupyter.org/github/sainathadapa/kaggle-carvana-image-masking-challenge/blob/master/04-unet-1024x1024.ipynb) | U-Net; 1024x1024; Contracting path filter sizes: 8, 16, 32, 64, 128, 256, 512, 1024 |  |  | 0.9961 |
| [07-threshold-analysis.ipynb](https://nbviewer.jupyter.org/github/sainathadapa/kaggle-carvana-image-masking-challenge/blob/master/07-threshold-analysis.ipynb) | Check to see if tuning the threshold value makes any difference to the score. | - | - | - |
| [08-bounding-boxes.ipynb](https://nbviewer.jupyter.org/github/sainathadapa/kaggle-carvana-image-masking-challenge/blob/master/08-bounding-boxes.ipynb) | Using the model from Notebook 2, bounding boxes are first visualized, and then calculated for both train and test sets. | - | - | - |
| [09-full-res-model-vertical-cut-and-bbox.ipynb](https://nbviewer.jupyter.org/github/sainathadapa/kaggle-carvana-image-masking-challenge/blob/master/09-full-res-model-vertical-cut-and-bbox.ipynb) | U-Net; 1024x1024; Contracting path filter sizes: 8, 16, 32, 64, 128, 256, 512, 1024; Vertical height of the original image is first reduced to 1024 from 1280, using bounding boxes. The resulting 1918x1024 image is cut vertically (with some overlap) to two images, each of size 1024x1024. |  |  | 0.9967 |
| [10-model-predictions-viz.ipynb](https://nbviewer.jupyter.org/github/sainathadapa/kaggle-carvana-image-masking-challenge/blob/master/10-model-predictions-viz.ipynb) | Models from notebooks 3,4, 9 are compared. Also worst predictions from Notebook 9's model are visualized | - | - | - |
| [11-ensemble.ipynb](https://nbviewer.jupyter.org/github/sainathadapa/kaggle-carvana-image-masking-challenge/blob/master/11-ensemble.ipynb) | Ensemble of Notebook 3 and 9 models, by taking average of predictions from both models. | - | - | 0.9967 |
| [12-tiramisu-256.ipynb](https://nbviewer.jupyter.org/github/sainathadapa/kaggle-carvana-image-masking-challenge/blob/master/12-tiramisu-256.ipynb) | One Hundred Layers Tiramisu; 256x256; Didn't fully train. Each epoch was taking way too long time to complete even for 256x256 resolution. | - | - | - |
| [13-bounding-boxes-revisit.ipynb](https://nbviewer.jupyter.org/github/sainathadapa/kaggle-carvana-image-masking-challenge/blob/master/13-bounding-boxes-revisit.ipynb) | Boundary boxes are analysed further | - | - | - |
| [14-full-res-model-1920-1080.ipynb](https://nbviewer.jupyter.org/github/sainathadapa/kaggle-carvana-image-masking-challenge/blob/master/14-full-res-model-1920-1080.ipynb) | U-Net; 1920x1280; Contracting path filter sizes: 8, 16, 32, 64, 128, 256, 512, 1024; The output from Notebook 3's model is added as an additional depth layer, after resizing to full resolution. | 0.0030; 0.9986 | 0.0139; 0.9958 | - |
| [16-unet-inception.ipynb](https://nbviewer.jupyter.org/github/sainathadapa/kaggle-carvana-image-masking-challenge/blob/master/16-unet-inception.ipynb) | UNet's VGG style Conv-BN-Act layers are replaced by InceptionV3 style blocks | 0.0184; 0.9905 | 0.0163; 0.9915 | - |

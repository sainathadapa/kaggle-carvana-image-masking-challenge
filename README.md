This repository contains my personal code for the Kaggle competition - [Carvana Image Masking Challenge](https://www.kaggle.com/c/carvana-image-masking-challenge).

Description of things that I had tried, in chronological order:
- In notebooks 1 to 4, U-Net based models were trained with increasing resolution from 128x128 to 1024x1024. The number of layers also been increased as the resolution increased. The dice coefficient increased, as the resolution and the number of total filters/layers increased. The 1024x1024 resolution model got 0.9961.
- A small analysis to see if tuning the threshold value makes any difference to the score was performed in Notebook 7.
- In Notebook 8, using the 256 model, bounding boxes are first visualized, and then calculated for both train and test sets.
- Notebook 9: Using the bounding boxes calculated in the previous notebook, the original images are first cut to the bounding box size. This is results in smaller images than the original resolution of 1918x1280, but still greater than 1024x1024. So each image is cut into two pices, each of resolution 1024x1024, such that there is an overlap between them. This way, the model can be trained at full resolution. The Public leaderboard score for this model was 0.9967.
- 512, 1024 and the full resolution models are compared in Notebook 10. Also, full resolution model's worst predictions are visualized.
- Notebook 11: Ensemble of 512 and full resolution model, by taking average of both models' predictions. This didn't increase the LB score.
- Notebook 12: Model based on the One Hundred Layers Tiramisu architecture. Even with much less parameters than the UNet model, and with just 256x256 resolution, each epoch took much more time to complete. Didn't fully trained the model.
- In Notebook 13, the boundary boxes are analysed further.
- Notebook 14: Model trained on the full resolution (~1918x1280), with additional depth layer being added to the input. This layer is the output from the 512 model, resized to the full resolution. The accuracy/loss didn't improve. 
- UNet's VGG style Conv-BN-Act layers are replaced by InceptionV3 style blocks in Notebook 16. The accuracy/loss didn't improve.


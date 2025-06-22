# T1 - VGG16 on All Images

Train VGG16 with all $9192$ images, size $128 \times 128$, $3$ channels RGB.

Set all random seed as $42$.

## Data

There are $9192$ images in total, $80\%$ in training set ($7353$ images) and $20\%$ in validation set ($1839$ images).

### Images Standardization

The mean values of three channels of the training set are $\left[13.54, 17.85, 112.11\right]$, and the standard deviation values of three channels of the training set are $\left[18.58, 20.26, 41.60\right]$.

Standardize all the images with the mean and std of images in training set.

### Labels Normalization

Set `MIN_LABEL = 1.3` and `MAX_LABEL = 5.2`. Normalize the labels by

$$
x \mapsto \frac{x - \text{min label}}{\text{max label} - \text{min label}}
$$

## Model

Load VGG16 model from `torchvision`, and change the last output layer from a $1000$-classifier to a regression output layer.

The second last layer have $4096$ nodes, representing extracted features of images.

Lock all the parameters in `vgg16.features` ($31$ layers), while the others could change during the training process.

## Training

Choose epochs in $\left[100, 200, 300\right]$ batch size in $\left[128, 256, 512\right]$, learning rate in $\left[10^{-2}, 10^{-3}, 10^{-4}\right]$.

The loss function is cross entropy and the optimizer is Adam.

In average, it takes about $5$ to $10$ minutes every $100$ epochs.


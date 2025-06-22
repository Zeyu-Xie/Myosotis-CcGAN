# Task 2 - CcGAN on All Images

We have two main notebooks in this task: `CcGAN_train.ipynb` and `CcGAN_loaded.ipynb`.

Notebook `CcGAN_train.ipynb` trains the CcGAN and saves the models, checkpoints, images in train and so on.

Notebook `CcGAN_loaded.ipynb` loads the trained CcGAN and generate images.

Both of the notebooks are available on both CPU and CUDA. (if don't consider time cost)

## Folders

In folder `datasets`, we save the datasets for training and validation.

In folder `models`, there are some models and functions for training CcGAN. (not ignored by git)

The `output` folder contains all generated data when training (and loading) CcGAN, including:

1. `CcGAN_models`: CcGAN models and checkpoints
2. `embed_models`: embed x2y net models and checkpoints and y2h net's models.
3. `saved_images`: images generated when training CcGAN. (to show the training process)
4. `saved_outputs`: includes data recording the loss and other indicies.
5. `genetated_images`: this folder is generated in notebook `CcGAN_loaded.ipynb`, and will contain all generated images.

## Data Downloading

Most of the folders mentioned in the last paragraph is ignored by git, so download them if needed.

The data are stored in AWS S3 buckets, please use the following code to download a single file:

```bash
aws s3 cp s3://your-bucket-name/path/to/file.txt /local/path/file.txt
```

Or download a whole folder recursively:

```bash
aws s3 cp s3://your-bucket-name/path/to/folder/ /local/folder/ --recursive
```

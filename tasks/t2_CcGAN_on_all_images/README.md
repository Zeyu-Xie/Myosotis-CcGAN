# Task 2 - CcGAN on All Images

We have two main notebooks in this task: `CcGAN_train.ipynb` and `CcGAN_loaded.ipynb`.

Notebook `CcGAN_train.ipynb` trains the CcGAN and saves the models, checkpoints, images in train and so on.

Notebook `CcGAN_loaded.ipynb` loads the trained CcGAN and generate images.

Both of the notebooks are available on both CPU and CUDA. (if don't consider time cost)

## Download Data

Download data from the AWS S3 Bucket. Some of the stored data is listed in the table below.

| Item          | Example Path                                                 |
| ------------- | ------------------------------------------------------------ |
| Ra Dataset    | `s3://myosotis-ccgan/tasks/t2_CcGAN_on_all_images/datasets/Ra_128_indexed.h5` |
| Trained CcGAN | `s3://myosotis-ccgan/tasks/t2_CcGAN_on_all_images/output/CcGAN_models/CcGAN_SAGAN_dim_128_128_batchSizeG_64_batchSizeD_64_lrG_1e-04_lrD_1e-04_nIters_30000_nDsteps_4_soft_0.047_108.739_loss_hinge_seed_42.pth` |

Use the following code to download a single file:

```bash
aws s3 cp s3://your-bucket-name/path/to/file.txt /local/path/file.txt
```

Or download a whole folder recursively:

```bash
aws s3 cp s3://your-bucket-name/path/to/folder/ /local/folder/ --recursive
```
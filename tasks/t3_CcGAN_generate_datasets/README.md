# Task 3 - CcGAN Generate Datasets

In this task we generate datasets of the fake images which contain the following parts:

| Key           | Shape          | Dtype     |
| ------------- | -------------- | --------- |
| `images`      | `(N, H, W, 3)` | `uint8`   |
| `labels`      | `(N, )`        | `float64` |
| `types`       | `(N, )`        | `int32`   |
| `index_train` | `(N/2, )`      | `int64`   |
| `index_valid` | `(N/2, )`      | `int64`   |
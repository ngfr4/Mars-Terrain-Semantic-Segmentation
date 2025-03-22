# Mars Terrain Semantic Segmentation with Deep Learning

## Abstract
This project focuses on semantic segmentation of 64×128 grayscale images of Mars terrain into five classes using deep learning. The goal was to accurately segment pixels into terrain categories despite severe class imbalance and small image sizes.

## Dataset Description

Dataset Details:

- Image Size: 64x128
- Color Space: Grayscale (1 channel)
- Input Shape: (64, 128)
- File Format: npz (Numpy archive)
- Number of Classes: 5
- Images: 2,505 training images + 10,022 test images


Class Labels: 

- 0: Background
- 1: Soil
- 2: Bedrock
- 3: Sand
- 4: Big Rock

<img width="603" alt="image" src="https://github.com/user-attachments/assets/6a226d2d-d50f-462f-b0c0-6f75f1df24e8" />

## Preprocessing:

- Duplicate & outlier removal via image hashing
- Pixel normalization and channel expansion
- 250-image validation split

## Techniques & Final Model

- Developed and tested U-Net architectures (2–5 layers)
- Best setup: 4-layer U-Net with Conv2DTranspose, skip connections, and Dice Loss
- Augmentations: horizontal/vertical flips and class oversampling (CutMix)
- Used AdamW optimizer (weight decay = 0.0001), with ReduceLROnPlateau, batch size = 16
- Final model achieved a test score of 0.53063

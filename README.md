# MDIBL-Self-Net

### Note
This code was taken from the Ning et. al. paper: Deep self-learning 
enables fast, high-fidelity isotropic resolution restoration for 
volumetric fluorescence microscopy 
(https://www.nature.com/articles/s41377-023-01230-2#Sec34)

### Software

- Python 3.9 (tested on)
- Conda
- Pytorch 1.13.1. (tested on)
- CUDA version 11.7 (tested on)
- Windows 10
- PyCharm 2022.3

### Hardware

- CPU or  GPU that supports CUDA CuDNN and  Pytorch 1.13.1.
- We tested on NVIDIA GeForce RTX 3090 (24 GB) and TITAN Xp (12 GB).

## Instructions

- Install Pytorch and other dependencies. The main Python dependencies 
include:

```
numpy
scipy
pytorch
opencv
scikit-image
tifffile
```

### Usage

1. For a given anisotropic 3D image stack (tiff format), first run the 
matlab co
de 'image_slice.m' to
generate lateral image slices (in the xy folder), down-sampled image 
slices (in
the xy_lr folder), and
opencv
scikit-image
tifffile
```

### Usage

1. For a given anisotropic 3D image stack (tiff format), first run the 
matlab co
de 'image_slice.m' to
generate lateral image slices (in the xy folder), down-sampled image 
slices (in
the xy_lr folder), and
axial image slices (in the xz or yz folder).

Input parameters: raw_path, data_name, scale


2. Run the python code 'Generate_training_data.py' to generate 
train_data.npz.

Input parameters: path, raw_data_path, train_data_path, 
signal_intensity_thresho
ld, xy_interval, xz_interval


3. Run 'Train_Self_net.py' to train Self_Net.

Input parameters:  path, min_v, max_v, imshow_interval


4. Run 'Self_net_output_volume.py' for isotropic restoration of the raw 
anisotro
pic image stack.

Input parameters:  test_path, model_path, min_v, max_v, raw_img, scale


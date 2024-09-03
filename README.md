# 3Dsegmentation-with-VNet


3D Organ Segmentation using VNet
Overview
This project involves training and evaluating a 3D segmentation model using VNet to segment four organs from CT abdomen images: Liver, Right Kidney, Left Kidney, and Spleen. The dataset used consists of .nii files containing CT scans and their corresponding labels.

Table of Contents
Requirements
Data Preparation
Model Setup
Training and Validation
Visualization
Usage
License


Requirements
Python 3.8+
PyTorch 1.10+
MONAI 0.8.1+
NumPy
Matplotlib
(Optionally) CUDA for GPU acceleration

You can install the required packages using the following command:
pip install torch torchvision monai numpy matplotlib

Data Preparation
data/
    images/
        image1.nii
        image2.nii
        ...
    labels/
        label1.nii
        label2.nii
        ...



Data Loading and Preprocessing
Loading: Loads .nii files for images and labels.
Preprocessing: Applies transformations including spacing, orientation, intensity scaling, and cropping.
Splitting: Divides the dataset into training and validation sets.
Model Setup
Model: VNet with 3D spatial dimensions.
Loss Function: Dice Loss with background exclusion.
Optimizer: Adam optimizer with a learning rate of 1e-4.
Training and Validation
Epochs: 100 epochs (can be adjusted).
Validation Interval: Validation performed every 2 epochs.
Metrics: Dice score calculated for Liver, Right Kidney, Left Kidney, and Spleen.
Model Saving: Best-performing models based on Dice scores are saved.
Visualization
Dice Scores: Plots Dice scores for each organ over epochs to visualize model performance.
Usage
Prepare your data: Place your .nii images and labels in the data/images and data/labels directories, respectively.
Adjust file paths: Update the paths in the data_preparation.py file to point to your dataset and model save directories.




This project is licensed under the MIT License. See the LICENSE file for details.


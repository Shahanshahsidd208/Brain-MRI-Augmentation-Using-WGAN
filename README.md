# MRI Image Generation Using WGAN

This project leverages a Wasserstein Generative Adversarial Network (WGAN) to generate high-quality synthetic MRI brain images. The solution addresses the challenge of limited medical imaging datasets by providing an effective augmentation method. By incorporating tailored prompts, the project streamlines data preprocessing, optimizes training processes, and ensures efficient resource usage, making it suitable for environments with constrained computational resources.

---

## Table of Contents
1. [Project Overview](#project-overview)
2. [Key Features](#key-features)
3. [Dataset](#dataset)
   - [Preprocessing Steps](#preprocessing-steps)
4. [Tools and Technologies](#tools-and-technologies)
5. [Prompt Engineering in Action](#prompt-engineering-in-action)
6. [How to Use This Repository](#how-to-use-this-repository)
7. [Future Work](#future-work)
8. [Acknowledgements](#acknowledgements)

---

## Project Overview

Medical imaging datasets are often constrained due to privacy and acquisition challenges. This project implements a WGAN to generate realistic MRI brain images, expanding the dataset for medical applications such as research and model training.

---

## Key Features
- **Custom Dataset Handling**: Processes nested directories and dynamically samples images to reduce memory usage.
- **Preprocessing Automation**: Tailored prompts optimized image resizing, normalization, and extraction of relevant slices from 3D MRI volumes.
- **Stable Training**: Implements RMSProp optimizer and gradient clipping for stable and efficient training.
- **Visualization**: Displays generated images in grid layouts to visualize progress across epochs.
- **Lightweight Design**: Limits the dataset to 50 images and uses a reduced epoch count (70) to accommodate resource constraints.

---

## Dataset

### BraTS 2020 Dataset
The project uses the BraTS 2020 Training Dataset, which includes multimodal MRI scans (T1, T2, T1Gd, FLAIR). These scans are widely used for tasks like brain tumor segmentation.

### Preprocessing Steps
1. **3D to 2D Conversion**: Extracts the central slice from 3D MRI volumes for 2D image representation.
2. **Transformations**: Resizes images to 256x256 and normalizes pixel values for compatibility with the model.
3. **Sampling**: Randomly selects 50 images from the dataset to balance computational efficiency and model performance.

---

## Tools and Technologies
- **Frameworks**: PyTorch for deep learning, Torchvision for data transformations
- **Data Handling**: Nibabel for reading `.nii` MRI files, custom PyTorch datasets
- **Model Components**: Generator and Discriminator networks with LeakyReLU activations
- **Environment**: Google Colab integrated with Google Drive
- **Visualization**: Matplotlib and Torchvision for image grids
- **Optimization**: RMSProp optimizer, Wasserstein loss

---

## Prompt Engineering in Action

The success of this project was driven by prompt engineering, which:
- **Automated Preprocessing**: Optimized the loading and slicing of MRI images from nested folders.
- **Streamlined Resource Usage**: Tailored prompts guided memory-efficient data handling and sampling.
- **Enhanced Debugging**: Facilitated intuitive debugging of model architecture and training pipeline.

---

## How to Use This Repository

1. Clone the repository and ensure dependencies are installed (`requirements.txt` is included).
2. Place the dataset in the appropriate folder or integrate with Google Drive.
3. Run the notebook to preprocess the dataset, train the WGAN, and visualize generated images.

---

## Future Work
- Expand to full datasets for enhanced diversity in generated images.
- Experiment with conditional GANs for labeled MRI generation.
- Explore domain-specific augmentation techniques to improve medical imaging workflows.

---

## Acknowledgements
- **Dataset**: BraTS 2020 provided by GroupLens.
- **Frameworks**: PyTorch, Torchvision.
- **Inspiration**: Research in GANs for medical imaging augmentation.

---

This project demonstrates the potential of WGANs and prompt engineering in enhancing medical imaging datasets. Contributions and feedback are welcome!
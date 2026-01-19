# PRODIGY_GA_04
# Pix2Pix: Image-to-Image Translation using Conditional GAN (cGAN)

Project Overview

This project implements **Pix2Pix**, an image-to-image translation model based on a **Conditional Generative Adversarial Network (cGAN)**.
The model learns a mapping from an input image to a corresponding output image using **paired training data**.

Image-to-image translation tasks include:

* Satellite images to maps
* Sketches to photographs
* Edge maps to real objects

The implementation uses **TensorFlow**, is trained on the **Maps dataset**, and includes a **Gradio-based user interface** for interactive inference.

Model Architecture

Generator

* U-Net based encoder–decoder architecture
* Uses skip connections between encoder and decoder layers
* Generates an output image conditioned on the input image

Discriminator

* PatchGAN discriminator
* Evaluates whether local image patches are real or fake
* Helps produce sharper and more realistic outputs

Dataset

* Dataset used: Maps dataset
* Dataset type: Paired image dataset
* Source: Berkeley Pix2Pix datasets

Each training image consists of:

* Left half: Input image (satellite view)
* Right half: Target image (map view)

Loss Functions

The Pix2Pix model uses a combination of two loss functions:

1. Adversarial Loss
   Encourages the generator to produce realistic images that can fool the discriminator.

2. L1 Loss
   Penalizes pixel-wise differences between the generated image and the ground truth image to preserve structural similarity.

Total Generator Loss:
Generator Loss = GAN Loss + λ × L1 Loss

Training Details

* Framework: TensorFlow
* Image size: 256 × 256
* Batch size: 1
* Optimizer: Adam
* Learning rate: 0.0002
* Beta1: 0.5
* Training environment: Google Colab (GPU)

Gradio Interface

A Gradio web interface is integrated to allow users to:

* Upload an input image
* Generate a translated output image
* View results in real time through a browser-based UI

How to Run the Project

1. Open the notebook in Google Colab
2. Enable GPU runtime
3. Run all cells sequentially to train the model
4. Launch the Gradio interface for testing image translation

Results

The trained Pix2Pix model successfully learns the mapping between satellite images and maps.
Generated outputs preserve structural layout and major features of the target images.

Technologies Used

* Python
* TensorFlow
* NumPy
* Matplotlib
* Gradio
* Google Colab

References

* Isola et al., "Image-to-Image Translation with Conditional Adversarial Networks"
* TensorFlow Pix2Pix Tutorial
* Berkeley Pix2Pix Dataset

Author
Brunda Addagalla


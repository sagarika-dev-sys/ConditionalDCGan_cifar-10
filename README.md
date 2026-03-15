# Conditional DCGAN on CIFAR-10

### Class-Controlled Image Generation using Deep Convolutional GANs

This repository presents an implementation of a **Conditional Deep Convolutional Generative Adversarial Network (cDCGAN)** trained on the **CIFAR-10 dataset** to generate **class-specific synthetic images**.

Unlike traditional GANs that generate random samples, **Conditional GANs allow controlled image generation** by incorporating **class label information** during training. This enables the generator to produce images belonging to a **specific category**, such as airplanes, cats, trucks, etc.

The project demonstrates how adversarial training combined with **label conditioning** can produce realistic images while maintaining control over the generated class.

---

# Project Highlights

* Implementation of **Conditional DCGAN architecture**
* Training performed on the **CIFAR-10 dataset**
* Generator produces **class-specific images**
* Visualization of **training images with labels**
* Monitoring **Generator vs Discriminator loss**
* Final **generated samples organized by class**

This project explores the power of **conditional generative models** in deep learning and their ability to learn complex visual distributions.

---

# How It Works

The Conditional DCGAN extends the traditional GAN framework by incorporating **class label information** into both the generator and discriminator networks. This conditioning allows the model to generate images corresponding to a specific class.

The workflow of the model is as follows:

1. **Input Preparation**  
   Real images from the CIFAR-10 dataset are used along with their corresponding class labels.

2. **Generator Input**  
   A random noise vector is combined with a class label to guide the generator in producing an image belonging to that category.

3. **Image Generation**  
   The generator processes the noise and label through transposed convolution layers to create a synthetic image.

4. **Discriminator Evaluation**  
   The discriminator receives both real and generated images along with their labels and learns to classify them as **real or fake**.

5. **Adversarial Training**  
   The generator and discriminator compete with each other during training.  
   - The discriminator tries to correctly identify fake images.  
   - The generator improves by trying to fool the discriminator.

6. **Class-Conditioned Image Generation**  
   After training, the generator can produce images for a **specific CIFAR-10 class by simply providing the desired label**.

---
Noise + Label → Generator → Generated Image
                     ↓
Real Image + Label → Discriminator → Real/Fake

---

# Dataset

The model is trained on the **CIFAR-10 dataset**, which contains:

* **60,000 color images**
* **10 different object classes**
* **32 × 32 image resolution**

### CIFAR-10 Classes

* Airplane
* Automobile
* Bird
* Cat
* Deer
* Dog
* Frog
* Horse
* Ship
* Truck

Each image is paired with a **label**, which is used as a conditioning variable during GAN training.

---

# Model Architecture

## Generator

The generator learns to transform **random noise vectors combined with class labels** into synthetic images.

Key components:

* Noise vector input
* Label embedding
* Transposed convolution layers
* Batch Normalization
* ReLU activations
* Output: **32×32 RGB generated image**

---

## Discriminator

The discriminator learns to distinguish between **real CIFAR-10 images and generated images** while also considering the **associated class label**.

Key components:

* Image input with label conditioning
* Convolutional layers
* LeakyReLU activations
* Binary classification output (Real / Fake)

---

# Training Process

The training follows the **adversarial learning paradigm**:

1. Real images and their labels are provided to the discriminator.
2. The generator creates fake images conditioned on labels.
3. The discriminator learns to classify **real vs generated images**.
4. The generator improves by trying to **fool the discriminator**.
5. Both networks improve iteratively through adversarial training.

Training continues until the generator learns to produce **visually meaningful class-conditioned samples**.

---

# Project Structure

```
Conditional-DCGAN-CIFAR10
│
├── dataset/
│
├── notebook/
│   └── conditional_dcgan.ipynb
│
├── results/
│   ├── training_images_with_labels.png
│   ├── generator_discriminator_loss.png
│   └── generated_images_by_class.png
│
├── models/
│   ├── generator.py
│   └── discriminator.py
│
└── README.md
```

---

# Results

## Training Images with Labels

Input samples from the CIFAR-10 dataset used during training.

![Training Images](training_images_with_labels.png)
---

## Generator vs Discriminator Loss

The graph below illustrates the **adversarial learning dynamics** between the generator and discriminator during training.

![Loss Graph](generator_discriminator_loss.png)

---

## Generated Images by Class

After training, the generator is able to produce **class-conditioned synthetic images** corresponding to different CIFAR-10 categories.

![Generated Images](generated_images_by_class.png)
---

# Technologies Used

* Python
* PyTorch
* NumPy
* Matplotlib
* Deep Learning
* Generative Adversarial Networks

---

# Applications

Conditional GANs are widely used in modern AI systems, including:

* Synthetic dataset generation
* Data augmentation
* Image-to-image translation
* AI art and creative systems
* Simulation and research

---

# Future Improvements

Potential enhancements to this project include:

* Training on **higher resolution datasets**
* Implementing **WGAN-GP for improved stability**
* Integrating **StyleGAN techniques**
* Building an **interactive image generation interface**
* Deploying the model as a **web application**

---

# Author

**Sagarika Sahoo**

-GitHub: https://github.com/sagrika-dev-sys

-LinkedIn: https://linkedin.com/in/sagarikasahoo2006

Developed as part of a deep learning exploration into **Generative Adversarial Networks and conditional image synthesis**.

---

# License

This project is intended for **educational and research purposes**.

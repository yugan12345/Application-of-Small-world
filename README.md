# 🌐 Small-World U-Net (SW-UNet) for Semantic Segmentation

> **Novel Application of Small-World Topology in Deep Learning Architectures**  
> Inspired by hierarchical graph blocks, this work proposes a unique integration of **Small-World Networks** into **U-Net** for satellite image segmentation.

[![🧪 Try Demo Notebook](https://img.shields.io/badge/View-Notebook-blue?style=for-the-badge)](#)

---

## 🧠 About the Project

This project explores **novel methods to integrate Small-World Network topologies** into machine learning architectures. We present a new segmentation model, **SW-UNet**, which leverages small-world connectivity to enhance information flow across layers.

Our exploration includes:
- Small-world based **graph signal processing** using **superpixels** for feature extraction  
- Multiple architectural trials to bring small-world principles into ML  
- A final successful realization through a **Small-World inspired skip connection topology** in a U-Net framework

---

## 🧬 Key Features

- ✅ U-Net backbone augmented with **probabilistically rewired connections**
- 🌐 Small-world topology embedded through **additive and rewired** edge construction
- 🔁 Skip connections are **not just local**; they include **long-range small-world edges**
- 📈 Measured improvements in **Dice** and **IoU** metrics over baseline U-Net
- 🧱 Built-in feature alignment using a **FeatureAligner** module for merging spatially mismatched feature maps

---

## 🔧 Technologies Used

| Component              | Library / Framework                        |
|------------------------|---------------------------------------------|
| Model Architecture     | PyTorch + Custom SW-UNet                   |
| Graph Topology         | Small-World Networks (Watts-Strogatz inspired) |
| Image Processing       | PIL, Torchvision                           |
| Training Loop          | PyTorch, Dice + IoU Metrics                |
| Dataset Handling       | Custom `SatelliteDataset` class           |
| Visualization          | Matplotlib                                |

---

## 📊 Metrics Used

- **Dice Coefficient**
- **Intersection over Union (IoU)**

---

## 🧱 Architecture Overview

The model uses a **Dense U-Net** backbone, where:
- Each encoder, bottleneck, and decoder block is a **DenseBlock**
- Skip connections are built via a **graph defined by small-world rewiring rules**
- An intermediate **FeatureAligner** ensures spatial and channel-wise compatibility

> 📌 The novelty lies in the design of these **graph-driven skip connections**, which are sampled using a **rewiring probability `p`** and embedded directly in the model's internal graph.

---

## 🧪 Dataset Used

- Dataset: [Crack Segmentation Dataset](https://www.kaggle.com/datasets/arnavsmayan/crack-detection-dataset)  
- Size: 3000 images  
- Preprocessing: Resized to 256×256, converted to grayscale masks

---

## 🏃‍♂️ How to Run

```bash
# Clone the repository
git clone https://github.com/your-username/sw-unet.git
cd sw-unet

# Install dependencies
pip install -r requirements.txt

# Run training
python Best.ipynb  # Or run the notebook in Jupyter/Lab/Colab

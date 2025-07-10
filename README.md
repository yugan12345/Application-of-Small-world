# 🌐 Small-World U-Net (SW-UNet): Small-World Networks in ML for Segmentation

> **A Novel Exploration of Small-World Topologies in Machine Learning Architectures**  
> Inspired by **hierarchical graph blocks**, this project introduces a **general-purpose use-case of Small-World Networks** in ML — with a focused application in image segmentation using a modified U-Net architecture.

---

## 🧠 Project Overview

This repository presents our exploration of how **small-world connectivity**, a concept rooted in complex networks, can enhance various machine learning workflows.  
We experimented with several architectural and representational approaches before discovering a **compelling use-case** in semantic segmentation.

Our journey involved:
- 🧩 **Graph Signal Processing** using superpixels to extract meaningful features  
- 🧠 Architecting a **Small-World-based feature aggregation pipeline**  
- 🧱 Finally discovering a practical and scalable use-case by **infusing small-world topology into U-Net** — a breakthrough driven by inspiration from **hierarchical block designs**

---

## 💡 Key Contributions

- ✅ Demonstrated **small-world edge rewiring** to improve long-range context flow in CNNs  
- 🔁 Explored **additive** and **rewired** variants of skip connections in deep architectures  
- ⚡ Proved that **non-local graph-style connectivity** benefits spatial segmentation  
- 📈 Achieved strong results on satellite image segmentation tasks using the proposed model

---

## 🔍 Methods Explored

| Approach | Description |
|---------|-------------|
| **Superpixel-based GSP** | Constructed graphs over superpixel regions and extracted visibility graph features |
| **Additive Small-World Edges** | Introduced extra long-range skip connections between encoder–decoder layers |
| **Rewired Small-World Edges** | Replaced original edges with probabilistically sampled graph edges |
| **Feature Aggregation** | Used aligned and fused features from dynamically connected layers via `FeatureAligner` |

---

## 🧪 Architecture: Small-World U-Net

The model follows the U-Net encoder–decoder layout but **rewires the feature flow graph**:

- 🔧 Skip connections follow a **graph topology** sampled from a **small-world distribution**
- 🧱 Each node is a `DenseBlock`, creating high internal connectivity
- 🔁 Long-range edges allow global information mixing at every layer
- 🧠 A `FeatureAligner` module resizes and matches feature dimensions from different layers

---

## 🔧 Technologies Used

| Component            | Library / Framework                    |
|----------------------|-----------------------------------------|
| Model + Training     | PyTorch                                 |
| Image Processing     | PIL, Torchvision                        |
| Visualization        | Matplotlib                              |
| Progress Bar         | tqdm                                    |
| Dataset Handling     | Custom Dataset class, DataLoader        |
| Architecture Design  | Custom `SWUNet` with Dense Blocks       |


---

## 📊 Evaluation Metrics

- 🧪 **Dice Coefficient**  
- 📉 **Intersection-over-Union (IoU)**  

> Both metrics show significant improvement when using small-world connectivity compared to standard U-Net baselines.

---

## 📁 Repository Highlights


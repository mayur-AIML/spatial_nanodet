# Efficient Real-time Pedestrian Detection and Social Distancing Monitoring using UAVs with Spatial Attention Mechanism

This repository contains the implementation of our lightweight pedestrian detection network designed for real-time social distancing monitoring using UAVs. The model uses ShuffleNet_V2 as the backbone and integrates a Spatial Attention Mechanism to enhance detection accuracy while maintaining computational efficiency

## Introduction
This repository provides an **efficient solution** for pedestrian detection and social distancing monitoring using **UAV imagery**. It includes code for **training**, **evaluation**, and **visualization**, as well as instructions on using **pre-trained models** for inference. The system is designed to run on **lightweight hardware**, making it suitable for **UAV deployment**.

## ✨ Features
- 🕵️‍♂️ **Real-time pedestrian detection** using **ShuffleNet_V2** and a **Spatial Attention Mechanism** for enhanced accuracy.
- 🚀 **Optimized for UAV applications** with **low computational complexity** and high efficiency.
- 📏 Supports **social distancing monitoring** by calculating distances between pedestrians in **real-world coordinates [Link](https://colab.research.google.com/drive/167n0oObT18-MGclHa9Qybicnk-XUvR1D?usp=sharing)**.
- 🎯 Includes **calibration functionality** for UAV imagery to accurately estimate **real-world distances**.

# NanoDet Installation Guide 🚀

## Requirements 🛠️
- **Linux** or **MacOS**
- **CUDA** >= 10.2
- **Python** >= 3.7
- **PyTorch** >= 1.10.0, < 2.0.0

## Steps to Install NanoDet 🐍

1. **Create and activate a conda environment:**

   ```bash
   conda create -n <env_nane> python=3.8 -y
   conda activate <env_name>
   ```
   
2. **Install PyTorch:**

```bash
   conda install pytorch torchvision cudatoolkit=11.1 -c pytorch -c conda-forge
```

3. **Clone the NanoDet repository:**
   ```bash
   git clone https://github.com/mt-project-cv/spatial_nanodet.git
   cd nanodet
   ```
4. **Install required packages:***
   ```bash
   pip install -r requirements.txt
   ```
5. **Setup NanoDet:**
   ```bash
   python setup.py develop
   ``` 

## 📂 Dataset
This project uses two datasets for training and evaluation:

1. **[Manipal UAV Person Detection Dataset](https://www.sciencedirect.com/science/article/abs/pii/S0924271622003008?via%3Dihub)**  
   - 📸 **13,462 images** with **153,112 annotated pedestrians**

2. **Custom UAV Dataset**  
   - 📷 **1,019 images** captured at **10 and 14 meters** altitude using a **DJI Mini UAV**

## 🚀 How to Train

### 📁 Dataset Preparation
- If your dataset annotations follow the **Pascal VOC XML format**, refer to the configuration file at `config/nanodet_custom_xml_dataset.yml`.
- For datasets with annotations in **YOLO format (Darknet TXT)**, check out the file at `config/nanodet-plus-m_416-yolo.yml`.
- Alternatively, you can convert your dataset annotations to the **MS COCO format** if required (details on COCO annotation format can be found online).

### ⚙️ Configuration Setup
1. **Copy and Modify**: Start by copying an example `.yml` config file from the `config/` folder.
2. **Save Directory**: Update the `save_dir` to specify where you’d like the model to be saved.
3. **Number of Classes**: Adjust `num_classes` in the `model->arch->head` section to match your dataset’s class count.
4. **Paths**: Ensure the correct image and annotation paths are set in both the `data->train` and `data->val` sections.
5. **Device Configuration**: Set `gpu_ids`, `num_workers`, and `batch_size` under the `device` section to match your system’s specifications.
6. **Training Parameters**: Adjust `total_epochs`, `lr` (learning rate), and `lr_schedule` based on your dataset size and batch size.
7. If you want to tweak the network architecture, data augmentation, or other settings, you can refer to the **Config File Detail** section.

### 🏋️‍♂️ Start Training
NanoDet now uses **PyTorch Lightning** for training. To start training, whether using a single GPU or multiple GPUs, run the following command:

```bash
python tools/train.py config/nanodet-plus-m_416-yolo.yml
```

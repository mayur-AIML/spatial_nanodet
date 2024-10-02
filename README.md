# Efficient Real-time Pedestrian Detection and Social Distancing Monitoring using UAVs with Spatial Attention Mechanism

This repository contains the implementation of our lightweight pedestrian detection network designed for real-time social distancing monitoring using UAVs. The model uses ShuffleNet_V2 as the backbone and integrates a Spatial Attention Mechanism to enhance detection accuracy while maintaining computational efficiency

## Introduction
This repository provides an **efficient solution** for pedestrian detection and social distancing monitoring using **UAV imagery**. It includes code for **training**, **evaluation**, and **visualization**, as well as instructions on using **pre-trained models** for inference. The system is designed to run on **lightweight hardware**, making it suitable for **UAV deployment**.

## ✨ Features
- 🕵️‍♂️ **Real-time pedestrian detection** using **ShuffleNet_V2** and a **Spatial Attention Mechanism** for enhanced accuracy.
- 🚀 **Optimized for UAV applications** with **low computational complexity** and high efficiency.
- 📏 Supports **social distancing monitoring** by calculating distances between pedestrians in **real-world coordinates**.
- 🎯 Includes **calibration functionality** for UAV imagery to accurately estimate **real-world distances**.

## 📂 Dataset
This project uses two datasets for training and evaluation:

1. **Manipal UAV Person Detection Dataset**  
   - 📸 **13,462 images** with **153,112 annotated pedestrians**

2. **Custom UAV Dataset**  
   - 📷 **1,200 images** captured at **10 and 14 meters** altitude using a **DJI Mini UAV**

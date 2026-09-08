# RISC-V-Edge-AI-with-VSDSquadron-Pro

# Course Project

## Overview
This repository documents my progress through the **RISC-V Edge AI with VSDSquadron PRO** course by **VLSI System Design (VSD)**.  
The course is centered on implementing **machine learning (ML) and neural networks** on a highly resource-limited platform — the **SiFive FE310-G002 RISC-V SoC** with only **16 KB RAM**.  

Since I did not have access to the physical board, the entire workflow (training, quantization, inference, and image capture) was simulated using **Freedom Studio** for RISC-V bare-metal builds.

The core of this project is an **MNIST handwritten digit classifier**, trained and quantized in Python, and ported into a simulated bare-metal RISC-V environment for inference.

---

## Note
All the code in this repository was developed as part of a workshop.  
I currently do not have access to the required hardware board, so the programs have not been tested on the actual hardware.  
However, each project has been built successfully with **zero errors and zero warnings** in the development environment.

---

##  Objectives
- Train and quantize a neural network for **MNIST digit recognition**.  
- Optimize the model to fit **memory-constrained environments** (≤16 KB).  
- Simulate deployment on **SiFive FE310-G002** without requiring hardware.  
- Explore bare-metal programming concepts and memory-aware inference.  

---

##  Course Modules (Highlights)
The course spans **27 learning modules**, progressing from basic ML to quantized NN deployment:

1. Edge AI introduction & VSDSquadron board overview  
2. ML basics – regression, gradient descent, visualization  
3. Classification – KNN, SVM, and embedded inference  
4. MNIST with SVM and RISC-V simulation  
5. Quantization & fitting AI into 16 KB RAM  
6. Neural networks – from scratch to 98% accuracy  
7. Bit-quantized NN deployment on RISC-V  

---

## 🛠 Hardware & Software Environment
**Target Hardware (simulated):**
- **SiFive FE310-G002** (RV32IMAC, 320 MHz, 16 KB L1 I-cache, 16 KB SRAM, QSPI Flash).  
- No physical board used — simulation only.  

**Tools & Software:**
- **Google Colab**
- **Python 3.10+** with:  
  - `tensorflow==2.15.0`  
  - `numpy`  
  - `matplotlib`  
- **Freedom Studio 3.1.1** – RISC-V simulation/debugging  
- **RISC-V GNU Toolchain (optional)** – for compiling C code  

---

##  Project Structure
```
├── src/
│ ├── training.py # Train & quantize MNIST model
│ ├── app_inference.h # Inference helper functions
│ ├── main.c # Bare-metal simulation logic
│ ├── mnist_quantized_model.tflite # Quantized TFLite model
│ ├── mnist_model_params.c/.h # Quantized weights & declarations
│ ├── cam_capture_image.py # Simulated camera input
│ ├── Image_Processing.py # Preprocessing (resize 28x28 → 12x12)
│ ├── send_image_uart.py # UART-based image transmission (simulated)
│ └── Makefile # Build setup (optional, C project)
├── images/
│ ├── mnist_sample.png # Example digit
│ └── nn_architecture.jpg # Model architecture diagram
└── README.md # This file
```
---

##  Setup Instructions

1. **Install Python dependencies**
   ```bash
   pip install tensorflow==2.15.0 numpy matplotlib
2. **Train & Quantize the Model**
  ```bash
  python src/training.py - From RiscV_Edge_AI_Workshop repo | Author: dhanvantibhavsar
```
3. **Feedom Studio**
```bash
 Reffer Datasheet (From Page 10  for Windows) 
```

---

##  Model Details
- **Input:** 12×12 grayscale image (downsized from MNIST 28×28)  
- **Hidden Layers:** 2 dense layers with 64 neurons each (LeakyReLU activation)  
- **Output:** 10 neurons (digits 0–9)  
- **Quantization:** 8-bit integer format (final size ≈ 17 KB)  
- **Inference:** Optimized C implementation with integer-only ops (ReLU + FC layer)  

---

##  Key Learnings
- Built a complete **Edge AI pipeline** without needing physical hardware  
- Learned **quantization strategies** to squeeze models into 16 KB SRAM  
- Explored **bare-metal RISC-V programming concepts** via simulation  
- Implemented **image preprocessing + simulated UART pipeline** for deployment  
- Gained confidence in **cross-domain workflow** (Python ML ↔ Embedded C)  

---

##  Acknowledgments
- **VSD (VLSI System Design)** – for course resources and mentorship  
- **SiFive** – for FE310-G002 documentation & SoC specifications  
- **TensorFlow Lite** – for providing quantization and deployment tools  

---

##  Repository Status
No releases yet. Project under active development.

# RISC-V Edge AI with VSDSquadron PRO

![RISC-V](https://img.shields.io/badge/Architecture-RISC--V-blue)
![Edge AI](https://img.shields.io/badge/Domain-Edge%20AI-orange)
![TinyML](https://img.shields.io/badge/Focus-TinyML-green)
![Python](https://img.shields.io/badge/Python-3.10%2B-yellow)
![C](https://img.shields.io/badge/Language-C-blue)
![Status](https://img.shields.io/badge/Status-In%20Progress-lightgrey)

> **Course Project | RISC-V • Edge AI • TinyML • Neural Networks • Quantization**

---

## 📌 About This Repository

This repository documents my learning journey and practical work for the **RISC-V Edge AI with VSDSquadron PRO** course conducted by **VLSI System Design (VSD)**.

The course focuses on bringing **Machine Learning and Neural Network inference to resource-constrained embedded systems**, combining concepts from:

* Machine Learning
* Neural Networks
* TinyML
* Edge AI
* RISC-V architecture
* Embedded C programming
* Model quantization
* Image processing
* Memory optimization
* Embedded inference

The primary application explored in this repository is an **MNIST handwritten digit classification system**, developed using Python and progressively adapted toward a resource-constrained RISC-V environment.

---

# 🎯 Course Objectives

The major objectives of this project are:

* Understand the fundamentals of **Edge AI and TinyML**.
* Learn Machine Learning concepts relevant to embedded systems.
* Implement classification algorithms such as **KNN and SVM**.
* Develop a neural-network-based **MNIST digit classifier**.
* Understand neural-network training and inference.
* Explore **model quantization** for embedded deployment.
* Reduce computational and memory requirements of AI models.
* Understand **RISC-V bare-metal programming**.
* Implement AI inference using embedded C.
* Explore image preprocessing for embedded AI.
* Understand host-to-embedded communication concepts.
* Study the complete **ML → Quantization → Embedded Inference** workflow.

---

# 🧠 Edge AI Workflow

The overall workflow followed in this course can be represented as:

```text
                DATASET
                   │
                   ▼
          Data Preprocessing
                   │
                   ▼
          Model Development
                   │
                   ▼
             Model Training
                   │
                   ▼
            Model Evaluation
                   │
                   ▼
              Quantization
                   │
                   ▼
          Memory Optimization
                   │
                   ▼
        Embedded C Implementation
                   │
                   ▼
             RISC-V Build
                   │
                   ▼
              AI Inference
```

The project therefore connects **Python-based AI development** with **embedded RISC-V software development**.

---

# 📚 Course Modules

The course consists of **27 learning modules** covering the progression from Machine Learning fundamentals to quantized neural-network deployment.

### 1. Edge AI Introduction

* Introduction to Edge AI
* TinyML concepts
* Edge AI applications
* VSDSquadron PRO overview
* RISC-V ecosystem

### 2. Machine Learning Fundamentals

* Machine Learning basics
* Training and testing
* Regression
* Gradient Descent
* Data visualization

### 3. Classification

* Classification fundamentals
* K-Nearest Neighbors (KNN)
* Support Vector Machines (SVM)
* Embedded classification

### 4. MNIST Classification

* MNIST dataset
* Image representation
* Digit classification
* SVM-based classification
* RISC-V-oriented implementation

### 5. Quantization and Memory Optimization

* Quantization fundamentals
* Model-size reduction
* Integer representation
* Memory constraints
* Embedded AI optimization

### 6. Neural Networks

* Neural network fundamentals
* Neurons and layers
* Forward propagation
* Activation functions
* Training
* Accuracy evaluation

### 7. Bit-Quantized Neural Network Deployment

* Neural-network quantization
* Integer inference
* Weight representation
* Embedded deployment
* RISC-V inference

---

# 🔬 Main Project — MNIST Digit Classification

The main demonstration project is a **handwritten digit classifier using the MNIST dataset**.

The system takes a grayscale image of a handwritten digit, performs preprocessing, and predicts one of ten classes:

```text
0  1  2  3  4  5  6  7  8  9
```

---

## 🖼️ Image Processing

The original MNIST images have a resolution of:

```text
28 × 28 pixels
```

To reduce computational and memory requirements, the project experiments with reducing the input to:

```text
12 × 12 pixels
```

The preprocessing pipeline is:

```text
Input Image
     │
     ▼
Grayscale Conversion
     │
     ▼
Resize
28 × 28 → 12 × 12
     │
     ▼
Normalization / Scaling
     │
     ▼
Model Input
     │
     ▼
Neural Network
     │
     ▼
Predicted Digit
```

---

# 🧠 Neural Network Architecture

The current neural-network configuration consists of:

```text
              Input Image
               12 × 12
                  │
                  ▼
             144 Features
                  │
                  ▼
        Fully Connected Layer
             64 Neurons
                  │
                  ▼
              LeakyReLU
                  │
                  ▼
        Fully Connected Layer
             64 Neurons
                  │
                  ▼
              LeakyReLU
                  │
                  ▼
             Output Layer
             10 Neurons
                  │
                  ▼
          Predicted Digit
              0 – 9
```

### Model Parameters

| Parameter           | Configuration     |
| ------------------- | ----------------- |
| Dataset             | MNIST             |
| Original Image      | 28 × 28 grayscale |
| Processed Image     | 12 × 12 grayscale |
| Input Features      | 144               |
| Hidden Layer 1      | 64 neurons        |
| Hidden Layer 2      | 64 neurons        |
| Output Layer        | 10 neurons        |
| Number of Classes   | 10                |
| Activation          | LeakyReLU         |
| Quantization        | 8-bit integer     |
| Target Architecture | RISC-V            |

---

# 🔢 Model Quantization

One of the important Edge AI concepts explored in this project is **model quantization**.

Quantization reduces the numerical precision used to represent model parameters.

The general process is:

```text
Floating-Point Model
        │
        ▼
    Quantization
        │
        ▼
  8-bit Integer Model
        │
        ▼
Reduced Memory / Computation
        │
        ▼
Embedded Inference
```

The project explores **8-bit integer quantization** as a technique for reducing the model footprint and making neural-network inference more suitable for embedded systems.

---

# 💾 Memory Constraints

A major challenge in embedded Edge AI is the limited memory available on the target platform.

The target RISC-V system is based on the **SiFive FE310-G002**, with approximately:

```text
16 KB SRAM
```

This creates a significant constraint for AI workloads.

The project therefore investigates:

* Input-size reduction
* Smaller neural-network architectures
* Weight quantization
* Integer arithmetic
* Memory-aware programming
* Static allocation
* Lightweight inference functions

### Current Model Size

The current quantized model is approximately:

```text
~17 KB
```

This is larger than the stated 16 KB SRAM capacity, so **further memory optimization and/or appropriate placement of model data in available memory regions is required for a complete hardware deployment**.

This limitation is documented intentionally as part of the Edge AI optimization challenge.

---

# 🖥️ Hardware Environment

## Target Platform

**VSDSquadron PRO**

The course targets a RISC-V-based embedded platform using the **SiFive FE310-G002** SoC.

The development work explores:

* RISC-V architecture
* RV32-based embedded programming
* Bare-metal development
* Embedded C
* Memory-constrained AI
* Neural-network inference

### Hardware Availability

The physical VSDSquadron PRO board was not available during the development of this repository.

Therefore, the current work focuses primarily on:

* Software development
* Model training
* Quantization
* Image processing
* C implementation
* RISC-V development environment
* Simulation/development-environment validation

**Physical hardware validation remains a future step.**

---

# 💻 Software Environment

## Development Tools

* Google Colab
* Python 3.10+
* TensorFlow
* NumPy
* Matplotlib
* Freedom Studio
* RISC-V GNU Toolchain
* Git
* GitHub

---

# 📦 Python Dependencies

Install the required Python packages using:

```bash
pip install tensorflow==2.15.0 numpy matplotlib
```

Or, if `requirements.txt` is provided:

```bash
pip install -r requirements.txt
```

---

# 🚀 Getting Started

## 1. Clone the Repository

```bash
git clone https://github.com/rajasekl-srm/RISC-V-Edge-AI-VSDSquadron-PRO.git
```

Enter the project directory:

```bash
cd RISC-V-Edge-AI-VSDSquadron-PRO
```

---

## 2. Install Python Dependencies

```bash
pip install tensorflow==2.15.0 numpy matplotlib
```

---

## 3. Train the Model

The model-training workflow is implemented in:

```text
src/training.py
```

Run:

```bash
python src/training.py
```

The training process includes:

```text
MNIST Dataset
     ↓
Preprocessing
     ↓
Model Creation
     ↓
Training
     ↓
Evaluation
     ↓
Quantization
     ↓
Model Export
```

---

# ⚙️ RISC-V / Embedded Build

The embedded application source code is located under:

```text
src/
```

The project contains C source files and supporting files intended for RISC-V development.

Where applicable, the project can be built using the provided Makefile:

```bash
make
```

The exact build, debug, and flashing procedure depends on the selected **Freedom Studio project configuration** and the availability of the physical target board.

---

# 🔌 Image and UART Pipeline

The repository also explores a simulated image-transfer workflow.

```text
Image / Camera Input
        │
        ▼
Python Capture
        │
        ▼
Image Preprocessing
        │
        ▼
Resize / Normalization
        │
        ▼
UART Transmission
        │
        ▼
RISC-V Application
        │
        ▼
Neural Network
        │
        ▼
Predicted Digit
```

Relevant scripts include:

```text
cam_capture_image.py
Image_Processing.py
send_image_uart.py
```

---

# 📁 Repository Structure

```text
RISC-V-Edge-AI-VSDSquadron-PRO/
│
├── README.md
├── requirements.txt
│
├── src/
│   ├── training.py
│   ├── main.c
│   ├── app_inference.h
│   ├── mnist_quantized_model.tflite
│   ├── mnist_model_params.c
│   ├── mnist_model_params.h
│   ├── cam_capture_image.py
│   ├── Image_Processing.py
│   ├── send_image_uart.py
│   └── Makefile
│
├── images/
│   ├── mnist_sample.png
│   └── nn_architecture.jpg
│
├── notebooks/
│
├── results/
│
└── docs/
```

> The repository structure will be updated as additional course experiments and documentation are added.

---

# 🧪 Experiments

The repository is intended to document experiments performed throughout the course.

Current areas include:

* Machine Learning fundamentals
* Regression
* Gradient Descent
* KNN classification
* SVM classification
* MNIST digit classification
* Neural networks
* Image preprocessing
* Model quantization
* Memory optimization
* Integer inference
* RISC-V programming
* Embedded C
* UART-based image transfer
* Edge AI deployment

---

# 📊 Project Progress

| Area                          | Status         |
| ----------------------------- | -------------- |
| Edge AI Fundamentals          | ✅ Completed    |
| Machine Learning Fundamentals | ✅ Completed    |
| Regression                    | ✅ Completed    |
| KNN Classification            | ✅ Completed    |
| SVM Classification            | ✅ Completed    |
| MNIST Classification          | ✅ Completed    |
| Neural Network Development    | ✅ Completed    |
| Model Quantization            | ✅ Completed    |
| Image Preprocessing           | ✅ Completed    |
| RISC-V Software Development   | 🚧 In Progress |
| Embedded Inference            | 🚧 In Progress |
| Physical Board Testing        | ⏳ Pending      |

---

# 📈 Results

The repository will maintain experiment results as the project progresses.

Results may include:

* Training accuracy
* Validation accuracy
* Test accuracy
* Model size
* Quantized model size
* Memory requirements
* Inference performance
* Image-processing results
* RISC-V build results
* Hardware measurements

Experiment outputs and visualizations will be maintained under:

```text
results/
```

---

# 🧠 Key Learning Outcomes

Through this course, I am developing practical understanding of:

### Machine Learning

* Supervised learning
* Regression
* Classification
* KNN
* SVM
* Model evaluation

### Neural Networks

* Neural-network architecture
* Layers and neurons
* Forward propagation
* Activation functions
* Training
* Inference

### TinyML / Edge AI

* Model compression
* Quantization
* Integer inference
* Memory optimization
* Resource-constrained AI

### RISC-V

* RISC-V architecture
* Embedded programming
* Bare-metal concepts
* C programming
* Toolchain usage
* Memory-aware development

### System Integration

* Image preprocessing
* Camera-input simulation
* UART communication
* Host-to-embedded data flow
* AI inference pipeline

---

# ⚠️ Hardware Validation

The current repository contains software and development-environment work.

Because the physical VSDSquadron PRO board was not available during development, the following aspects require hardware validation:

* Actual SRAM utilization
* Flash utilization
* Execution time
* UART communication
* Camera/input interface
* Real-time inference
* Power consumption
* End-to-end AI inference

Therefore, software/development-environment results should not be interpreted as final hardware measurements.

---

# 🙏 Acknowledgments

I would like to acknowledge:

* **VLSI System Design (VSD)** for the RISC-V Edge AI course and learning resources.
* **SiFive** for the FE310-G002 documentation and RISC-V ecosystem.
* **TensorFlow** for machine-learning and model-quantization tools.
* The **RISC-V open-source community** for the tools, documentation, and ecosystem supporting embedded development.

---

# 📚 References

Useful technical resources include:

* RISC-V Architecture Documentation
* SiFive FE310-G002 Documentation
* VSD RISC-V / Edge AI course resources
* TensorFlow Documentation
* TensorFlow Lite / LiteRT Documentation
* MNIST Dataset

---

# 📌 Repository Status

**🚧 Active Development**

This repository is being continuously updated with:

* Course activities
* Source code
* Experiments
* Neural-network models
* Quantization work
* RISC-V implementations
* Documentation
* Results
* Hardware validation

---

## ⭐ Repository

If you find this project useful for learning about **RISC-V, Edge AI, TinyML, and embedded neural-network deployment**, feel free to explore the repository and follow the progress.

---

**Author:** Raj Sekar

**GitHub:** [rajasekl-srm](https://github.com/rajasekl-srm)


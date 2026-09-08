# RISC-V Edge AI with VSDSquadron PRO

![RISC-V](https://img.shields.io/badge/Architecture-RISC--V-blue)
![Edge AI](https://img.shields.io/badge/Domain-Edge%20AI-orange)
![TinyML](https://img.shields.io/badge/Focus-TinyML-green)
![Python](https://img.shields.io/badge/Python-3.10%2B-yellow)
![C](https://img.shields.io/badge/Language-C-blue)
![Freedom Studio](https://img.shields.io/badge/Freedom%20Studio-3.1.1-purple)
![Status](https://img.shields.io/badge/Status-In%20Progress-lightgrey)

> **Course Project | RISC-V • Edge AI • TinyML • Neural Networks • Quantization**

---

## 📌 About This Repository

This repository documents my learning journey and practical implementation work for the **RISC-V Edge AI with VSDSquadron PRO** course conducted by **VLSI System Design (VSD)**.

The course explores the implementation of **Machine Learning, Neural Networks, TinyML, and Edge AI** on resource-constrained RISC-V embedded systems.

The project combines concepts from:

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
* UART communication

The primary application explored in this repository is an **MNIST handwritten digit classification system**, developed using Python and progressively adapted toward deployment on a resource-constrained RISC-V platform.

---

# 🎯 Course Objectives

The major objectives of this project are:

* Understand the fundamentals of **Edge AI and TinyML**.
* Learn Machine Learning concepts relevant to embedded systems.
* Implement classification algorithms such as **KNN and SVM**.
* Develop an **MNIST handwritten digit classifier**.
* Understand neural-network training and inference.
* Explore **model quantization** for embedded deployment.
* Reduce computational and memory requirements of AI models.
* Understand **RISC-V architecture and bare-metal programming**.
* Implement AI inference using embedded C.
* Explore image preprocessing for embedded AI.
* Understand host-to-embedded communication concepts.
* Study the complete **Machine Learning → Quantization → Embedded Inference** workflow.

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
                       │
                       ▼
                Edge AI System
```

This workflow connects **Python-based AI development** with **embedded RISC-V software development**.

---

# 📚 Course Modules

The course consists of **27 learning modules**, progressing from Machine Learning fundamentals to quantized neural-network deployment.

### Module 1 — Edge AI Introduction

* Introduction to Edge AI
* TinyML concepts
* Edge AI applications
* VSDSquadron PRO overview
* RISC-V ecosystem

### Module 2 — Machine Learning Fundamentals

* Machine Learning basics
* Training and testing
* Regression
* Gradient Descent
* Data visualization

### Module 3 — Classification

* Classification fundamentals
* K-Nearest Neighbors (KNN)
* Support Vector Machines (SVM)
* Classification for embedded systems

### Module 4 — MNIST Classification

* MNIST dataset
* Image representation
* Digit classification
* SVM-based classification
* RISC-V-oriented implementation

### Module 5 — Quantization and Memory Optimization

* Quantization fundamentals
* Model-size reduction
* Integer representation
* Memory constraints
* Embedded AI optimization

### Module 6 — Neural Networks

* Neural-network fundamentals
* Neurons and layers
* Forward propagation
* Activation functions
* Training
* Accuracy evaluation

### Module 7 — Bit-Quantized Neural Network Deployment

* Neural-network quantization
* Integer inference
* Weight representation
* Embedded deployment
* RISC-V inference

> The detailed learning activities, experiments, code, and observations will be organized in the repository as the course progresses.

---

# 🛠️ Hardware & Software Environment

## Target Hardware

**VSDSquadron PRO RISC-V Development Board**

The target platform uses the **SiFive FE310-G002 RISC-V SoC**.

The development work explores:

* RISC-V architecture
* RV32-based embedded programming
* Bare-metal development
* Embedded C
* Memory-constrained AI
* Neural-network inference

---

## Hardware Specifications

The target SoC is based on the **SiFive FE310-G002** and provides a resource-constrained environment suitable for studying embedded AI concepts.

Key resources relevant to this project include:

* RISC-V RV32 architecture
* RV32IMAC instruction set support
* 16 KB SRAM
* Instruction cache
* QSPI Flash
* Embedded peripherals

> Exact hardware resources and configuration should be verified against the VSDSquadron PRO / FE310-G002 documentation for the specific board revision.

---

# 💻 Software Environment

The following software tools are used throughout the project:

| Software / Tool      | Purpose                                  |
| -------------------- | ---------------------------------------- |
| Freedom Studio 3.1.1 | RISC-V development and debugging         |
| RISC-V SDK           | Embedded software development            |
| OpenOCD              | Debug/programming interface              |
| Python 3.10+         | AI model development                     |
| TensorFlow           | Neural-network training and quantization |
| NumPy                | Numerical processing                     |
| Matplotlib           | Visualization                            |
| Git                  | Version control                          |
| GitHub               | Project documentation and collaboration  |

---

# ⚙️ Environment Setup

The VSDSquadron PRO development environment was successfully configured using **Freedom Studio 3.1.1**.

The setup included:

1. USB driver configuration
2. Freedom Studio installation/extraction
3. Workspace creation
4. RISC-V SDK configuration
5. Target selection
6. Validation Software Project creation
7. OpenOCD debug configuration
8. VSDSquadron PRO board connection
9. `sifive-welcome` example execution
10. Serial terminal verification
11. On-board LED verification

---

## 1. USB Driver Configuration

For Windows-based setup, the USB interface driver can be configured using **Zadig**.

The configuration procedure is:

```text
Zadig
   │
   ├── Options
   │      └── List All Devices
   │
   ├── Select:
   │      Dual RS-232-HS (Interface 0)
   │
   ├── Driver:
   │      libusb-win32
   │
   └── Install / Reinstall Driver
```

> Driver installation is platform-dependent. Follow the appropriate procedure for the operating system being used.

---

# 2. Freedom Studio Setup

Freedom Studio 3.1.1 was configured as the primary development environment for the VSDSquadron PRO board.

The setup involved:

1. Extracting the VSDSquadron PRO Freedom Studio package.
2. Launching **Freedom Studio 3.1.1**.
3. Creating a workspace.
4. Selecting the workspace directory.
5. Creating a **Validation Software Project**.
6. Selecting the appropriate SDK.
7. Selecting the `sifive-hifive1` target where applicable.
8. Selecting the example application.
9. Creating the debug launch configuration.

---

# 3. OpenOCD Debug Configuration

The VSDSquadron PRO board was connected to the development system and the project was launched using **OpenOCD**.

The debug workflow is:

```text
VSDSquadron PRO
       │
       ▼
USB Connection
       │
       ▼
Freedom Studio
       │
       ▼
Debug Configuration
       │
       ▼
OpenOCD
       │
       ▼
RISC-V Target
       │
       ▼
Program Execution
```

---

# 4. `sifive-welcome` Hardware Test

As an initial hardware validation step, the **`sifive-welcome`** example was executed on the physical VSDSquadron PRO board.

Successful execution was verified through:

* Freedom Studio debug session
* COM terminal output
* On-board blue LED activity

The expected terminal output includes:

```text
SiFive
```

The **blue LED on the VSDSquadron PRO board blinked successfully**, confirming the basic hardware connection, development environment, debug configuration, and program execution.

---

# 🎥 Hardware Demonstration

A video demonstration has been recorded showing the successful execution of the `sifive-welcome` program and the **blue LED blinking on the VSDSquadron PRO board**.

### Demonstration

```text
sifive-welcome
      │
      ▼
Freedom Studio
      │
      ▼
OpenOCD Debug
      │
      ▼
VSDSquadron PRO
      │
      ▼
Blue LED Blinking
```

### Video 

Then the video can be referenced as:

```markdown
[▶️ Watch VSDSquadron PRO LED Blinking Demonstration](media/vsdsquadron_led_blink.mp4)
```

> The video provides practical evidence of successful basic board initialization and execution of the `sifive-welcome` application.

---

# ✅ Hardware Validation Status

| Test                         | Status         | Observation                        |
| ---------------------------- | -------------- | ---------------------------------- |
| Freedom Studio Installation  | ✅ Completed    | Development environment configured |
| Workspace Creation           | ✅ Completed    | Workspace created                  |
| RISC-V SDK Configuration     | ✅ Completed    | Target configured                  |
| Validation Project           | ✅ Completed    | Project created                    |
| OpenOCD Configuration        | ✅ Completed    | Debug session established          |
| `sifive-welcome` Build       | ✅ Completed    | Program built                      |
| VSDSquadron PRO Connection   | ✅ Verified     | Board connected                    |
| Program Execution            | ✅ Verified     | Application executed               |
| COM Terminal Output          | ✅ Verified     | `SiFive` output observed           |
| Blue LED Test                | ✅ Verified     | LED blinking observed              |
| AI/MNIST Hardware Deployment | 🚧 In Progress | Further validation required        |

---

# 🧠 Main AI Project — MNIST Digit Classification

The main AI application explored in this repository is a **handwritten digit classification system using the MNIST dataset**.

The system accepts a grayscale image of a handwritten digit, performs preprocessing, and predicts one of ten classes:

```text
0  1  2  3  4  5  6  7  8  9
```

---

# 🖼️ Image Processing

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

One of the major Edge AI concepts explored in this project is **model quantization**.

Quantization reduces the numerical precision used to represent model parameters.

The general workflow is:

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
Reduced Model Footprint
        │
        ▼
Embedded Inference
```

The project explores **8-bit integer quantization** as a technique for reducing the model footprint and making neural-network inference more suitable for resource-constrained embedded systems.

---

# 💾 Memory Constraints

A major challenge in embedded Edge AI is the limited memory available on the target platform.

The target environment provides approximately:

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

This is larger than the stated 16 KB SRAM capacity.

Therefore, **additional memory optimization and appropriate placement of model data in available memory regions are required for complete deployment on the target hardware**.

This limitation is documented as part of the Edge AI optimization challenge.

---

# 🔌 Image and UART Pipeline

The repository also explores a host-to-embedded image-transfer workflow.

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

# 🐍 Python Environment

Create a Python virtual environment:

```bash
python3 -m venv venv
```

Activate it:

### Linux / macOS

```bash
source venv/bin/activate
```

### Windows

```bash
venv\Scripts\activate
```

---

# 📦 Install Python Dependencies

Install the required packages:

```bash
pip install tensorflow==2.15.0 numpy matplotlib
```

If `requirements.txt` is available:

```bash
pip install -r requirements.txt
```

---

# 🧪 Train the Model

The model-training workflow is implemented in:

```text
src/training.py
```

Run:

```bash
python src/training.py
```

The training process follows:

```text
MNIST Dataset
     │
     ▼
Preprocessing
     │
     ▼
Model Creation
     │
     ▼
Training
     │
     ▼
Evaluation
     │
     ▼
Quantization
     │
     ▼
Model Export
```

---

# ⚙️ RISC-V Build

The embedded application source code is located under:

```text
src/
```

The project contains C source files and supporting files intended for RISC-V development.

Where applicable, the project can be built using the provided Makefile:

```bash
make
```

The exact build, debug, and flashing procedure depends on the selected **Freedom Studio project configuration** and target hardware.

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
├── media/
│   └── vsdsquadron_led_blink.mp4
│
├── notebooks/
│
├── results/
│
└── docs/
```

> The repository structure will evolve as additional course experiments, results, and documentation are added.

---

# 🧪 Experiments

The repository is intended to document practical experiments performed throughout the course.

Current areas include:

* Edge AI fundamentals
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

| Area                                | Status         |
| ----------------------------------- | -------------- |
| Edge AI Fundamentals                | ✅ Completed    |
| Machine Learning Fundamentals       | ✅ Completed    |
| Regression                          | ✅ Completed    |
| Gradient Descent                    | ✅ Completed    |
| KNN Classification                  | ✅ Completed    |
| SVM Classification                  | ✅ Completed    |
| MNIST Classification                | ✅ Completed    |
| Neural Network Development          | ✅ Completed    |
| Model Quantization                  | ✅ Completed    |
| Image Preprocessing                 | ✅ Completed    |
| Freedom Studio Setup                | ✅ Completed    |
| OpenOCD Debug Setup                 | ✅ Completed    |
| VSDSquadron PRO Basic Hardware Test | ✅ Completed    |
| RISC-V Software Development         | 🚧 In Progress |
| Embedded AI Inference               | 🚧 In Progress |
| MNIST Hardware Deployment           | 🚧 In Progress |
| Full Hardware Validation            | ⏳ Pending      |

---

# 📈 Results

Experiment results will be documented as the project progresses.

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

## Machine Learning

* Supervised learning
* Regression
* Classification
* KNN
* SVM
* Model evaluation

## Neural Networks

* Neural-network architecture
* Layers and neurons
* Forward propagation
* Activation functions
* Training
* Inference

## TinyML / Edge AI

* Model compression
* Quantization
* Integer inference
* Memory optimization
* Resource-constrained AI

## RISC-V

* RISC-V architecture
* Embedded programming
* Bare-metal concepts
* C programming
* Toolchain usage
* Memory-aware development

## System Integration

* Image preprocessing
* Camera-input simulation
* UART communication
* Host-to-embedded data flow
* AI inference pipeline

---

# ⚠️ Hardware Validation Note

The basic VSDSquadron PRO development environment has been successfully validated using the `sifive-welcome` example.

The successful LED test confirms:

* Board connectivity
* Freedom Studio configuration
* OpenOCD debug communication
* Basic RISC-V program execution

However, the successful `sifive-welcome` test does **not** by itself confirm successful deployment of the complete MNIST neural-network application.

The following aspects still require validation as the AI deployment progresses:

* Actual AI model memory utilization
* Flash utilization
* SRAM utilization
* Inference execution time
* UART-based image transfer
* Real-time inference
* Power consumption
* End-to-end MNIST inference on hardware

---

# 🎥 Demonstration Evidence

The repository includes practical evidence of the hardware setup.

### VSDSquadron PRO LED Blinking

The recorded demonstration shows:

1. VSDSquadron PRO board connected to the development system.
2. `sifive-welcome` application executed through Freedom Studio.
3. RISC-V target accessed using OpenOCD.
4. `SiFive` output observed through the terminal.
5. Blue LED blinking on the VSDSquadron PRO board.

Video:

```text
media/vsdsquadron_led_blink.mp4
```

---

# 🙏 Acknowledgments

I would like to acknowledge:

* **VLSI System Design (VSD)** for the RISC-V Edge AI course and learning resources.
* **SiFive** for the FE310-G002 documentation and RISC-V ecosystem.
* **TensorFlow** for machine-learning and model-quantization tools.
* The **RISC-V open-source community** for the tools, documentation, and ecosystem supporting embedded development.

---

# 📚 References

The project refers to the following types of technical resources:

* VSD RISC-V Edge AI course resources
* VSDSquadron PRO documentation
* SiFive FE310-G002 documentation
* RISC-V architecture documentation
* Freedom Studio documentation
* OpenOCD documentation
* TensorFlow documentation
* TensorFlow Lite / LiteRT documentation
* MNIST dataset

---

# 📌 Repository Status

**🚧 Active Development**

This repository is continuously updated with:

* Course activities
* Source code
* Experiments
* Neural-network models
* Quantization experiments
* RISC-V implementations
* Image-processing experiments
* Hardware validation
* Documentation
* Results
* Demonstration videos

---

## ⭐ About the Project

This project provides a practical exploration of how **Machine Learning and Neural Networks can be brought closer to resource-constrained RISC-V embedded systems**.

The long-term goal is to understand the complete journey from:

```text
AI Model
   ↓
Optimization
   ↓
Quantization
   ↓
Embedded C
   ↓
RISC-V
   ↓
VSDSquadron PRO
   ↓
Edge AI Inference
```

---

**Author:** Raj Sekar

**GitHub:** [rajasekl-srm](https://github.com/rajasekl-srm)

**Repository:** [RISC-V-Edge-AI-VSDSquadron-PRO](https://github.com/rajasekl-srm/RISC-V-Edge-AI-VSDSquadron-PRO)

---


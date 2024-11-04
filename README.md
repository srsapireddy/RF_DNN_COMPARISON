# RF_DNN_Comparison

# Lightweight Deep Learning Model for Automatic Modulation Classification in Cognitive Radio Networks

This repository contains an implementation of an optimized lightweight deep learning model designed for Automatic Modulation Classification (AMC) in Cognitive Radio (CR) networks. The primary objective is to reduce computational complexity while maintaining high classification accuracy, making the model suitable for deployment on resource-limited hardware such as FPGAs.

---

## Comparison Results

| Feature                        | Updated Paper Model       | Updated FPGA-Optimized Model     |
|--------------------------------|---------------------------|----------------------------------|
| **Convolution Type**           | Standard 3x3 & Asymmetric | Depthwise Separable              |
| **Number of Layers**           | 10 layers                 | Fewer layers                     |
| **Parameter Reduction Technique** | Bottleneck & Asymmetric | Depthwise Separable              |
| **Skip Connections**           | Used                      | Not used                         |
| **Pooling Strategy**           | Multiple Pooling Layers   | Single Global Pooling            |
| **Fully Connected Layers**     | One Fully Connected       | Minimized with Global Pooling    |
| **Parameter Count**            | 150,296                   | 39,893                           |
| **Inference Time (s/sample)**  | 0.000281                  | 0.001129                         |
| **Accuracy**                   | 45.6841                   | 54.0750                          |
| **Suitability for FPGA**       | Less suitable             | Highly suitable                  |

---

## Explanation of Key Features

1. ### Convolution Type
   - **Standard 3x3 & Asymmetric Convolution**: The paper model uses standard and asymmetric convolutions (e.g., 3x1 or 1x3 filters) to reduce the number of computations while learning from the data.
   - **Depthwise Separable Convolution**: The optimized model uses depthwise separable convolutions, which process each “channel” of data independently before combining them. This reduces memory and computational requirements, making it suitable for lightweight models.

2. ### Number of Layers
   - **10 Layers vs. Fewer Layers**: More layers allow for complex feature learning but require more memory and computational power. The optimized model uses fewer layers, making it more suitable for resource-constrained devices like FPGAs.

3. ### Parameter Reduction Technique
   - **Bottleneck & Asymmetric**: The paper model uses bottleneck layers and asymmetric convolutions (1x1, 3x1, and 1x3 filters) to reduce memory usage without losing valuable features.
   - **Depthwise Separable**: This efficient technique is employed in the optimized model to reduce parameter count significantly while maintaining performance.

4. ### Skip Connections
   - **Used vs. Not Used**: Skip connections in the paper model help prevent vanishing gradient issues, enabling effective learning in deeper networks. The optimized model, designed for simplicity, omits these connections for enhanced efficiency.

5. ### Pooling Strategy
   - **Multiple Pooling Layers**: The paper model gradually reduces data size across several layers to manage memory and retain detailed features.
   - **Single Global Pooling**: The optimized model simplifies data processing with a global pooling layer, reducing memory usage and making the model faster and lighter.

6. ### Fully Connected Layers
   - **One Fully Connected Layer vs. Minimized with Global Pooling**: Fully connected layers are resource-intensive. The optimized model minimizes these layers, using global pooling to achieve a more efficient, low-memory design.

7. ### Parameter Count
   - **150,296 vs. 39,893**: The optimized model has significantly fewer parameters, making it faster and more memory-efficient for FPGA or low-power devices.

8. ### Inference Time (s/sample)
   - **0.000281 vs. 0.001129**: Inference time measures how quickly the model processes a sample. Although the paper model has a slightly faster raw inference time, the FPGA-optimized model is designed to be more efficient on specialized hardware like FPGAs.

9. ### Accuracy
   - **45.6841 vs. 54.0750**: The optimized model achieves higher accuracy than the paper model, demonstrating its ability to balance efficiency with performance.

10. ### Suitability for FPGA
    - The optimized model is highly suitable for FPGA deployment due to its efficient design, reduced parameter count, and simplified layer structure, making it practical for resource-constrained environments.

---

## Getting Started

### Prerequisites

- Python 3.x
- PyTorch
- NumPy
- scikit-learn

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/lightweight-amc-model.git
   cd lightweight-amc-model


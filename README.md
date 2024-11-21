# MNIST Neural Network Classifier with Quadrant Feature Extraction

This project explores different neural network architectures for classifying MNIST digits. Instead of using the raw pixel data, a custom feature extraction method computes quadrant-wise averages, reducing the input dimensionality to enhance computational efficiency. Various models with different numbers of layers and nodes are compared to find the best-performing architecture.

## Features

- **Custom Feature Extraction:** 
  - Computes average pixel values for four quadrants of each image.
- **Neural Network Architectures:**
  - Trains and compares five models with varying layer counts and node configurations.
- **Evaluation Metrics:**
  - Tracks training and validation loss and accuracy for model performance comparison.

## Dataset

The project uses the MNIST dataset, which consists of:
- 60,000 training images.
- 10,000 test images.
Each image is a 28x28 grayscale representation of a digit (0-9).

## Project Overview

1. **Data Preprocessing:**
   - The images are flattened and normalized to the range `[0, 1]`.
   - A custom function computes quadrant-wise average pixel values for feature extraction.
   
2. **Train-Validation Split:**
   - Training data is split into 80% training and 20% validation subsets.

3. **Label Encoding:**
   - Labels are one-hot encoded to match the output format of the neural networks.

4. **Model Architectures:**
   - Single-layer networks with 16, 64, and 128 nodes.
   - Two-layer networks with combinations of 128-16 and 128-64 nodes.
   - All models use the ReLU activation function for hidden layers and softmax for the output layer.

5. **Training:**
   - Models are trained for 30 epochs using stochastic gradient descent (SGD) with a learning rate of 0.0001.

6. **Evaluation:**
   - Training and validation loss and accuracy are recorded for each model.
   - The best-performing model is evaluated on the test set.

## Results

| Model | Architecture     | Training Loss | Training Accuracy | Validation Loss | Validation Accuracy |
|-------|------------------|---------------|-------------------|-----------------|---------------------|
| 1     | 1 layer, 16 nodes  | 0.3590        | 0.8499            | 0.3685          | 0.8478              |
| 2     | 1 layer, 64 nodes  | 0.3602        | 0.8505            | 0.3698          | 0.8458              |
| 3     | 1 layer, 128 nodes | 0.3489        | 0.8552            | 0.3573          | 0.8521              |
| 4     | 2 layers, 128-16 nodes | 0.3497        | 0.8545            | 0.3586          | 0.8501              |
| 5     | 2 layers, 128-64 nodes | 0.3511        | 0.8543            | 0.3609          | 0.8493              |

**Best Model:** The single-layer network with 128 nodes achieved the best balance between training and validation performance.

**Test Performance:**  
- Loss: `0.3609`  
- Accuracy: `0.8508`

## Key Observations

- Increasing the number of layers and nodes generally improves performance.
- Model 3 (1 layer, 128 nodes) consistently outperforms others in validation accuracy.
- Small variations in loss and accuracy occur across multiple training runs due to stochastic factors.

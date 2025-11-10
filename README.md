# AnimusVision

**A Deep Learning Binary Classification System for Animal Recognition**

AnimusVision is a computer vision project that leverages deep learning to perform binary classification on three distinct animal species: **Elephants**, **Tigers**, and **Foxes**. This project implements both custom CNN architectures and transfer learning approaches to achieve high-accuracy animal detection.

---

## Project Overview

This project implements two different deep learning approaches:

1. **Custom CNN Model** - A lightweight convolutional neural network built from scratch
2. **Transfer Learning Model** - Leveraging pre-trained ResNet50 for enhanced performance

Each model is trained to perform binary classification, determining whether an input image contains the target animal or not.

---

## Model Performance

### Training Progress: Basic CNN Model

The custom CNN model demonstrates steady learning across all three animal classes, with effective convergence and minimal overfitting through dropout regularization and early stopping.

![Loss and Accuracy - Basic Model](assets/loss%20and%20accuracy%20basic%20model.png)

*The training curves show the model's learning progression for Elephant, Tiger, and Fox classification tasks. The validation loss closely tracks the training loss, indicating good generalization.*

---

### Model Architecture Comparison

We compared the performance of our custom CNN architecture against the ResNet50 transfer learning approach across all three animal species.

![Model Comparison](assets/model%20comparison%20plot.png)

*Comparative analysis showing training and validation loss for both model architectures. The transfer learning approach with ResNet50 demonstrates superior performance with faster convergence and lower final loss values.*

---

## Feature Visualization

### Activation Maps Analysis

Understanding what the model "sees" is crucial for interpretability. We visualized the convolutional layer activations to identify which regions of the image the model focuses on during classification.

![Feature Maps Comparison](assets/feature_maps_comparison.png)

*Heat map overlays showing the model's attention regions. The activation maps highlight key distinguishing features such as elephant trunks, tiger stripes, and fox facial structures, demonstrating that the model has learned meaningful patterns.*

---

## Technical Stack

- **PyTorch** - Deep learning framework
- **OpenCV** - Image processing
- **NumPy** - Numerical computations
- **Matplotlib** - Visualization
- **scikit-learn** - Data splitting and preprocessing
- **torchvision** - Pre-trained models and transforms

---

## Key Features

- **Dual Architecture Approach** - Compare custom CNN vs. transfer learning  
- **Weighted Loss Function** - Handles class imbalance effectively  
- **Early Stopping** - Prevents overfitting with patience-based monitoring  
- **Learning Rate Scheduling** - Adaptive learning rate reduction  
- **Feature Map Visualization** - Interpretable model decisions  
- **Comprehensive Evaluation** - Real-world testing with internet images  

---

## Results

The models achieve high accuracy across all three animal species:

- **Elephant Classification**: High precision with clear feature detection
- **Tiger Classification**: Strong pattern recognition of stripes and body structure  
- **Fox Classification**: Accurate identification of facial features and coloring

The transfer learning approach with ResNet50 consistently outperforms the custom CNN, demonstrating the power of pre-trained models on ImageNet for animal classification tasks.

---

## Model Architecture Details

### Custom CNN Model
- **Input**: 128×128 RGB images
- **Architecture**: Conv2d → ReLU → Dropout → MaxPool → FC layers
- **Regularization**: Dropout (0.4 and 0.6) to prevent overfitting
- **Output**: Binary classification (sigmoid activation)

### Transfer Learning Model (ResNet50)
- **Backbone**: Pre-trained ResNet50 (frozen layers)
- **Custom Head**: Dropout → Linear(256) → ReLU → Dropout → Linear(1)
- **Fine-tuning**: Only the final classification layers are trained
- **Output**: Binary classification with BCEWithLogitsLoss

---

## Dataset Structure

```
Tiger-Fox-Elephant/
├── elephant/              # Positive class - elephant images
├── Elephant_negative_class/  # Negative class - non-elephant animals
├── tiger/                 # Positive class - tiger images
├── Tiger_negative_class/     # Negative class - non-tiger animals
├── fox/                   # Positive class - fox images
└── Fox_negative_class/       # Negative class - non-fox animals
```

---

## Learning Insights

This project demonstrates several important concepts in deep learning:

1. **Data Augmentation Importance** - Enhancing dataset diversity improves generalization
2. **Transfer Learning Power** - Pre-trained models accelerate training and boost performance
3. **Class Imbalance Handling** - Weighted loss functions are crucial for unbalanced datasets
4. **Model Interpretability** - Activation maps provide insights into model decision-making
5. **Regularization Techniques** - Dropout and weight decay prevent overfitting




# Self-Driving Cars Using Semantic Segmentation with U-Net Model

## Introduction

The rapid advancement of autonomous vehicles has transformed modern transportation systems. One of the most critical components enabling self-driving cars to perceive and understand their surroundings is **semantic segmentation**. This technique allows a model to classify every pixel in an image into meaningful categories such as roads, vehicles, pedestrians, buildings, and obstacles.

In this project, a **U-Net architecture** was implemented to perform semantic segmentation on road scene images. The objective was to enhance environmental perception for self-driving cars by accurately classifying each pixel into one of **13 predefined classes**, contributing to a more reliable and intelligent autonomous driving system.

---

## Methodology

### 1. Model Architecture

The implemented U-Net model follows a classic **encoder–decoder architecture** designed to efficiently capture contextual information and restore spatial resolution for precise pixel-level classification.

#### Conv Block

Each convolutional block consists of:

* Two convolutional layers
* Batch normalization
* Leaky ReLU activation
* Optional dropout for regularization
* Conditional max pooling for downsampling

This structure enables effective feature extraction while reducing overfitting.

#### Upsampling Block

The upsampling block performs:

* Upsampling of feature maps
* Concatenation with corresponding encoder feature maps (skip connections)
* Two convolutional layers to refine spatial details

These skip connections help preserve fine-grained information lost during downsampling.

#### U-Net Model Structure

The full U-Net architecture is built by:

* Stacking multiple downsampling convolutional blocks (encoder)
* Adding bottleneck layers at the deepest level
* Applying symmetric upsampling blocks (decoder) to recover spatial resolution

This design ensures accurate segmentation by combining global context with local details.

---

### 2. Model Training

The model was trained using the **Adam optimizer** and **Sparse Categorical Crossentropy** loss function, which is well-suited for multi-class pixel-wise classification.

**Training Configuration:**

* Learning Rate: 0.001
* Epochs: 20
* Loss Function: Sparse Categorical Crossentropy
* Metric: Accuracy

#### Training Results

| Metric          | Value  |
| --------------- | ------ |
| Accuracy        | 97.60% |
| Validation Loss | 0.1860 |
| Learning Rate   | 0.001  |

The high accuracy and low validation loss indicate strong generalization performance on unseen data.

---

### 3. Visualization and Evaluation

Model performance was evaluated visually by comparing predicted segmentation masks with ground truth labels from the validation dataset.

#### Training & Validation Loss

The loss curves demonstrate stable convergence with no significant overfitting.

![Training & Validation Loss](https://github.com/user-attachments/assets/c72e9ea9-cc08-4e5e-818d-c2c2e6c51ae7)

#### Training & Validation Accuracy

Accuracy curves show consistent improvement throughout training, confirming effective learning.

![Training & Validation Accuracy](https://github.com/user-attachments/assets/894e2a27-58f0-48d7-9fce-a3300a44a505)

#### Sample Predictions

The following visualization illustrates model predictions compared to ground truth segmentation masks, highlighting accurate class separation and boundary detection.

![Model Predictions](https://github.com/user-attachments/assets/5b7daac0-b139-4d39-b6a5-8a6adc19bf5d)

---

## Conclusion

This project demonstrates the effectiveness of the **U-Net architecture** for semantic segmentation in self-driving car applications. Achieving an accuracy of **97.60%** with low validation loss confirms the model’s strong capability in understanding complex road scenes.

Future improvements may include:

* Architectural optimization
* Training with larger and more diverse datasets
* Integration into a full autonomous driving pipeline

Overall, the project highlights the significant role of deep learning–based semantic segmentation in advancing autonomous vehicle perception systems.

Self-Driving Cars Using Semantic Segmentation with U-Net Model
Introduction
The rise of autonomous vehicles has revolutionized modern transportation, with semantic segmentation playing a crucial role in enhancing the perception capabilities of self-driving cars. Semantic segmentation enables these cars to accurately distinguish between different elements in the environment, such as roads, vehicles, pedestrians, and obstacles, by classifying each pixel in an image.

In this project, I utilized a U-Net architecture for semantic segmentation to segment road scenes, thereby providing self-driving cars with a more detailed understanding of their surroundings. The model was designed to classify each pixel in an image into one of 13 predefined classes, facilitating the creation of a robust perception system for autonomous vehicles.
Methodology
1. Model Architecture
The U-Net architecture used in this project follows an encoder-decoder structure, featuring convolutional and upsampling blocks to capture and recover spatial information effectively.
Conv Block:
The Conv block consists of two convolutional layers followed by batch normalization and Leaky ReLU activation. The dropout probability and max pooling are applied conditionally.
Upsampling Block:
The upsampling block combines feature maps from the encoder with feature maps from the decoder, followed by two convolutional layers.
U-Net Model:
The U-Net model is constructed by stacking downsampling conv blocks, followed by bottleneck layers, and upsampling blocks to recover spatial resolution.
2. Training
The model was compiled with the Adam optimizer and Sparse Categorical Crossentropy loss function, ensuring pixel-wise classification. The learning rate was set to 0.001, and the model was trained for 20 epochs.
• Learning Rate: 0.001
• Epochs: 20
• Loss Function: Sparse Categorical Crossentropy
• Metrics: Accuracy
Training Results

| Metric        | Value |
|---------------|-------|
| Accuracy      | 97.60%|
| Validation Loss| 0.1860 |
| Learning Rate | 0.0010|



3. Visualization and Evaluation
The following screenshots display predictions from the validation dataset, comparing the ground truth and the model's predicted segmentation:

Training & Validation Loss Plot:


![UNETmodel_Semanticesegmentation-MohamedAshraf-Depi - Google Chrome 10_18_2024 4_29_02 PM](https://github.com/user-attachments/assets/c72e9ea9-cc08-4e5e-818d-c2c2e6c51ae7)


 
Training & Validation Accuracy Plot:

![UNETmodel_Semanticesegmentation-MohamedAshraf-Depi - Google Chrome 10_18_2024 4_30_43 PM](https://github.com/user-attachments/assets/894e2a27-58f0-48d7-9fce-a3300a44a505)

 
Showing some Predictions using the model after training 

![UNETmodel_Semanticesegmentation-MohamedAshraf-Depi - Google Chrome 10_18_2024 4_31_04 PM](https://github.com/user-attachments/assets/5b7daac0-b139-4d39-b6a5-8a6adc19bf5d)


Conclusion
This project demonstrates how a U-Net model can be effectively applied to semantic segmentation for self-driving cars. The model achieved an accuracy of 97.60%, with low validation loss, indicating its strong potential for real-world application in autonomous vehicles. Future improvements could focus on optimizing the architecture and integrating the model into a broader self-driving system.

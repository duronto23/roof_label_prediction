# Roof Label Prediction with NN

## Problem Statement
Given two sets of satellite images:
1. **Training Set**: Includes images with corresponding labels that indicate the roofs.
2. **Test Set**: Consists of images without labels.

The task is to train a neural network using the labeled data from the first set and predict labels for the second set of images.

## Solution Overview
To solve this problem, I implemented neural network models leveraging **DeepLabV3** and **U-Net** architectures. For DeepLabV3, I experimented with multiple pre-trained base models and performed hyperparameter tuning to optimize performance. After evaluating the models based on accuracy, I found that **DeepLabV3 with Xception as the base model** achieved the best performance.

Additionally, I included **U-Net** in the solution because of its strength in accurately capturing boundaries and edges. The predictions from U-Net and the best-performing DeepLabV3 model were saved for further analysis.

## Key Highlights
### DeepLabV3
- **Architecture**: Designed for semantic segmentation, DeepLabV3 utilizes Atrous Spatial Pyramid Pooling (ASPP) to capture features at multiple scales.
- **Base Models**: Tried several pre-trained backbones, including:
  - ResNet-50
  - ResNet-101
  - Xception
  - MobileNetV2
- **Best Performer**: DeepLabV3 with **Xception** base model achieved the highest accuracy during evaluation.

### U-Net
- **Architecture**: U-Net is a fully convolutional network that is widely recognized for its ability to capture fine-grained details, making it ideal for tasks requiring precise boundary and edge detection.
- **Strengths**: U-Net demonstrated superior performance in segmenting boundaries and edges of the roofs compared to DeepLabV3.

### Why Used Both Models for Prediction?
**DeepLabV3** excels in general segmentation tasks and scales well with larger datasets, and it is the best performer in this case.
<br>
I also included **U-Net** in prediction for reference. However, it should ideally not be part of the solution as it was showing less accuracy during validation.

## Implementation Details
### Training
1. **Data Preparation**:
   - Resized all input images to 256x256.
   - Normalized pixel values to improve convergence.
2. **Hyperparameter Tuning**:
   - Experimented with different learning rates, batch sizes, and optimizer settings.
   - Grid search was performed to identify the optimal parameters.

### Results
- **DeepLabV3 with Xception** achieved the best accuracy on the validation set.


## Conclusion
This project demonstrates the use of **DeepLabV3** and **U-Net** for roof segmentation. While DeepLabV3 with Xception backbone emerged as the best performer, U-Net's capability to accurately detect edges adds value to the overall solution. Combining these models ensures robust and precise segmentation results.

Feel free to explore the code and adapt it for your specific requirements. Contributions are welcome!


# Machine Unlearning: A Case Study on CNN with MNIST Digits

## Description

This project explores the concept of machine unlearning using a Convolutional Neural Network (CNN) trained on the MNIST digits dataset. The objective is to remove the influence of a specific class (class 6) from the trained model and introduce a new class (class 7) while maintaining the model’s performance and efficiency.
[Download the Report](https://github.com/user-attachments/files/16317361/DLAI_Final_Project_Report.pdf)


## Features

- **Baseline Approach**: Identifies crucial weights related to the unlearned class, freezes the rest, and retrains the model with a custom loss function.
- **Innovative Approach**: Trains two separate models, integrates their parameters to exclude the unlearned class, and retrains to incorporate the new class.
- **Naive Unlearning**: Retrains the model from scratch on the modified dataset, excluding the class to be unlearned.

## Methodology

1. **Baseline Approach**:
   - Identify significant weights for class 6 and freeze them.
   - Merge datasets of classes 6 and 7 into a single class 7.
   - Retrain the model with a custom loss function that penalizes class 6 predictions and favors class 7.

2. **Innovative Approach**:
   - Train a model only on data from class 6.
   - Subtract the weights of this model from the pretrained model.
   - Add a new fully connected layer to predict 8 classes (0 to 7) and retrain.

3. **Naive Unlearning**:
   - Discard class 6 data and retrain the model from scratch.
   - Merge images of classes 6 and 7 into a single class 7.
   - Modify the initial model’s fully connected layer to output 8 values and retrain.

## Results

The project compares these methods based on training time and accuracy to identify the most effective strategy for machine unlearning. The evaluation shows that each method has its own advantages and trade-offs, with the Innovative Approach demonstrating significant effectiveness in our case study.

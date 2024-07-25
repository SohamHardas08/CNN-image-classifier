# CNN-image-classifier

This project is a Convolutional Neural Network (CNN) based classifier designed to distinguish between organic and recyclable waste.
Info about the dataset and credits : https://www.kaggle.com/datasets/techsash/waste-classification-data

## Key Features

- **Convolutional Neural Network (CNN)**: Utilizes a CNN architecture to classify images of waste as either organic or recyclable plastic.
- **L2 Regularization**: Applied L2 regularization with a factor of 0.01 to prevent overfitting by penalizing large weights.
- **Early Stopping**: Implemented early stopping with a patience of 3 epochs to halt training when the model's performance on a validation set stops improving, ensuring efficient training.


## Data transformation

- Image scaling for consistent feature extraction
- Converted 8-bit image to a binary black and white image

## The model
Input layer:
- The input layer takes the image of size 256x256 and 3 pixels, the activation function being 'relu'

Hidden layers
- Conv2D layers with 32 and 16 filters of size 3x3, each followed by MaxPooling2D layers.
- Flattens the 3D output from the convolutional layers into a 1D vector.
- A fully connected dense layer with 256 neurons and ReLU activation. L2 regularization is applied to this layer.

Output layer:
- This layer has a single neuron with a sigmoid activation function, which outputs a value between 0 and 1, suitable for binary classification.

Used cudatoolkit to boost the training time, GPU: Nvidia GTX 1650 (mobile) (6hrs with CPU, 30minutes with GPU)

### Without regularisation the validation loss and traninig loss:

![](https://github.com/user-attachments/assets/6c1983e1-7320-4b1e-a7aa-a245670baa60)


### After L2 regularisation and early stopping callback:


![Screenshot 2024-07-25 195816](https://github.com/user-attachments/assets/dfc85c0d-ead2-4157-a5ff-f05ce20db154)


### Confusion Matrix:

![image](https://github.com/user-attachments/assets/51c9ea43-e939-47db-a673-a7edc7b0ddf3)

## Evalutation Metrics
- Precision : 0.85383
- Accuracy : 0.8820
- Recall : 0.87809











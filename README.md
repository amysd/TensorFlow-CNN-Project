# TensorFlow CNN Image Classification

## About the Project

This project is based on the official TensorFlow Convolutional Neural Network (CNN) image classification tutorial.

The original tutorial uses the CIFAR-10 dataset with 10 image classes. For this project, I created a modified input dataset by selecting three classes from CIFAR-10:

- Class 0: Airplane
- Class 1: Automobile
- Class 2: Bird

The CNN was trained using this modified dataset and then refined to compare the performance of different CNN configurations.

## Requirements

This project was completed using:

- Google Colab
- Python
- TensorFlow
- NumPy
- Matplotlib

Google Colab was used because TensorFlow was not installed locally.

## How to Load the Project

1. Download or open the `cnn.ipynb` file.
2. Open Google Colab:
   https://colab.research.google.com/
3. Select **File → Upload notebook**.
4. Upload `cnn.ipynb`.
5. Make sure the runtime is connected.
6. Run the notebook from the beginning using **Runtime → Run all**.

The CIFAR-10 dataset will be downloaded automatically when the dataset cell is executed.

## How the CNN Works

The CNN uses several layers to classify the images:

- **Conv2D layers** extract visual features from the images.
- **MaxPooling2D layers** reduce the size of the feature maps.
- **Flatten** converts the feature maps into a one-dimensional format.
- **Dense layers** perform the classification.
- **Dropout** was used in the refined models to help reduce overfitting.

The images are normalized from values between 0 and 255 to values between 0 and 1 before training.

## CNN Refinements

Three CNN configurations were tested:

### Original CNN

The original CNN architecture was trained using the modified three-class dataset.

Validation accuracy:

**89.90%**

### First Refinement

The first refinement added:

- Data augmentation
- Random horizontal flipping
- Random rotation
- Random zoom
- Dropout

Validation accuracy:

**86.83%**

This configuration performed lower than the original CNN.

### Second Refinement

The second refinement used the original CNN structure with a smaller dropout rate of 0.3.

Validation accuracy:

**90.23%**

This was an improvement over the original CNN.

## Results

| Model | Validation Accuracy |
|---|---:|
| Original CNN | 89.90% |
| First Refinement | 86.83% |
| Second Refinement | 90.23% |

The second refinement achieved the highest validation accuracy in this experiment, improving the original CNN by **0.33 percentage points**.

The notebook also includes a line graph comparing the validation accuracy of all three models across the training epochs.

## How to Interpret the Results

Validation accuracy represents how accurately the model classified images that were not used for training.

A higher validation accuracy indicates that the model correctly classified a larger percentage of the validation images.

The results also demonstrate that modifying a neural network does not always improve its performance. The first refinement decreased accuracy, while the second refinement produced a small improvement.

## Files

- `cnn.ipynb` — Google Colab notebook containing the CNN implementation, dataset preparation, training, refinements, results, and graphs.
- `README.md` — Instructions and description of the project.

## Source

This project is based on the TensorFlow CNN image classification tutorial:

https://www.tensorflow.org/tutorials/images/cnn

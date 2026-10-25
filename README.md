# CNN Fruits Classification

A Deep Learning project that uses a Convolutional Neural Network (CNN)
to classify fruit images into 12 categories using TensorFlow and Keras.

## Project Overview

This notebook demonstrates an image-classification workflow: - Load
images from a folder-based dataset. - Split the dataset into training
(80%) and validation (20%) subsets. - Resize images to `150 × 150`
pixels and use batches of 32 images. - Normalize pixel values to the
`0–1` range. - Build and train a CNN model. - Evaluate the model using
validation loss and accuracy. - Plot training/validation accuracy and
loss. - Save the trained model and predict the class of a new fruit
image.

## Fruit Classes

The prediction code lists these 12 classes:

1.  Apple
2.  Banana
3.  Blueberry
4.  Cherry
5.  Grape
6.  Kiwi
7.  Lemon
8.  Mango
9.  Orange
10. Papaya
11. Pineapple
12. Strawberry

Make sure the folder names in your dataset match the class names
expected by your project.

## Technologies Used

-   Python
-   TensorFlow / Keras
-   NumPy
-   Matplotlib

## Project Structure

``` text
CNN-Fruits-Classification/
├── main file.ipynb
├── README.md
├── requirements.txt
├── datasets/              # Keep the dataset locally; upload only if size/licensing permits
└── testing_images/
    └── apple.jpg          # Optional sample image for prediction
```

The trained model file (`fruit_classifier.keras`) is not required to
view the notebook, so it can be kept out of the repository if it exceeds
GitHub's file-size limit.

## Dataset Setup

The notebook currently contains a local Windows dataset path. Update the
`dataset_path` cell to the location of your own dataset before running
the notebook.

Expected folder-based dataset layout:

``` text
datasets/
├── Apple/
│   ├── image1.jpg
│   └── ...
├── Banana/
├── Blueberry/
├── Cherry/
├── Grape/
├── Kiwi/
├── Lemon/
├── Mango/
├── Orange/
├── Papaya/
├── Pineapple/
└── Strawberry/
```

Each fruit category should have its own folder of images. The notebook
uses `image_dataset_from_directory` to load the images and create an
80/20 training-validation split.

## Installation

Install the required libraries:

``` bash
pip install tensorflow numpy matplotlib
```

Or use the provided `requirements.txt` file:

``` bash
pip install -r requirements.txt
```

## How to Run

1.  Clone or download this repository.
2.  Install the dependencies.
3.  Download or place the fruit dataset in the `datasets/` folder.
4.  Update `dataset_path` in the notebook to point to your dataset
    folder.
5.  Open `main file.ipynb` in Jupyter Notebook or JupyterLab.
6.  Run the notebook cells in order.
7.  To test a new image, update `img_path` to the image you want to
    classify. The example code uses `testing_images/apple.jpg`.

## Model Architecture

The notebook builds a Sequential CNN containing: - Three convolutional
layers with 32, 64, and 128 filters. - Max-pooling layers after each
convolutional layer. - A flatten layer. - A dense layer with 128 units
and ReLU activation. - Dropout with a rate of 0.5. - A 12-unit softmax
output layer.

The model is compiled with the Adam optimizer and sparse categorical
cross-entropy loss, and trained for 10 epochs.

## Evaluation

The notebook evaluates the model on the validation dataset and prints
validation loss and validation accuracy. It also plots training versus
validation accuracy and loss.

No fixed accuracy score is stated here because the result depends on the
dataset and training run. Check the notebook output for your actual
results.

## Model Output

After training, the notebook saves the model as:

``` text
fruit_classifier.keras
```

## Notes

-   The dataset and trained model are not included in this repository by
    default.
-   The notebook needs a valid dataset path and a test-image path to run
    successfully.
-   Ensure that the test image belongs to one of the fruit categories
    supported by the model.


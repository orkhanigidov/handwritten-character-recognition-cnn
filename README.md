# Handwritten Character Recognition using CNN in MATLAB

This repository contains a Convolutional Neural Network (CNN) implemented in MATLAB for recognizing and classifying handwritten English characters. The model is trained on the EMNIST dataset and can predict characters from digital drawings or scanned images.

## Features
* **Custom CNN Architecture:** Built from scratch using MATLAB's Deep Learning Toolbox.
* **EMNIST Dataset Integration:** Includes custom scripts to load, parse, and preprocess the EMNIST raw dataset.
* **Multiple Testing Environments:** * `test_painter.m`: Optimized for digital handwritten images.
    * `test_scanner.m`: Includes median filtering (`medfilt2`) optimized for scanned paper documents.
* **Bounding Box Extraction:** Automatically detects and isolates individual characters within an image using region properties.

## Dataset
This project uses the **EMNIST (Extended MNIST)** dataset, specifically the letters split. 
* You can download the dataset from the official NIST website: [https://www.nist.gov/itl/products-and-services/emnist-dataset](https://www.nist.gov/itl/products-and-services/emnist-dataset).
* Extract the downloaded files and place the images and labels inside the `/dataset` folder.

## Prerequisites
To run this project, you need MATLAB installed along with the following toolboxes:
* Deep Learning Toolbox
* Image Processing Toolbox

## How to Use

### 1. Training the Model
1. Ensure the EMNIST dataset files are placed in the `/dataset` directory.
2. Open and run the `main.m` script.
3. The script will load the images, build the CNN layers, and start the training process. 
4. Once training is complete, the trained model will be saved automatically as `matlab.mat` in your workspace.

### 2. Testing the Model
You can test the model with your own handwritten images. An example test image (`test.png`) is provided in the `test images/` folder.
* **For digital drawings:** Run `test_painter.m`. A file dialog will open; select your `.png` image.
* **For scanned text:** Run `test_scanner.m`. This script applies a 2-D median filter to reduce noise from scanning.
* The script will display the image with red bounding boxes around the detected characters and print the recognized text in the MATLAB command window.

## Project Structure
* `main.m`: Main script to define the CNN architecture, set training options, and train the model.
* `loadEMNIST.m`, `loadImages.m`, `loadLabels.m`: Helper functions to read and format the idx-formatted EMNIST data.
* `test_painter.m` & `test_scanner.m`: Testing scripts for model inference and image processing.
* `app_painter.mlapp` & `app_scanner.mlapp`: MATLAB App Designer GUI files for interactive use.

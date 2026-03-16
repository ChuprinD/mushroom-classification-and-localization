# Deep Learning Minor --- Assignment 2

## Overview

This project implements a computer vision pipeline for mushroom
classification and localization using deep learning.

The goal of this assignment is to train models capable of:

1.  Classifying mushroom species from images
2.  Improving classification performance using transfer learning
3.  Detecting and localizing mushrooms within images using bounding
    boxes

The dataset contains more than 6000 images of mushrooms from 9 different
species. The project follows the structure required in the assignment
specification and is implemented using TensorFlow/Keras with Python
3.11.

------------------------------------------------------------------------

# Repository Structure

. ├── data\
│ └── raw\
│ └── mushrooms \# dataset must be placed here (not included in repo)\
│\
├── step1_data_preparation.ipynb\
├── step2_transfer_learning.ipynb\
├── step3_object_localization.ipynb\
│\
├── requirements.txt\
└── README.md

------------------------------------------------------------------------

# Dataset

The original dataset is **NOT included in this repository** because it
is too large to store in Git.

To run the notebooks you must manually place the dataset in:

data/raw/mushrooms/

Expected structure:

data/raw/mushrooms/\
species_1/\
image1.jpg\
image2.jpg\
species_2/\
image1.jpg\
...

Once the dataset is placed in this directory the notebooks should run
without modification.

------------------------------------------------------------------------

# Project Structure

The project consists of three main notebooks that should be executed in
sequence:

1.  step1_data_preparation.ipynb
2.  step2_transfer_learning.ipynb
3.  step3_object_localization.ipynb

Each notebook corresponds to a specific step in the assignment.

------------------------------------------------------------------------

# Step 1 - Data Preparation

Notebook: step1_data_preparation.ipynb

This step prepares the dataset for training.

Main operations:

-   dataset inspection
-   removal of corrupted images
-   image resizing and normalization
-   splitting the dataset into:
    -   training set
    -   validation set
    -   test set
-   implementation of data augmentation such as:
    -   random rotations
    -   flips
    -   scaling

Efficient TensorFlow data pipelines are created to feed the data into
the models.

Data augmentation helps improve generalization and reduce overfitting.

------------------------------------------------------------------------

# Step 2 - Custom Classification Models

Notebook: step2_transfer_learning.ipynb

Several custom CNN architectures are explored for mushroom
classification.

Different architectures are tested with variations in:

-   number of convolutional layers
-   filter sizes
-   dropout layers
-   dense layer sizes

The best architecture is selected after initial experiments and then
fully trained, validated and evaluated.

Evaluation metrics include:

-   Accuracy
-   Precision
-   Recall
-   F1-score

A confusion matrix is used to analyze classification performance across
species.

------------------------------------------------------------------------

# Step 3 - Transfer Learning

Notebook: step2_transfer_learning.ipynb

Transfer learning is used to improve classification performance using
pretrained convolutional neural networks.

Backbones explored include:

-   ResNet
-   EfficientNet
-   MobileNet
-   VGG

Workflow:

1.  Load pretrained backbone
2.  Freeze convolutional layers
3.  Add custom classification head
4.  Train classifier layers
5.  Fine‑tune selected layers if necessary

The best model is selected and fully trained.

Performance is compared with the custom CNN model.

------------------------------------------------------------------------

# Step 4 - Image Annotation

Object localization requires bounding box annotations.

Because the dataset originally contains only labels, bounding boxes must
be created manually using an external annotation tool.

Annotation files contain:

-   image name
-   object class
-   bounding box coordinates

These annotations are later used to train the localization model.

------------------------------------------------------------------------

# Step 5 - Object Localization

Notebook: step3_object_localization.ipynb

A model is implemented that predicts where a mushroom is located in an
image.

The model predicts:

-   mushroom class
-   bounding box coordinates

Evaluation metrics include:

-   Intersection over Union (IoU)
-   localization error
-   classification accuracy of detected objects

Predictions are visualized by drawing bounding boxes on images.

------------------------------------------------------------------------

# Requirements

Python 3.11

Required libraries:

-   numpy
-   pandas
-   scikit-learn
-   tensorflow
-   matplotlib
-   pillow
-   opencv-python
-   jupyter
-   openpyxl

------------------------------------------------------------------------

# Setup (Virtual Environment)

### Windows (PowerShell)

``` powershell
py -3.11 -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install -U pip
python -m pip install -r requirements.txt
```

### macOS / Linux

``` bash
python3.11 -m venv .venv
source .venv/bin/activate
python -m pip install -U pip
python -m pip install -r requirements.txt
```

------------------------------------------------------------------------

# Running the Project

1.  Place the dataset in:

data/raw/mushrooms/

2.  Open the repository in VS Code or Jupyter.

3.  Select the `.venv` interpreter.

4.  Run the notebooks in order:

5.  step1_data_preparation.ipynb\

6.  step2_transfer_learning.ipynb\

7.  step3_object_localization.ipynb

------------------------------------------------------------------------

# Output

The project produces:

-   trained classification CNN models
-   comparison between custom CNN and transfer learning models
-   evaluation metrics and confusion matrices
-   object localization predictions
-   visualizations with predicted bounding boxes

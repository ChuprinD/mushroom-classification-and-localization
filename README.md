# Deep Learning Minor --- Assignment 2

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


------------------------------------------------------------------------

# Requirements

Python 3.11

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

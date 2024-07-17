# ds-ml-beer-challenge

## Project Description
This project focuses on the development and evaluation of machine learning models to predict credit card application and crime rate. The primary tools used in this project include PyCaret, LightGBM, and various Python libraries.

### Analysis Cases
This repository contains two analysis cases:

1. **Credit Card Application**:
   - **Objective**: Build a classification model with a binary target that predicts whether a credit card application should be approved or not.
   - **Notebook**: `credito_model.ipynb`

2. **Crime Rate**:
   - **Objective**: Build a regression model to predict the crime rate.
   - **Notebook**: `crimen_model.ipynb`

## Configuration
To set up the environment for this project, follow the steps below:

### Step 1: Install Homebrew (if not already installed) outside of your development environment

1. Open your terminal (outside of your development environment) and run the following command to install Homebrew:
    ```bash
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```

2. Add Homebrew to your PATH:
    ```bash
    nano ~/.zshrc
    export PATH="/usr/local/bin:/opt/homebrew/bin:$PATH"
    ```

3. Reload your shell configuration:
    ```bash
    source ~/.bash_profile  # or source ~/.zshrc, depending on your shell
    ```

### Step 2: Set Up Your Virtual Environment within your development tool

1. Activate your virtual environment within your development tool
    ```bash
    conda activate myenv
    ```

2. Install the required libraries using 'brew' and 'pip':
    ```bash
    brew install libomp
    ```

3. After installing libomp, export the necessary environment variables for LightGBM:
    ```bash
    nano ~/.zshrc
    export CMAKE_ARGS="-DOpenMP_C_FLAGS=-Xpreprocessor\ -fopenmp\ -I$(brew --prefix libomp)/include -DOpenMP_C_LIB_NAMES=omp -DOpenMP_CXX_FLAGS=-Xpreprocessor\ -fopenmp\ -I$(brew --prefix libomp)/include -DOpenMP_CXX_LIB_NAMES=omp -DOpenMP_omp_LIBRARY=$(brew --prefix libomp)/lib/libomp.dylib"
    ```

4. Install the LightGBM library:
    ```bash
    pip install lightgbm
    ```

### Step 3: Installation of required dependencies.

To install the required dependencies, run:
```bash
pip install -r requirements.txt
```

## Usage
To run the models and analyses, use the provided Jupyter notebooks:

- `credito_model.ipynb`: Credit model analysis and training
- `crimen_model.ipynb`: Crime model analysis and training

## Contribution
Contributions are welcome! Please submit a pull request or open an issue to discuss any changes.

Feel free to further customize this `README.md` file to fit your specific needs.


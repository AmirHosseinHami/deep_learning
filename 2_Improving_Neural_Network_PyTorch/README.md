## What You Will Learn in This Assignment

- How to load and explore a real-world dataset in Python and Google Colab.
- How to handle class imbalance and split data for training, validation, and testing.
- How to preprocess data for PyTorch and create custom DataLoaders.
- How to build, train, and evaluate a fully connected neural network using PyTorch.
- How to use CUDA, optimizers, and regularization techniques like Dropout and L2.
- How to visualize model performance with metrics and confusion matrices.

### Dataset Introduction

The Covertype dataset was prepared by the U.S. Forest Service and is available in the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/31/covertype). The main goal of this dataset is to predict the forest cover type of various regions in Colorado, USA based on geographical and environmental features.

This dataset contains **581,012 samples** and **54 features**. The target variable is a discrete value with **7 different classes**, where each class represents a specific type of vegetation, such as pine forest, spruce trees, etc. You can refer to the dataset website for the exact class descriptions.

### Some of Important Features

- **Elevation**: Height above sea level (in feet), a numeric feature that strongly affects vegetation type.
- **Aspect**: The direction of the slope (0 to 360 degrees).
- **Slope**: The steepness of the land.
- **Horizontal & Vertical Distance to Hydrology**: Distance to the nearest water source such as a river or lake.
- **Hillshade features**: Three features representing sunlight intensity at different times of the day (9 AM, 12 PM, and 3 PM).
- **Soil Type**: 40 binary features representing soil categories.
- **Wilderness Area**: 4 binary features representing protected forest areas.

Using this code, you can load the dataset in Google Colab and view its metadata.

```python
!pip install ucimlrepo
from ucimlrepo import fetch_ucirep

# Fetch dataset
covertype = fetch_ucirepo(id=31)

# Data as pandas DataFrames
X = covertype.data.features
y = covertype.data.targets

# Metadata
print("\nDataset overview:")
display(covertype.metadata)
print("\nTarget distribution:")
print(y.value_counts())
```

## Data Preparation

Load the dataset using the provided code. Then, perform a brief Exploratory Data Analysis (EDA) on it, such as checking for NULL values, duplicate records, and normalizing features if necessary (note that some of these steps have already been done on this dataset, so extensive cleaning is not required).

Next, use `train_test_split` to split the data into three sets: **training (90%)**, **validation (5%)**, and **test (5%)**. Since this dataset is highly class-imbalanced, it is necessary to use the `stratify` parameter. Research how it works and explain what issues may arise if it is not used.

## Data Analysis

- Plot histograms to show the number of samples for each class in the training, validation, and test sets.
- Plot histograms or bar plots for selected features to better understand their distribution.You can also use other visualization techniques such as heatmaps to explore feature correlations.

## Data Preparation for PyTorch

- Create a **custom dataset class** that reads the data and labels from Numpy or Pandas.
- Convert the data to `torch.tensor` if needed.
- Create **DataLoaders** for the training, validation, and test sets.
- Enable **shuffle=True** for the training DataLoader.

## Neural Network Model

- Define a **fully connected neural network** class.
- Layers can follow this structure:
  - `Linear → BatchNorm → ReLU → Dropout → Linear → ...`
- Input dimension should match the number of features (54) and output dimension should match the number of classes (7).
- Use **CrossEntropyLoss** as the loss function.

## CUDA Implementation

- Check if **CUDA** is available (e.g., using Google Colab GPU).
- Move the **model, data, and labels** to the CUDA device.

## Optimizer and Regularization

- Use a suitable optimizer such as **Adam** or **SGD**.
- If using **L2 regularization**, set the `weight_decay` parameter.
- Optionally, adjust the learning rate during training using **StepLR** or **ReduceLROnPlateau**.

## Training and Validation

- Implement `train()` and `validate()` functions that include:
  - Iterating over the DataLoader
  - Calculating loss and accuracy
  - Using `model.train()` and `model.eval()` modes
  - Zeroing gradients
- At the end of each epoch, save loss and accuracy and plot them.

## Final Testing and Performance Reporting

- Evaluate the trained model on the test set and report the final accuracy.
- Plot a confusion matrix to analyze which classes the model performs well on and which classes it struggles with.

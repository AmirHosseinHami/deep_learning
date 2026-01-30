**This assignment is essentially based on the [Kaggle Titanic Competition](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://www.kaggle.com/competitions/titanic&ved=2ahUKEwjx54KfvrGSAxW_R_EDHZL7ACcQFnoECA4QAQ&usg=AOvVaw231G6wh38j8fp0KZOLmyab).**

## What You Will Learn in This Assignment
- How to implement a simple neural network from scratch, without using deep learning frameworks.
  
---

The goal is to train a model that predicts whether a Titanic passenger survived or not. The network architecture must have at least one hidden layer with a minimum of 3 neurons.

## 1. Dataset Description
You are provided with the dataset files: `train.csv` and `test.csv`. The dataset includes the following features:

- **survival**: Whether the passenger survived the disaster (0 = No, 1 = Yes)  
- **pclass**: Ticket class (1 = First, 2 = Second, 3 = Third); indicates socio-economic status  
- **sex**: Gender of the passenger  
- **age**: Age in years (decimal values less than 1 for infants)  
- **sibsp**: Number of siblings or spouses aboard  
- **parch**: Number of parents or children aboard  
- **ticket**: Ticket number  
- **fare**: Ticket fare  
- **cabin**: Cabin number  
- **embarked**: Port of embarkation  


## 2. Steps to Complete

### 2.1 Load Data 
Load the dataset using libraries such as `pandas` and explore it.

### 2.2 Data Preprocessing 
- Handle missing values by either imputing them or removing the corresponding rows.  
- Convert categorical features to numerical values.  
- Normalize numerical features.  
- Split the training data into:  
  - **X_train**: Feature matrix  
  - **Y_train**: Labels (0 or 1)  
  - Prepare **X_test** for the test data.

### 2.3 Neural Network Implementation 
- Initialize the weights and biases with small random values.  
- Implement **forward propagation** to compute the network output.  
- Implement **backpropagation** to compute gradients.  
- Update the parameters using **gradient descent**.

### 2.4 Prediction Function 
Write a function that takes a feature vector as input and predicts whether the passenger survived or not.

### 2.5 Training and Evaluation 
- Train your model on the training data.  
- Plot the cost function changes over epochs.  
- Save predictions for the test data into a CSV file.  
- Report the accuracy of your model.  
- Optionally, submit your predictions to the **Kaggle Titanic Competition**!



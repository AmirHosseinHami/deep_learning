## What You Will Learn in This Assignment

- How to build and train a neural network using **TensorFlow** to predict students’ GPA.


## 1.1 Dataset Description  

The files train.csv and test.csv are provided to you. This dataset contains the following features:

- StudentID: Unique identifier for each student (this feature is not considered as an input)
- Age: Student’s age
- Gender: Student’s gender (0 for male, 1 for female)
- Ethnicity: Student’s ethnicity
- ParentalEducation: Level of parents’ education
- StudyTimeWeekly: Weekly study time (between 0 and 20 hours)
- Absences: Number of student absences during the academic year (between 0 and 30)
- Tutoring: Whether the student receives private tutoring (0 for no, 1 for yes)
- ParentalSupport: Level of parental support
- Extracurricular: Participation in extracurricular activities (0 for no, 1 for yes)
- Sports: Participation in sports programs (0 for no, 1 for yes)
- Music: Participation in music programs (0 for no, 1 for yes)
- Volunteering: Participation in volunteering programs (0 for no, 1 for yes)
- GPA: Student’s GPA (target variable, between 0 and 4)

## 1.2 Implementation Steps  

## 1. Data Loading:  
Load the data using libraries such as pandas and separate the features and the target variable (GPA).

## 2. Data Preprocessing :  
Process the data so that it is suitable for training a neural network. These steps include:
- Imputing missing values or removing the corresponding rows
- Converting categorical features into numerical values
- Normalizing numerical features

## 3. Model Definition :  
Define a neural network model for predicting students’ GPA. This model must include:
- An input layer that matches the number of features
- One or more hidden layers
- An output layer with a single neuron (since GPA is a continuous value)

## 4. Model Training :  
Train your model using the following:
- Mean Squared Error (MSE) as the loss function for regression
- An optimizer such as Adam
- Monitoring the training loss  
Train the model for a reasonable number of epochs and track the changes in loss over these epochs.

## 5. Plotting Training and Validation Loss :  
After training, plot the training and validation loss versus the number of epochs to observe the model’s performance.

## 6. Model Testing :  
Evaluate your model on the test data and compute the R² metric, which is defined as:

**R² = 1 − ( Σᵢ (yᵢ − ŷᵢ)² ) / ( Σᵢ (yᵢ − ȳ)² )**

where yᵢ are the true values, ŷᵢ are the predicted values, and ȳ is the mean of the true values.

<details>
  <summary>Table Of Contents</summary>
  
  1. [About The Project](#about-the-project)
      - [Built With](#built-with)
  2. [Loading and Explore Data](#loading-and-explore-data)
  3. [Data Wrangling on multiple tables]
       - [Extract and Create Features from different tables](#extract-and-create-features-from-different-tables)
       - [Concatenate and Join the tables](#concatenate-and-join-the-tables)
  5. [Data Cleansing and Transformation](#data-wrangling-on-multiple-tables)
       - [Missing Values and Outliers](#missing-values-and-outliers)
  7. [Machine Learning Models](#machine-learning-models)
</details>

# About The Project
The purpose of this project is to create a model that will predict whether independent variables such as driver or grandprix circuit affect then chances of a f1 driver being able to win the race In F1, most drivers do finish the race except for a handful of drivers. There are many factors that will result in a driver not being able to finish a race. This may be due to the face that they are unlucky and are always running into issues. This might also be due to the fact that some drivers are not as skillful as others resulting in them colliding with other cars or spinning off the track due to inability to control the car hence not being able to finish the race. Whatever the factor that cause a f1 driver to not be able to finish the race, this dw assignment that Im trying to complete seeks out the independent variables that are capable of affecting the chances of a driver not being able to finish the race.

### Built With
<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/98efb040-b4de-465a-bc0d-c8da2c95c4f7" width="200"><br>
<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/69448f1e-9924-4c68-9ddd-4bd6d88e7b19" width="200"><br>
<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/faef1b95-92a0-42f8-a6b0-2131afd320bb" width="200"><br>
<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/8619bf77-7389-499b-8c74-4dff06861fc1" width="200"><br>
<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/a2ae5eda-c052-4a8e-b9da-a81f93b77445" width="200"><br>

# Loading and Explore data
To get started on this project, we first had to load the data from the relevant csv files as well as explore the features available in each of these csv files to ensure that the data

In order to explore the data, I decided to plot a correlation matrix for every dataframe to see if there are any correlation between different variables in each dataframe. 
<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/9d03b544-1673-4a6d-8997-9ef92f8ddda4"><br>
<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/e0e7d033-9819-4cb1-95b8-f933bed2d634"><br>
The above correlation matrix is for the pit stops dataframe and we can see that stops variable is related to laps as seen from the correlation matrix as these two variables have a correlation of 0.59 which shows a strong relationship between the two variables
<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/2dcac08c-7649-4b34-bd4c-0d413bb67875"><br>
<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/d98ac4a6-3e0f-464d-8369-bea89db1de6b"><br>
<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/7687cc87-395f-48d5-a98e-9691867a6511"><br>
Before merging the tables, miswritten years were discovered and a for loop was used to replace those miswritten years. 

# Data Wrangling on Multiple Tables
### Extract and Create features from different tables
<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/a3fe0d10-6cbf-478c-98ac-356801d518ce.png"><br>
Extracted year, month and quarter values.
<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/b91f2b1c-1a04-4652-b7da-d56402211d74.png"><br>
Created new feature, driver_age.
<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/1e45ead6-cd71-48d8-8983-a09dd7af035a.png"><br>
Create a feature replacement map to map whether the drivers have finished their race with binary values of 0 and 1.

### Concatenate, Merge or Join the tables
<br><img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/9f7dd451-1f0b-4e93-aaab-3a7351261ad5.png"><br>
Chose the dataframes to merge together that would help in the prediction of whether a driver would finish the race.

<br><img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/feded21e-baef-429f-a8e3-10b2e5184330.png"><br>
Renaming and dropping variables that have suffixes behind them for clarity.

# Data Cleansing and Transformation
### Missing Values and Outliers
<br><img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/5ecf0ae6-ce8c-4572-95a6-8b535005ed7d.png"><br>
Outliers are sifted out using box plots and logic to ensure that these outliers are not errors during the recording of data.

<br><img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/2f6904b1-3ca2-436c-a662-6d45bb34367b.png"><br>
```isnull().sum()``` function is used to find missing values in the data such that missing value imputation can be carried out.

<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/154aced0-ab6a-4838-8f9e-819531573c5b.png"><br>
I decided that for the missing values that are present in the dataset, the values would be replaced through an arbitrary number.

### Encoding Categorical Data
<br><img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/04332bf3-fad9-4828-9227-6a83a51420ac.png"><br>
There are a few categorical variables in the dataset that requires encoding into numerical data. The chosen method for encoding is One Hot Encoding of top categorical variables so as to not increase the dimensionality of the dataset.

### Transforming Numerical Data
It is important to ensure that the data in the datasets are normalized before feeding it into the model as a skewed distribution might affect the accuracy of a model's distributions.
<br><img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/4b8e0f49-1ef8-4982-af02-2ff422e618ec.png"><br>
In order to normalize the data, Power Transformation is done and chosen due to its effectiveness.

### Variable Discretization
<br><img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/04d56227-4a4f-46c2-ace2-ea729e8454cd.png"><br>
Equal Frequency Discretization is done to the dataset to spread the skewed data observations over different bins more equally.

### Feature Scaling
Feature scaling is required to transform the data into a standardized range to reduce the impact of extreme values, making the models more robust.
<br><img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/04627006-1183-4ef6-9781-6a434613d863.png"><br>

# Machine Learning Models
| Model Type | Train Accuracy | Test Accuracy |
| :---: | :---: | :---: |
|NB (Baseline Model)| 0.67 | 0.67 |
| Logistic Regression Model | 0.80 | 0.80 |








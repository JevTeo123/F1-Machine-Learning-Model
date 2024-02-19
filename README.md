<details>
  <summary>Table Of Contents</summary>
  
  1. [About The Project](#about-the-project)
      - [Built With](#built-with)
  2. [Loading and Explore Data](#loading-and-explore-data)
  3. [Data Wrangling on multiple tables]
  4. [Data Cleansing and Transformation](#data-wrangling-on-multiple-tables)
  5. [Machine Learning Models](#machine-learning-models)
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

In order to explore the data, I decided to plot a correlation matrix for every dataframe to see if there are any correlation between different variables in each dataframe. We can see from the above screenshot that the screenshot is for the results dataframe. From the correlation matrix created for the results dataframe, we can see that status is related to position order with a correlation of 0.43 representing a moderate linear relationship. This makes sense to me as status is the damage or penalty taken by the car which will in turn affect the position order of the car.
<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/9d03b544-1673-4a6d-8997-9ef92f8ddda4"><br>
<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/e0e7d033-9819-4cb1-95b8-f933bed2d634"><br>
The above correlation matrix is for the pit stops dataframe and we can see that stops variable is related to laps as seen from the correlation matrix as these two variables have a correlation of 0.59 which shows a strong relationship between the two variables. This makes sense to me as with more laps taken by a car, the tyres of the car will tend to get warn down faster and hence more pitstops would be needed. I also plotted a regression plot to see the what is the trend of pitstops against laps.
<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/2dcac08c-7649-4b34-bd4c-0d413bb67875"><br>
<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/d98ac4a6-3e0f-464d-8369-bea89db1de6b"><br>
<img src="https://github.com/JevTeo123/F1-Machine-Learning-Model/assets/123255675/7687cc87-395f-48d5-a98e-9691867a6511"><br>
Before merging the tables, I actually analyzed each dataframe to see if there are any data that does not seem normal. After checking through, I realised that one of the datasets called races dataset actually had miswritten years. As you can see from the screenshot, in the date column in row 2, the year is written as 12009 instead of 2009 and after checking through the dataframe, there are a few rows that has the same problem. Therefore, I created a for loop to loop through the dataframe to check and replace year values that are miswritten so that it would not cause problems for me afterwards.

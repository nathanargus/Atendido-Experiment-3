# ECE2112 Programming Problems

This repository contains Python scripts for solving various programming problems in ECE2112. Below is an overview of each script included.

### 1. Problem 1

##### This problem involves working with a CSV file that contains data about cars. The tasks include loading this data into a pandas DataFrame and performing basic data inspection. Specifically:

1. **Loading the Data:**
    - The CSV file, which should be saved to the default user folder, needs to be read into a DataFrame named `cars` using pandas.
    - This requires utilizing the `pd.read_csv()` function to import the data.
2. **Displaying Key Data:**
    - Both the first and last five rows of the DataFrame should be displayed to understand its structure and content.
    - The `head()` method will show the initial rows, while the `tail()` method will reveal the final rows of the DataFrame.
   
##### The objective is to practice data loading and initial exploration techniques using pandas, which are fundamental for understanding and preparing data for further analysis. The code should be clear and well-commented to reflect these tasks effectively.

**Function:**

```python

import pandas as pd

# Load the CSV file containing the model of cars and their specifications
cars = pd.read_csv('cars.csv')
cars

# Display both the head (first 5 rows) and tail (last 5 rows) of the DataFrame
# 'cars.head()' retrieves the first 5 rows by default
# 'cars.tail()' retrieves the last 5 rows by default
# 'pd.concat()' combines these two DataFrames into one
pd.concat([cars.head(), cars.tail()])

```

**Output:**

![image](https://github.com/user-attachments/assets/c4686d11-1e4f-4cd0-8ab7-16bb7f14a03c)



### 2. Problem 2

##### This problem involves analyzing a dataset containing information about cars. The task requires loading the dataset into a pandas DataFrame and performing basic operations to extract specific details. 

1. First, the CSV file should be read into a DataFrame named `cars` using the `pd.read_csv()` function.
2. The next step is to display the first five rows of the dataset while selecting only the odd-numbered columns.
3. Finally, an additional task involves displaying the value of the "Model" column for the first row.

##### These operations help in understanding basic indexing, column selection, and data retrieval in pandas.

**Function:**

```python

import pandas as pd

# Load the CSV file containing the model of cars and their specifications
cars = pd.read_csv('cars.csv')

# a. Display the first five rows with odd-numbered columns (columns 1, 3, 5, 7…)
print("First 5 rows with odd-numbered columns:")
print(cars.iloc[:5, 1::2])

# b. Display the row that contains the 'Model' of 'Mazda RX4'
print("\nRow with the 'Model' Mazda RX4:")
mazda_rx4_row = cars[cars['Model'] == 'Mazda RX4']
print(mazda_rx4_row,)

# c. How many cylinders does the car model 'Camaro Z28' have?
print("\nCylinders in 'Camaro Z28':")
camaro_cylinders = cars.loc[cars['Model'] == 'Camaro Z28', 'cyl']
print(camaro_cylinders.iloc[0], "cylinders\n")

# d. How many cylinders and what gear type the car models 'Mazda RX4 Wag', 'Ford Pantera L' and 'Honda Civic' have.
car_models = ['Mazda RX4 Wag', 'Ford Pantera L', 'Honda Civic']
print(f"Cylinders and gear type for {car_models}:")
selected_cars = cars[cars['Model'].isin(car_models)][['Model', 'cyl', 'gear']]
print(selected_cars)

```

**Output:**

![image](https://github.com/user-attachments/assets/9854be35-11f3-4c41-9a86-5f0a9e188122)

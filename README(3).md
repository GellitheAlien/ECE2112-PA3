## ECE2112_PA3

Made by: Geri Allison Geneta | 2ECE-B

This repository contains our Programming Assignment 3 for ECE2112. This project covers three python problems referenced to Module 3 - Pandas.

```python
import pandas as pd
```

## A. POSITIONAL AND LABEL-BASED SLICING

The following problem uses the cars dataset and demonstrates how to select specific rows and columns using positional-based and label-based indexing in Pandas.

The following functions and methods were used in this problem:

* pd.read_csv() - a Pandas function used to read a CSV file and load its contents into a DataFrame. Here, it is used to import the cars.csv dataset into a DataFrame named cars.

* .iloc[] - a Pandas indexing method used to select rows and columns based on their integer positions. In this problem, cars.iloc[6:11] selects the rows starting from index 6 up to, but not including, index 11.

* .loc[] - a Pandas indexing method used to select data based on row and column labels. In this problem, cars_6_to_10.loc[:, ['Model', 'mpg', 'cyl', 'hp', 'gear']] selects all rows from the previously sliced DataFrame while keeping only the specified columns.

These methods were combined to first select a specific range of rows using .iloc[], and then select specific columns using .loc[]. The resulting data contains the cars from index 6 to index 10 and only the Model, mpg, cyl, hp, and gear information.

```python
cars = pd.read_csv('cars.csv')
cars
```

```python
cars_6_to_10 = cars.iloc[6:11]
cars_6_to_10
```

```python
cars_6_to_10.loc[:, ['Model', 'mpg', 'cyl', 'hp', 'gear']]
```

## B. MODEL LOOKUP

The following problem uses the cars dataset to look up specific car models and display their corresponding information.

The following functions and methods were used in this problem:

* Boolean Indexing - a method used to filter rows in a DataFrame by creating a condition that evaluates to either True or False. In this problem, cars['Model'] == 'Toyota Corolla' checks which row has the Model value equal to "Toyota Corolla".

* .loc[] - a Pandas indexing method used to select specific rows and columns based on labels. Here, it is used to find the row where the Model is "Pontiac Firebird" and display only the Model, mpg, hp, and wt columns.

These operations were combined to search for a specific car model and retrieve only the information needed from the dataset. The Toyota Corolla lookup returns its complete row, while the Pontiac Firebird lookup limits the output to the Model, mpg, hp, and wt columns.

```python
cars[cars['Model'] == 'Toyota Corolla']
```

```python
cars.loc[(cars['Model']) == 'Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]
```

## C. MULTI-MODEL SUBSETTING


The following problem creates a smaller DataFrame from the cars dataset by selecting specific columns and then filtering the dataset to include only selected car models.

The following functions and methods were used in this problem:

* pd.DataFrame() - a Pandas function used to create a DataFrame. In this problem, it is used to create a new DataFrame containing only the Model, mpg, cyl, hp, and gear columns from the original cars DataFrame.

* .loc[] - a Pandas indexing method used to select specific rows and columns based on labels. Here, it is used to filter the car models while also selecting the required columns.

* Boolean OR operator | - an operator used to combine multiple filtering conditions. It allows the DataFrame to include a row when at least one of the conditions is True.

* .shape - a DataFrame attribute used to determine the number of rows and columns in a DataFrame. It returns the result in the form (rows, columns).

These operations were combined to create a subset containing only the Datsun 710, Lotus Europa, and Ferrari Dino models, together with their Model, mpg, cyl, hp, and gear information. The resulting DataFrame contains 3 rows and 5 columns, which is confirmed by using .shape.

```python
selected_cars = pd.DataFrame(cars, columns = ['Model', 'mpg','cyl', 'hp', 'gear'])
selected_cars
```

```python
selected_cars = pd.DataFrame(cars.loc[(cars['Model'] == 'Datsun 710') | (cars['Model'] == 'Lotus Europa') | (cars['Model'] == 'Ferrari Dino'), ['Model', 'mpg', 'cyl', 'hp', 'gear']])
selected_cars

```

```python
selected_cars.shape
```

The End.

## Thank you for reading!

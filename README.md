# ECE2112_PA3
### Made by Antonio Gabriel L. Urbano | 2ECE-A
### EXPERIMENT 3:PYTHON DATA ANALYSIS (PANDAS)
The content of this repository contains the Programming Assignment 3 for our course "Advance Computer Programming and Algorithms" this S.Y. 2026-2027. This project covers three problems pertaining to Module 3 - Pandas. 

The objectives of this experiment are to be able to load cars.csv dataset into a Pandas DataFrame, select rows and columns using positional and label-based indexing, filter records using conditions on a DataFrame column, and to extract a well-defined subset of data without changing the source data. 

### 1. Positional and Label-Based Slicing 

#### Requirement:
Display dataset properties like (shape, columns), and extract rows 6 through 10 positionally using .iloc, and specific columns (Model, mpg, cyl, hp, gear).

```python
print("Shape of cars DataFrame:", cars.shape)
print("List of Column Names:", list(cars.columns))

cars_6_to_10 = cars.iloc[5:10]

cars_6_to_10.loc[:, ['Model', 'mpg', 'cyl', 'hp', 'gear']]
```

### 2. Model Lookup
### Requirement: 
Use Pandas .loc with Boolean indexing to look up vehicle specifications without hardcoding integer row positions. Extract all columns for the Toyota Corolla, and extract only the (Model, mpg, hp, wt) columns for the Pontiac Firebird.

```pyhton
toyota = cars.loc[cars['Model'] == 'Toyota Corolla']
display(toyota)

pontiac = cars.loc[cars['Model'] == 'Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]
display(pontiac)
```

### 3. Multi-Model Subsetting
#### Requirement:
Using .isin() or Boolean filtering, extract the rows where Model is ('Datsun 710', 'Lotus Europa', or 'Ferrari Dino'). Subset the result to (Model, mpg, cyl, hp, gear) and programmatically check that data frame shape is equal to (3, 5).

```pyhton
target_models = ['Datsun 710', 'Lotus Europa', 'Ferrari Dino']
target_columns = ['Model', 'mpg', 'cyl', 'hp', 'gear']

selected_cars = cars.loc[cars['Model'].isin(target_models), target_columns ]

display(selected_cars)
print("Shape of selected_cars:", selected_cars.shape)
```

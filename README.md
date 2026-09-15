# ECE2112_PA3
### Made by Antonio Gabriel L. Urbano | 2ECE-A
### EXPERIMENT 3:PYTHON DATA ANALYSIS (PANDAS)
The content of this repository contains the Programming Assignment 3 for our course "Advance Computer Programming and Algorithms" this S.Y. 2026-2027. This project covers three problems pertaining to Module 3 - Pandas. 

The objectives of this experiment are to be able to load cars.csv dataset into a Pandas DataFrame, select rows and columns using positional and label-based indexing, filter records using conditions on a DataFrame column, and to extract a well-defined subset of data without changing the source data. 

### Methods Used
- Positional Row Slicing (cars.iloc[5:10]): Accepts an integer index range (5:10) and outputs a DataFrame. It retrieves records by zero-based position from index 5 up to 9, corresponding to the 6th through 10th rows in the dataset.

- Single-Condition Label Filtering (cars.loc[cars['Model'] == ...]): Accepts a conditional expression and optional target column list to output a DataFrame. It dynamically filters entries matching a specific model name while allowing concurrent column selection.

- Vectorized Multi-Value Selection (cars.loc[cars['Model'].isin(...), target_columns]): Accepts a list of model names alongside a list of target columns to output a DataFrame. It performs multi-item matching and column subsetting simultaneously within a single .loc call.

### 1. Positional and Label-Based Slicing 

#### Requirement:
Display dataset properties like (shape, columns), and extract rows 6 through 10 positionally using .iloc, and specific columns (Model, mpg, cyl, hp, gear).

```python
print("Shape of cars DataFrame:", cars.shape)
print("List of Column Names:", list(cars.columns))

cars_6_to_10 = cars.iloc[5:10]

cars_6_to_10.loc[:, ['Model', 'mpg', 'cyl', 'hp', 'gear']]
```
*Output:*

```text
Shape of DataFrame: (32, 12)
Column names: ['Model', 'mpg', 'cyl', 'disp', 'hp', 'drat', 'wt', 'qsec', 'vs', 'am', 'gear', 'carb']
```

| Index | Model | mpg | cyl | hp | gear |
| :--- | :--- | :--- | :--- | :--- | :--- |
| *5* | Valiant | 18.1 | 6 | 105 | 3 |
| *6* | Duster 360 | 14.3 | 8 | 245 | 3 |
| *7* | Merc 240D | 24.4 | 4 | 62 | 4 |
| *8* | Merc 230 | 22.8 | 4 | 95 | 4 |
| *9* | Merc 280 | 19.2 | 6 | 123 | 4 |

---

### 2. Model Lookup
### Requirement: 
Use Pandas .loc with Boolean indexing to look up vehicle specifications without hardcoding integer row positions. Extract all columns for the Toyota Corolla, and extract only the (Model, mpg, hp, wt) columns for the Pontiac Firebird.

```pyhton
toyota = cars.loc[cars['Model'] == 'Toyota Corolla']
display(toyota)

pontiac = cars.loc[cars['Model'] == 'Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]
display(pontiac)
```
*Output:*

*Toyota Corolla:*

| Index | Model | mpg | cyl | disp | hp | drat | wt | qsec | vs | am | gear | carb |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| *19* | Toyota Corolla | 33.9 | 4 | 71.1 | 65 | 4.22 | 1.835 | 19.91 | 1 | 1 | 4 | 1 |

*Pontiac Firebird:*

| Index | Model | mpg | hp | wt |
| :--- | :--- | :--- | :--- | :--- |
| *24* | Pontiac Firebird | 19.2 | 175 | 3.845 |

---

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
*Output:*

| Index | Model | mpg | cyl | hp | gear |
| :--- | :--- | :--- | :--- | :--- | :--- |
| *2* | Datsun 710 | 22.8 | 4 | 93 | 4 |
| *27* | Lotus Europa | 30.4 | 4 | 113 | 5 |
| *29* | Ferrari Dino | 19.7 | 6 | 175 | 5 |

```text
DataFrame Shape: (3, 5)
```
---


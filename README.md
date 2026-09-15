# ECE2112_PA3
### Made by Antonio Gabriel L. Urbano | 2ECE-A
### EXPERIMENT 3:PYTHON DATA ANALYSIS (PANDAS)
The content of this repository contains the Programming Assignment 3 for our course "Advance Computer Programming and Algorithms" this S.Y. 2026-2027. This project covers three problems pertaining to Module 3 - Pandas. 

The objectives of this experiment are to be able to load a CSV dataset into a Pandas DataFrame, select rows and columns using positional and label-based indexing, filter records using conditions on a DataFrame column, and to extract a well-defined subset of data without changing the source data. 

### 1. Positional and Label-Based Slicing 
After loading cars, complete the following operations.
a. Display the shape and complete list of column names of cars.

b. Use positional slicing to create cars_6_to_10 containing rows 6 through 10 of the dataset, where the first data row is row 1. 

c. From cars_6_to_10, display only the columns Model, mpg, cyl, hp, and gear in that order. 
#### Requirement:
The row selection in part (b) must use iloc; the column selection in part (c) must use column labels. 

### 2. Model Lookup
Use Boolean indexing on the Model column to answer both requests.

a. Display the complete row for Toyota Corolla.

b. For Pontiac Firebird, display only Model, mpg, hp, and wt.
### Requirement: 
Store the two results in toyota and pontiac, respectively. Do not use a hard-coded row number to
locate either model.

### 3. Multi-Model Subsetting
Create a DataFrame named selected cars containing only the records for three models: Datsun 710,
Lotus Europa, and Ferrari Dino.

For these records, retain only Model, mpg, cyl, hp, and gear. Select the rows by their model values
rather than by row numbers. Display selected cars and its shape.

#### Required check:
The final DataFrame must contain exactly three rows and five columns

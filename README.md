# VILLAR-PA-3
### Made by : Vance Q. Villar | 2ECE-C

This repository contains Experiment 3: PYTHON DATA ANALYSIS (PANDAS)

# **A. Positional and Label-Based Slicing Problem**

Load the `cars.csv` file into a DataFrame named `cars`. Using positional slicing (`iloc`), create `cars_6_to_10` containing rows 6 through 10 of the dataset, where the first data row is row 1. From `cars_6_to_10`, display only the columns `Model`, `mpg`, `cyl`, `hp`, and `gear`, in that order.

The following Pandas functions and methods were used in this problem:

• `pd.read_csv('cars.csv')` - loads the CSV dataset into a Pandas DataFrame.

• `cars.iloc[5:10]` - uses positional slicing to extract rows at index 5 through 9 (corresponding to rows 6 to 10 of the dataset).

• `cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]` - utilizes label-based column indexing to select and display specific columns from the DataFrame.

```python
import pandas as pd


cars = pd.read_csv('cars.csv')
cars

cars_6_to_10 = cars.iloc[5:10]
cars_6_to_10

cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]
```

# **B. Model Lookup Problem**

Use Boolean indexing on the `Model` column to answer both requests. Display the complete row for `Toyota Corolla` and store it in `toyota`. For `Pontiac Firebird`, display only `Model`, `mpg`, `hp`, and `wt` and store it in `pontiac`. Do not use a hard-coded row number to locate either model.

The following functions and methods were used in this problem:

• `pd.read_csv('cars.csv')` - loads the CSV dataset into a Pandas DataFrame.

• `cars.loc[cars['Model']=='Toyota Corolla']` - uses Boolean indexing on the `Model` column to filter and locate the full row for Toyota Corolla.

• `cars.loc[cars['Model']=='Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]` - combines Boolean row filtering with label-based column selection in a single operation.

```python
import pandas as pd


cars = pd.read_csv('cars.csv')
cars

toyota = cars.loc[cars['Model']=='Toyota Corolla']
toyota

pontiac = cars.loc[cars['Model']=='Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]
pontiac
```

# **C. Multi-Model Subsetting Problem**

Create a DataFrame named `selected_cars` containing only the records for three models: `Datsun 710`, `Lotus Europa`, and `Ferrari Dino`. For these records, retain only `Model`, `mpg`, `cyl`, `hp`, and `gear`. Select the rows by their model values rather than by row numbers. Display `selected_cars` and its shape.

The following functions and methods were used in this problem:

• `(cars['Model']=='Datsun 710') | ...` - uses bitwise OR (`|`) logical operators to construct multi-condition Boolean filtering across row values.

• `cars.loc[..., ['Model', 'mpg', 'cyl', 'hp', 'gear']]` - filters specified rows by model name while simultaneously restricting output columns.

• `.shape` - an attribute that retrieves the tuple representing the dimensional shape `(rows, columns)` of the resulting DataFrame.

Combining these Pandas operations yields the final code for this problem;

```python
import pandas as pd


cars = pd.read_csv('cars.csv')
cars

selected_cars = cars.loc[(cars['Model']=='Datsun 710') | (cars['Model']=='Lotus Europa') | (cars['Model']=='Ferrari Dino'), ['Model', 'mpg', 'cyl', 'hp', 'gear']]
selected_cars

selected_cars.shape
```

September 10, 2026- update README output uploaded

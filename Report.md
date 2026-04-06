# Data Wrangling Report

## First exercise
[Click here for the first exercise](Ex1.ipynb)

### In the first exercise we analyzed data about specific users. We used basic functions from pandas, such as:
1. **read_csv()** - import data from an external address,
2. **head()** - select first rows,
3. **tail()** - select rows at the end,
4. **len()** - describe the number of columns or rows, 
5. **list()** - print the names of columns,
6. **describe()** - summarize data,
7. **mean()** - calculate the mean of a column,
8. **value_counts()** - count occurences within a column,
9. **nunique()** - get the number of unique observations,
10. **set_index()** - set an index for the DataFrame.

### We also used following DataFrame attributtes:
1. **dtypes** - determine the data type of each column,
2. **index** - check how data is indexed.

## Second exercise
[Click here for the second exercise](Ex2.ipynb)

### In the second exercise we analyzed data about Euro 2012. We used functions from previous exercise, as well as several new functions to filter and sort data:
1. **sort_values** - sort values by a column,
2. **startswith()** - select data whose values start with a specific letter,
3. **iloc[]** - select columns from an interval or with specific exclusions,
4. **isin()** - select rows whose columns values match a given list :
    `euro12.loc[euro12.Team.isin(['England', 'Italy', 'Russia']), ['Team', 'Shooting Accuracy']]`.

### Filtering allowed us to select teams that scored more than 6 goals:
`euro12[euro12['Goals'] > 6]`

## Third exercise
[Click here for the third exercise](Ex3.ipynb)

### In the third exercise we analyzed data about drinks. The main function used was groupby(). Function happened to be extremely useful for extracting specific data that interested us.

- In the last step, we not only used **groupby()** to group continent by spirit servings, but we also used **agg()** to create completely new columns, desciribing mean, min and max.
    `drinks.groupby('continent')['spirit_servings'].agg(['mean','min', 'max'])`

- We encountered a small difficulty - while loading the data, we discovered that the continent code for **North America (NA)** was being read as a **NULL** value. To solve this problem, we used ***keep_default_na=False*** in **pd.read_csv()**.

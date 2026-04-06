# Data Wrangling Report

## First exercise
[Click here for first exercise](Ex1.ipynb)

### In the first exercise we analyzed data about specific users. We used basic functions from pandas, such as:
1. **read_csv()** to import data from external address,
2. **head()** to select first rows,
3. **tail()** to select rows at the end,
4. **len()** to describe number of columns or rows, 
5. **list()** to print name of columns,
6. **describe()** to summarize data,
7. **mean()** to calculate the mean of data,
8. **value_counts()** to count occurences in a column,
9. **nunique()** to get the number of unique observations,
10. **set_index()** to set an index for the data.

## We also used some attributes of our data frame:
1. **dtypes** to determine the data type in each column,
2. **index** to check how data is indexed.

## Second exercise
[Click here for second exercise](Ex2.ipynb)

### In the second exercise we analyzed data about Euro 2012. We used functions from previous exercise, as well as some new functions to filter and sort data:
1. **sort_values** to sort values by a column,
2. **startsith()** to select data that starts with a specific letter,
3. **iloc[]** to select columns from an interval or with specific exceptions,
4. **isin()** to select data that has a match in columns :
    `euro12.loc[euro12.Team.isin(['England', 'Italy', 'Russia']), ['Team', 'Shooting Accuracy']]`.

### Filtration helped us with selecting teams that scored more than 6 goals:
`euro12[euro12['Goals'] > 6]`

## Third exercise
[Click here for third exercise](Ex3.ipynb)

### In the third exercise we analyzed data about drinks. Main function which we used was groupby(). Function happened to be extremely useful for extracting specific data that interested us.

- In the last step, we not only used **groupby()** to group continent by spirit servings, but we also used **agg()** to create completely new columns, desciribing mean, min and max.
    `drinks.groupby('continent')['spirit_servings'].agg(['mean','min', 'max'])`

- We encountered a small difficulty - while loading the data, we discovered that the continent code for **North America (NA)** was being read as a **NULL** value. To solve this problem, we used ***keep_default_na=False*** in **pd.read_csv()**.

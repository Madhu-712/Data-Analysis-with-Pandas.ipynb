# Data-Analysis-with-Pandas.ipynb

Data Analysis with Pandas
Pandas is an open source library for data analysis in Python. In this project, I explore pandas and important data analysis tools of pandas.

Table of contents
The contents of this project are divided into various categories which are listed below:-

Introduction to Pandas

Key features of Pandas

Advantages of Pandas

Importing Pandas

Data structures in Pandas

Pandas series

Pandas dataframe

Pandas panel

Data import with pandas

Dataset description

Exploratory data analysis

Handle missing values with pandas

Indexing and slicing in pandas

Indexing and reindexing in pandas

MultiIndex or Advanced indexing

Sorting in pandas

Categorical data in pandas

Basic functionality in pandas

Descriptive statistics in pandas

Statistical functions in pandas

Window functions in pandas

Aggregations in pandas

Iteration in pandas

Function application in pandas

Pandas GroupBy operations

Pandas merging and joining

Pandas concatenation operation

Reshaping by melt and pivot

Reshaping by stacking and unstacking

Options and customization with pandas

1. Introduction to Pandas
Today, Python is considered as the most popular programming language for doing data science work. The reason behind this popularity is that Python provides great packages for doing data analysis and visualization work.

Pandas is one of those packages that makes analysing data much easier. Pandas is an open source library for data analysis in Python. It was developed by Wes McKinney in 2008. Over the years, it has become the standard library for data analysis using Python.

According to the Wikipedia page on Pandas,

"Pandas offers data structures and operations for manipulating numerical tables and time series. It is free software released under the three-clause BSD license. The name is derived from the term 'panel data', an econometrics term for data sets that include observations over multiple time periods for the same individuals."

In this project, I explore Pandas and various data analysis tools provided by Pandas.

2. Key features of Pandas
Some key features of Pandas are as follows:-

It provides tools for reading and writing data from a wide variety of sources such as CSV files, excel files, databases such as SQL, JSON files.
It provides different data structures like series, dataframe and panel for data manipulation and indexing.
It can handle wide variety of data sets in different formats – time series, heterogeneous data, tabular and matrix data.
It can perform variety of operations on datasets. It includes subsetting, slicing, filtering, merging, joining, groupby,
reordering and reshaping operations.
It can deal with missing data by either deleting them or filling them with zeros or a suitable test statistic.
It can be used for parsing and conversion of data.
It provides data filtration techniques.
It provides time series functionality – date range generation, frequency conversion, moving window statistics, data shifting and lagging.
It integrates well with other Python libraries such as Scikit-learn, statsmodels and SciPy.
It delivers fast performance. Also, it can be speeded up even more by making use of Cython (C extensions to Python).
3. Advantages of Pandas
Pandas is a core component of the Python data analysis toolkit. Pandas provides data structure and operations facilities, which is particularly useful for data analysis. There are various advantages of using Pandas for data analysis.

These advantages are as follows:-

Data representation
It represents data in a form that is very much suited for data analysis through its Dataframe and Series data structures.

Data subsetting and filtering
It provides for easy subsetting and filtering of data. It provides procedures that are suited for data analysis.

Concise and clear code
It provides functionality to write clear and concise code. It allows us to focus on the task at hand, rather than have to write tedious code.

4. Importing Pandas
In order to use Pandas in our work, we need to import the Pandas library first. We can import the Pandas library with the following command:-

import pandas

Usually, we import the Pandas library by appending the alias as pd. It makes things easier because now instead of writing pandas.command we need to write pd.command. So, we will import pandas with the following command:-

import pandas as pd

Also, I will import Numpy as well, because it is very useful library for scientific computing with Python. I will import Numpy with the following command:-

import numpy as np

# import pandas and numpy

import pandas as pd

import numpy as np
5. Data structures in Pandas
Pandas provide easy to use data structures.

There are three main data structures in Pandas. They are:-

Series

Dataframe

Panel

These data structures are built on top of Numpy array, which means they are fast. I have described these data structures in the following sections.

6. Pandas Series
A Pandas Series is a one-dimensional array like structure with homogeneous data.

The data can be of any type (integer, string, float, etc.). The axis labels are collectively called index.

For example, the following series is a collection of integers 10, 20, 30, 40, 50, 60, 70, 80, 90, 100.

Key Points of Pandas Series
Homogeneous data

Size of series immutable

Values of data mutable

Series Constructor
A Pandas Series can be created using the following constructor −

pandas. Series (data, index, dtype, copy)

The parameters of the constructor are as follows –

data - data takes various forms like ndarray, list, dictionary, constants, etc.
index- index values must be unique, hashable and have the same length as data. The default index is RangeIndex (0, 1, 2,
       …, n) if no index is passed.
dtype - dtype is for data type. If none, data type will be inferred.
copy - Copy input data. Default value is False.
7. Pandas DataFrame
A Dataframe is a two-dimensional data structure. So, data is aligned in a tabular fashion in rows and columns. Its column types can be heterogeneous: - that is, of varying types. It is similar to structured arrays in NumPy with mutability added.

Properties of Dataframe are as follows:-
The dataframe is conceptually analogous to a table or spreadsheet of data.
Its columns are of different types – float64, int, bool, and so on.
A Dataframe column is a Series structure.
Its size is mutable – columns can be inserted and deleted.
It has labelled axes (rows and columns).
It can be thought of as a dictionary of Series structures where both the rows and columns are indexed, denoted as index in the case of rows and columns in the case of columns.
It can perform arithmetic operations on rows and columns.
Dataframe Constructor
Dataframe is the most commonly used data structure in pandas.

A pandas Dataframe can be created using the following constructor-

pandas.DataFrame(data, index, columns, dtype, copy)

The constructor accepts many different types of arguments:

Dictionary of 1D ndarrays, lists, dictionaries, or Series structures 

2D NumPy array

Structured or record ndarray

Series structures

Another DataFrame structure 



The parameters description of the constructor is as follows –

-data - data takes various forms like ndarray, series, map, lists, dict, constants and also another DataFrame.

-index- Index or array-like

        Index to use for resulting frame. Will default to RangeIndex if no indexing information part of 
        input data and no index provided


-columns- Index or array-like

          Column labels to use for resulting frame. Will default to RangeIndex (0, 1, 2, …, n) if no column labels are  
          provided.


-dtype - data type of each column

-copy - boolean, default False

        Copy data from inputs. Only affects DataFrame / 2d ndarray input




Dataframe Creation
A pandas Dataframe can be created using various inputs like −

• Lists

• dict

• Series

• Numpy ndarrays

• Another Dataframe

8. Pandas Panel
A panel is a 3D container of data.

The term Panel data is derived from econometrics and is partially responsible for the name pandas − pan(el)-da(ta)-s.

The names for the 3 axes are intended to give some semantic meaning to describing operations involving panel data.

They are −

items − axis 0, each item corresponds to a DataFrame contained inside.

major_axis − axis 1, it is the index (rows) of each of the DataFrames.

minor_axis − axis 2, it is the columns of each of the DataFrames.

9. Data import with Pandas
Pandas input output API provides several functions that can be used to import and export various file formats.

Below is the list of file formats and the corresponding functions to import these file formats.

Flat files - read_csv(), to_csv()

Excel files - read_excel(), ExcelWriter(), to_excel()

JSON files - read_json(), to_json()

HTML tables - read_html(), to_html()

SAS files - read_sas()

SQL files - read_sql(), read_sql_query(), read_sql_table(), to_sql()

STATA files - read_stata(), to_stata()

pickle object - read_pickle(), to_pickle()

HDF5 files - read_hdf(), to_hdf()

In this project, I work with the BlackFriday dataset which is a comma-separated values (CSV) file type. In a CSV file type, the data is stored as a comma-separated values where each row is separated by a new line, and each column by a comma (,). Also, in some sections, I create my own dataset to discuss the respective functionality.

So, I use the read_csv() function to import the file as follows:-

data = 'C:/datasets/BlackFriday.csv'

df = pd.read_csv(data)
10. Dataset description
I have used BlackFriday dataset for this project. The dataset is the sample of the transactions made in a retail store.

The dataset contains 12 variables and 537577 instances.

I have downloaded this dataset from the following url:-

https://www.kaggle.com/mehdidag/black-friday

11. Exploratory Data Analysis
The next step is to conduct exploratory data analysis.

check the type of df
I have imported the dataset. The next step is to check its type. We can check its type with the following command:-

type(df)
pandas.core.frame.DataFrame
We can see that the df is the pandas dataframe.

check shape of dataframe
The next step is to check the shape of the dataframe. We can check the shape of the dataframe as follows:-

df.shape
(537577, 12)
There are 537577 rows and 12 columns in the dataset.

view the first five rows of the dataframe
We can view the first 5 rows of the dataframe with head() method as follows:-

df.head()
User_ID	Product_ID	Gender	Age	Occupation	City_Category	Stay_In_Current_City_Years	Marital_Status	Product_Category_1	Product_Category_2	Product_Category_3	Purchase
0	1000001	P00069042	F	0-17	10	A	2	0	3	NaN	NaN	8370
1	1000001	P00248942	F	0-17	10	A	2	0	1	6.0	14.0	15200
2	1000001	P00087842	F	0-17	10	A	2	0	12	NaN	NaN	1422
3	1000001	P00085442	F	0-17	10	A	2	0	12	14.0	NaN	1057
4	1000002	P00285442	M	55+	16	C	4+	0	8	NaN	NaN	7969
view concise summary of dataframe
We can view the concise summary of dataframe with info() method as follows:-

df.info()
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 537577 entries, 0 to 537576
Data columns (total 12 columns):
User_ID                       537577 non-null int64
Product_ID                    537577 non-null object
Gender                        537577 non-null object
Age                           537577 non-null object
Occupation                    537577 non-null int64
City_Category                 537577 non-null object
Stay_In_Current_City_Years    537577 non-null object
Marital_Status                537577 non-null int64
Product_Category_1            537577 non-null int64
Product_Category_2            370591 non-null float64
Product_Category_3            164278 non-null float64
Purchase                      537577 non-null int64
dtypes: float64(2), int64(5), object(5)
memory usage: 49.2+ MB
12. Handle missing values with pandas
We can check the total number of missing values in each column in the dataset with the following command:-

df.isnull().sum()
User_ID                            0
Product_ID                         0
Gender                             0
Age                                0
Occupation                         0
City_Category                      0
Stay_In_Current_City_Years         0
Marital_Status                     0
Product_Category_1                 0
Product_Category_2            166986
Product_Category_3            373299
Purchase                           0
dtype: int64
We can see that there are 166986 missing values in Product_Category_2 and 373299 columns in Product_Category_3 columns.

isna() and notna() functions to detect 'NA' values
Pandas provides isna() and notna() functions to detect 'NA' values.

These are also methods on Series and DataFrame objects.

Examples of isna() and notna() commands.

detect ‘NA’ values in the dataframe

df.isna().sum()

detect ‘NA’ values in a particular column in the dataframe

pd.isna(df[‘col_name’])

df[‘col_name’].notna()

df.isna().sum()
User_ID                            0
Product_ID                         0
Gender                             0
Age                                0
Occupation                         0
City_Category                      0
Stay_In_Current_City_Years         0
Marital_Status                     0
Product_Category_1                 0
Product_Category_2            166986
Product_Category_3            373299
Purchase                           0
dtype: int64
We can see that all the missing values are encoded as NA values. If the missing values are encoded in different ways we should encode them first.

Encode missing numerical values
Missing values are encoded in different ways. They can appear as NaN, NA, ?, zeros, xx, -1 or a blank space “ ”. We can use various pandas methods to deal with missing values.

But, pandas always recognize missing values as NaN. So, it is essential that we should first convert all the ?, zeros, xx, -1 or “ ” to NaN. If the missing values isn’t identified as NaN, then we have to first convert or replace such non NaN entry with a NaN.

Convert '?' to ‘NaN’
df[df == '?'] = np.nan

Handle missing numerical values
There are several methods to handle missing values. Each method has its own advantages and disadvantages. The choice of the method is subjective and depends on the nature of data and the missing values. In this section, I have listed the most commonly used methods to deal with missing values. They are as follows:-

Drop missing values with dropna() method

Fill missing values with zeros

Fill missing values with a test statistic

Fill missing values backward or forward

In this section, I have fill the missing values with forward or backward filling.

The pad or fill option fill values forward, while bfill or backfill option fill values backward.

The following code helps us to achieve this task:-

df = df.fillna(method = 'pad')
Again, we should check whether missing values are removed or not.

df.isnull().sum()
User_ID                       0
Product_ID                    0
Gender                        0
Age                           0
Occupation                    0
City_Category                 0
Stay_In_Current_City_Years    0
Marital_Status                0
Product_Category_1            0
Product_Category_2            1
Product_Category_3            1
Purchase                      0
dtype: int64
We can see that the Product_Category_2 and Product_Category_3 have 1 missing value. We can use the head() to check this.

df[['Product_Category_2', 'Product_Category_3']].head()
Product_Category_2	Product_Category_3
0	NaN	NaN
1	6.0	14.0
2	6.0	14.0
3	14.0	14.0
4	14.0	14.0
We can see that the first element of each column are NaN. So, in this case pad or fill option does not work. Here, we should use bfill or backfill options as follows:-

df = df.fillna(method = 'backfill')
Again, we should check whether missing values are filled or not.

df.isnull().sum()
User_ID                       0
Product_ID                    0
Gender                        0
Age                           0
Occupation                    0
City_Category                 0
Stay_In_Current_City_Years    0
Marital_Status                0
Product_Category_1            0
Product_Category_2            0
Product_Category_3            0
Purchase                      0
dtype: int64
Check with ASSERT statement
Finally, we should check for missing values programmatically. If we drop or fill missing values, we expect no missing values. We can write an assert statement to verify this. So, we can use an assert statement to programmatically check that no missing or unexpected '0' value is present. This gives confidence that our code is running properly.

Assert statement will return nothing if the value being tested is true and will throw an AssertionError if the value is false.

Asserts

• assert 1 == 1 (return Nothing if the value is True)

• assert 1 == 2 (return AssertionError if the value is False)

#assert that there are no missing values in the dataframe

assert pd.notnull(df).all().all()
The above command does not throw any AssertionError. So, it is confirmed that there are no missing values in the dataframe.

13. Indexing and slicing in pandas
In this section, I will discuss how to slice and dice the data and get the subset of pandas dataframe.

Pandas provides three types of Multi-axes indexing. Those three types are mentioned in the following table:-

.loc - Label based
.iloc - Integer based
.ix - Both Label and Integer based
Starting with pandas 0.20.0, the .ix indexer is deprecated, in favor of the more strict .iloc and .loc indexers. So, I will not discuss it here and limit the discussion to .loc and .iloc indexers.

Label based indexing using .loc indexer
Pandas provide .loc indexer to have purely label based indexing. When slicing, the start bound is also included. Integers are valid labels, but they refer to the label and not the position.

.loc indexer has multiple access methods like −

A single scalar label

A list of labels

A slice object

A Boolean array

Syntax-

.loc takes two single/list/range operator separated by ','.

The first one indicates the row and the second one indicates columns.

Below are the examples of selecting data using .loc indexer:-

# make a copy of dataframe
df1 = df.copy()
# select first row of dataframe

df1.loc[0]
User_ID                         1000001
Product_ID                    P00069042
Gender                                F
Age                                0-17
Occupation                           10
City_Category                         A
Stay_In_Current_City_Years            2
Marital_Status                        0
Product_Category_1                    3
Product_Category_2                    6
Product_Category_3                   14
Purchase                           8370
Name: 0, dtype: object
#select first five rows for a specific column

df1.loc[:,'Purchase'].head()
0     8370
1    15200
2     1422
3     1057
4     7969
Name: Purchase, dtype: int64
Similar examples of selecting data using .loc indexer are as follows:-

Select all rows for multiple columns, say list[]

df1.loc[:,['Age','Occupation']]

Select first five rows for multiple columns, say list[]

df1.loc[[0, 1, 2, 3, 4],['Age','Occupation']]

Select range of rows for all columns

df1.loc[0:4]

The above functionality can also be given by

df1.head()

Integer position based indexing using .iloc indexer
Pandas provides .iloc indexer for integer position based indexing.

.iloc is primarily integer position based (from 0 to length-1 of the axis), but may also be used with a boolean array. .iloc will raise IndexError if a requested indexer is out-of-bounds, except slice indexers which allow out-of-bounds indexing. Allowed inputs of .iloc indexer are:-

An integer e.g. 5.
A list or array of integers [4, 3, 0].
A slice object with ints 1:7.
A boolean array.
Rows selection using .iloc indexer
Below are the examples of row selection using .iloc indexer

select first row of dataframe
df1.iloc[0]

select second row of dataframe
df1.iloc[1]

select last row of dataframe
df1.iloc[-1]

select second last row of dataframe
df1.iloc[-2]

#select first row of dataframe

df1.iloc[0]
User_ID                         1000001
Product_ID                    P00069042
Gender                                F
Age                                0-17
Occupation                           10
City_Category                         A
Stay_In_Current_City_Years            2
Marital_Status                        0
Product_Category_1                    3
Product_Category_2                    6
Product_Category_3                   14
Purchase                           8370
Name: 0, dtype: object
#select last row of dataframe

df1.iloc[-1]
User_ID                         1004737
Product_ID                    P00118242
Gender                                M
Age                               36-45
Occupation                           16
City_Category                         C
Stay_In_Current_City_Years            1
Marital_Status                        0
Product_Category_1                    5
Product_Category_2                    8
Product_Category_3                   16
Purchase                           6875
Name: 537576, dtype: object
Columns selection using .iloc indexer
select first column of dataframe
df1.iloc[:,0]

select second column of dataframe
df1.iloc[:,1]

select last column of dataframe
df1.iloc[:,-1]

select second last column of dataframe
df1.iloc[:,-2]

Multiple rows and columns selection using .iloc indexer
select first five rows of dataframe
df1.iloc[0:5]

select first five columns of data frame with all rows
df1.loc[:, 0:5]

select 1st, 5th and 10th rows with 1st, 4th and 7th columns
df1.iloc[[0,4,9]], [0,3,6]]

select first 5 rows and 5th, 6th, 7th columns of data frame
df1.iloc[0:5, 5:8]

Indexing first occurrence of maximum or minimum values with idxmax() and idxmin()
Pandas provide two functions idxmax() and idxmin() that return index of first occurrence of maximum or minimum values over requested axis. NA/null values are excluded from the output.

# get index of first occurence of maximum Purchase value 

df1['Purchase'].idxmax()
87440
# get the row with the maximum Purchase value 

df1.loc[df1['Purchase'].idxmax()]
User_ID                         1001474
Product_ID                    P00052842
Gender                                M
Age                               26-35
Occupation                            4
City_Category                         A
Stay_In_Current_City_Years            2
Marital_Status                        1
Product_Category_1                   10
Product_Category_2                   15
Product_Category_3                    8
Purchase                          23961
Name: 87440, dtype: object
Indexing a single value with at() and iat()
Pandas provides at() and iat() functions to access a single value for a row and column pair by label or by integer position.

# get value at 1st row and Purchase column pair

df1.at[1, 'Purchase']
15200
# get value at 1st row and 11th column pair

df1.iat[1, 11]
15200
Boolean indexing in pandas
Boolean indexing is the use of boolean vectors to filter and select the data. The operators for boolean indexing are -

| for or,
& for and,
~ for not.
These must be grouped by using parentheses. Using a boolean vector to index a Series works exactly as in a NumPy ndarray.

Conditional selections with boolean arrays using df.loc[selection] is the most common method to use with Pandas DataFrames. With boolean indexing or logical selection, we can pass an array or Series of True/False values to the .loc indexer to select the rows where the Series has True values. Then, we will make selections based on the values of different columns in dataset.

We can use a boolean True/False series to select rows in a pandas dataframe where there are true values. Then, a second argument can be passed to .loc indexer to select other columns of the dataframe with the same label. The columns are referred to by name for the loc indexer and can be a single string, a list of columns, or a slice ":" operation.

# make a copy of dataframe df

df2 = df.copy()
df2.head()
User_ID	Product_ID	Gender	Age	Occupation	City_Category	Stay_In_Current_City_Years	Marital_Status	Product_Category_1	Product_Category_2	Product_Category_3	Purchase
0	1000001	P00069042	F	0-17	10	A	2	0	3	6.0	14.0	8370
1	1000001	P00248942	F	0-17	10	A	2	0	1	6.0	14.0	15200
2	1000001	P00087842	F	0-17	10	A	2	0	12	6.0	14.0	1422
3	1000001	P00085442	F	0-17	10	A	2	0	12	14.0	14.0	1057
4	1000002	P00285442	M	55+	16	C	4+	0	8	14.0	14.0	7969
# get the purchase amount with a given user_id and product_id

df2.loc[((df2['User_ID'] == 1000001) & (df2['Product_ID'] == 'P00069042')), 'Purchase']
0    8370
Name: Purchase, dtype: int64
Indexing with isin() method
The isin() method of Series, returns a boolean vector. It is true wherever the Series elements exist in the passed list. This allows you to select rows where one or more columns have values we want to access. The same method is available for Index objects. It is useful for the cases when we don't know which of the sought labels are in fact present.

DataFrame also has an isin() method. When calling isin, we pass a set of values as either an array or dict. If values is an array, isin returns a DataFrame of booleans that is the same shape as the original DataFrame, with True wherever the element is in the sequence of values.

values=[1000001,'P00069042','F',0-17,10,'A',2,0,3,6,14,8370]

df2_indexed=df2.isin(values)


df2_indexed.head(10)
User_ID	Product_ID	Gender	Age	Occupation	City_Category	Stay_In_Current_City_Years	Marital_Status	Product_Category_1	Product_Category_2	Product_Category_3	Purchase
0	True	True	True	False	True	True	False	True	True	True	True	True
1	True	False	True	False	True	True	False	True	False	True	True	False
2	True	False	True	False	True	True	False	True	False	True	True	False
3	True	False	True	False	True	True	False	True	False	True	True	False
4	False	False	False	False	False	False	False	True	False	True	True	False
5	False	False	False	False	False	True	False	True	False	True	True	False
6	False	False	False	False	False	False	False	False	False	False	False	False
7	False	False	False	False	False	False	False	False	False	False	False	False
8	False	False	False	False	False	False	False	False	False	False	False	False
9	False	False	False	False	False	True	False	False	False	False	False	False
We can combine DataFrame's isin with the any() and all() methods to quickly select subsets of the data that meet a given criteria. We can select a row where each column meets its own criterion as follows:-

row_mask = df2.isin(values).any(1)

df[row_mask]
User_ID	Product_ID	Gender	Age	Occupation	City_Category	Stay_In_Current_City_Years	Marital_Status	Product_Category_1	Product_Category_2	Product_Category_3	Purchase
0	1000001	P00069042	F	0-17	10	A	2	0	3	6.0	14.0	8370
1	1000001	P00248942	F	0-17	10	A	2	0	1	6.0	14.0	15200
2	1000001	P00087842	F	0-17	10	A	2	0	12	6.0	14.0	1422
3	1000001	P00085442	F	0-17	10	A	2	0	12	14.0	14.0	1057
4	1000002	P00285442	M	55+	16	C	4+	0	8	14.0	14.0	7969
5	1000003	P00193542	M	26-35	15	A	3	0	1	2.0	14.0	15227
9	1000005	P00274942	M	26-35	20	A	1	1	8	16.0	17.0	7871
10	1000005	P00251242	M	26-35	20	A	1	1	5	11.0	17.0	5254
11	1000005	P00014542	M	26-35	20	A	1	1	8	11.0	17.0	3957
12	1000005	P00031342	M	26-35	20	A	1	1	8	11.0	17.0	6073
13	1000005	P00145042	M	26-35	20	A	1	1	1	2.0	5.0	15665
14	1000006	P00231342	F	51-55	9	A	1	0	5	8.0	14.0	5378
15	1000006	P00190242	F	51-55	9	A	1	0	4	5.0	14.0	2079
16	1000006	P0096642	F	51-55	9	A	1	0	2	3.0	4.0	13055
17	1000006	P00058442	F	51-55	9	A	1	0	5	14.0	4.0	8851
18	1000007	P00036842	M	36-45	1	B	1	1	1	14.0	16.0	11788
20	1000008	P00220442	M	26-35	12	C	4+	1	5	14.0	15.0	8584
21	1000008	P00156442	M	26-35	12	C	4+	1	8	14.0	15.0	9872
22	1000008	P00213742	M	26-35	12	C	4+	1	8	14.0	15.0	9743
23	1000008	P00214442	M	26-35	12	C	4+	1	8	14.0	15.0	5982
24	1000008	P00303442	M	26-35	12	C	4+	1	1	8.0	14.0	11927
25	1000009	P00135742	M	26-35	17	C	0	0	6	8.0	14.0	16662
26	1000009	P00039942	M	26-35	17	C	0	0	8	8.0	14.0	5887
27	1000009	P00161442	M	26-35	17	C	0	0	5	14.0	14.0	6973
28	1000009	P00078742	M	26-35	17	C	0	0	5	8.0	14.0	5391
29	1000010	P00085942	F	36-45	1	B	4+	1	2	4.0	8.0	16352
30	1000010	P00118742	F	36-45	1	B	4+	1	5	11.0	8.0	8886
31	1000010	P00297942	F	36-45	1	B	4+	1	8	11.0	8.0	5875
32	1000010	P00266842	F	36-45	1	B	4+	1	5	11.0	8.0	8854
33	1000010	P00058342	F	36-45	1	B	4+	1	3	4.0	8.0	10946
...	...	...	...	...	...	...	...	...	...	...	...	...
537547	1004733	P00244042	M	18-25	18	C	1	0	1	2.0	15.0	11543
537548	1004734	P00111042	M	51-55	1	B	1	1	15	2.0	15.0	20924
537549	1004734	P00345842	M	51-55	1	B	1	1	2	8.0	14.0	13082
537550	1004735	P00278242	M	46-50	3	C	3	0	1	8.0	14.0	11658
537551	1004735	P00313442	M	46-50	3	C	3	0	5	6.0	8.0	6863
537552	1004735	P0098642	M	46-50	3	C	3	0	6	8.0	8.0	16415
537553	1004735	P00119342	M	46-50	3	C	3	0	10	13.0	8.0	18526
537554	1004735	P00114042	M	46-50	3	C	3	0	5	14.0	8.0	7099
537555	1004735	P00135142	M	46-50	3	C	3	0	13	16.0	8.0	578
537556	1004736	P00194542	M	18-25	20	A	1	1	8	14.0	8.0	2183
537557	1004736	P00175242	M	18-25	20	A	1	1	2	14.0	8.0	12724
537558	1004736	P00101942	M	18-25	20	A	1	1	8	17.0	8.0	7796
537559	1004736	P00109142	M	18-25	20	A	1	1	8	17.0	8.0	7770
537560	1004736	P00084842	M	18-25	20	A	1	1	8	16.0	8.0	5940
537561	1004736	P00078142	M	18-25	20	A	1	1	8	16.0	8.0	7834
537562	1004736	P00146742	M	18-25	20	A	1	1	1	13.0	14.0	11508
537563	1004736	P00154642	M	18-25	20	A	1	1	8	13.0	14.0	6074
537564	1004736	P00117442	M	18-25	20	A	1	1	5	14.0	14.0	7084
537565	1004736	P00051142	M	18-25	20	A	1	1	8	14.0	14.0	7934
537566	1004736	P00048742	M	18-25	20	A	1	1	5	14.0	14.0	5350
537567	1004736	P00157542	M	18-25	20	A	1	1	8	14.0	14.0	1994
537568	1004736	P00250642	M	18-25	20	A	1	1	11	14.0	14.0	5930
537569	1004736	P00023142	M	18-25	20	A	1	1	5	14.0	14.0	7042
537570	1004736	P00162442	M	18-25	20	A	1	1	1	16.0	14.0	15491
537571	1004737	P00221442	M	36-45	16	C	1	0	1	2.0	5.0	11852
537572	1004737	P00193542	M	36-45	16	C	1	0	1	2.0	5.0	11664
537573	1004737	P00111142	M	36-45	16	C	1	0	1	15.0	16.0	19196
537574	1004737	P00345942	M	36-45	16	C	1	0	8	15.0	16.0	8043
537575	1004737	P00285842	M	36-45	16	C	1	0	5	15.0	16.0	7172
537576	1004737	P00118242	M	36-45	16	C	1	0	5	8.0	16.0	6875
497270 rows × 12 columns

The where() method and masking
We can select values from a Series with a boolean vector and it returns a subset of the data. To guarantee that the output has the same shape as the original data, we can use the where method in Series and DataFrame.

We can select values from a DataFrame with a boolean criterion. It also preserves input data shape.

The below code is equivalent to

df2[df2==0]

It replaces values with NaN where the condition is false.

df2_where=df2.where(df2 == 0)


(df2_where).head(10)
User_ID	Product_ID	Gender	Age	Occupation	City_Category	Stay_In_Current_City_Years	Marital_Status	Product_Category_1	Product_Category_2	Product_Category_3	Purchase
0	NaN	NaN	NaN	NaN	NaN	NaN	NaN	0.0	NaN	NaN	NaN	NaN
1	NaN	NaN	NaN	NaN	NaN	NaN	NaN	0.0	NaN	NaN	NaN	NaN
2	NaN	NaN	NaN	NaN	NaN	NaN	NaN	0.0	NaN	NaN	NaN	NaN
3	NaN	NaN	NaN	NaN	NaN	NaN	NaN	0.0	NaN	NaN	NaN	NaN
4	NaN	NaN	NaN	NaN	NaN	NaN	NaN	0.0	NaN	NaN	NaN	NaN
5	NaN	NaN	NaN	NaN	NaN	NaN	NaN	0.0	NaN	NaN	NaN	NaN
6	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN
7	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN
8	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN
9	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN	NaN
Indexing with query() method
There is a query() method in the DataFrame objects that allows selection using an expression. This method queries the columns of a DataFrame with a boolean expression.

df2.query('(Product_Category_1 > Product_Category_2) & (Product_Category_2 > Product_Category_3)')
User_ID	Product_ID	Gender	Age	Occupation	City_Category	Stay_In_Current_City_Years	Marital_Status	Product_Category_1	Product_Category_2	Product_Category_3	Purchase
165	1000033	P00111742	M	46-50	3	A	1	1	15	8.0	5.0	17391
304	1000053	P00117542	M	26-35	0	B	1	0	18	16.0	5.0	3794
351	1000058	P00288642	M	26-35	2	B	3	0	16	14.0	12.0	16579
387	1000062	P00087242	F	36-45	3	A	1	0	14	12.0	6.0	11279
724	1000137	P00124642	F	46-50	6	C	4+	1	16	14.0	6.0	16828
1179	1000195	P00183142	M	26-35	12	B	4+	1	15	14.0	5.0	21224
1356	1000216	P00281942	M	46-50	13	B	1	0	15	11.0	10.0	12953
1766	1000284	P00180142	M	26-35	12	B	3	1	11	5.0	4.0	1602
1806	1000293	P00255842	M	55+	1	C	1	1	16	14.0	9.0	16875
1935	1000308	P00031142	M	26-35	2	A	3	1	16	14.0	12.0	16712
1967	1000314	P00117542	F	55+	9	C	1	0	18	17.0	13.0	2356
2025	1000324	P00312742	M	36-45	17	B	0	1	15	14.0	5.0	4198
2174	1000338	P00111742	M	36-45	7	A	1	0	15	14.0	12.0	8750
3226	1000529	P00111042	M	36-45	12	C	1	0	15	10.0	9.0	17045
3351	1000544	P0094442	M	36-45	12	B	2	0	18	14.0	4.0	3079
3506	1000566	P00111042	M	26-35	17	A	3	0	15	8.0	5.0	16661
3851	1000637	P00124342	M	36-45	12	B	2	1	11	9.0	5.0	7566
3944	1000648	P00298442	F	26-35	12	B	1	1	16	14.0	8.0	12635
4380	1000720	P00020542	M	18-25	0	B	0	0	18	17.0	15.0	897
5080	1000833	P00288642	M	36-45	7	C	1	1	16	15.0	5.0	12403
5113	1000839	P00046942	M	26-35	0	A	2	0	16	15.0	8.0	16421
5174	1000850	P00117542	M	36-45	0	A	3	1	18	11.0	8.0	2365
5361	1000875	P00355642	M	0-17	10	C	4+	0	16	13.0	5.0	20963
5909	1000957	P00117542	M	36-45	1	C	2	1	18	16.0	12.0	3059
6067	1000984	P00313742	M	51-55	16	A	2	1	18	8.0	5.0	3023
7916	1001227	P00061442	M	51-55	1	B	2	0	17	16.0	8.0	12767
8320	1001281	P00276142	M	26-35	19	C	1	0	12	8.0	5.0	1717
8321	1001283	P0097142	F	18-25	1	C	3	0	12	8.0	5.0	1759
8772	1001340	P00001842	M	26-35	7	A	2	0	16	11.0	8.0	4107
8882	1001357	P00326742	M	46-50	0	C	1	1	11	8.0	5.0	6076
...	...	...	...	...	...	...	...	...	...	...	...	...
529816	1003622	P00113642	M	18-25	1	B	2	1	8	6.0	5.0	8128
530284	1003688	P00119242	M	18-25	6	B	1	0	18	16.0	5.0	1590
530289	1003688	P00115842	M	18-25	6	B	1	0	16	14.0	5.0	16312
530711	1003747	P00355642	M	46-50	13	C	1	1	16	14.0	5.0	16868
530889	1003769	P00115842	M	26-35	15	B	0	0	16	10.0	8.0	20568
530897	1003769	P00136442	M	26-35	15	B	0	0	14	13.0	10.0	15227
531004	1003780	P00111042	M	0-17	0	C	0	0	15	14.0	8.0	21551
531339	1003824	P00271442	M	26-35	17	A	3	1	18	16.0	5.0	3107
531533	1003841	P00152542	M	46-50	18	A	4+	0	16	15.0	13.0	12791
531540	1003841	P00246842	M	46-50	18	A	4+	0	17	16.0	15.0	13201
531542	1003841	P00313742	M	46-50	18	A	4+	0	18	17.0	15.0	3786
531543	1003841	P00112042	M	46-50	18	A	4+	0	18	17.0	15.0	3869
531998	1003910	P00116742	M	26-35	20	A	2	0	11	8.0	5.0	5935
532279	1003958	P00174842	M	46-50	7	C	1	0	17	11.0	5.0	13231
532582	1004001	P00298742	F	26-35	1	B	1	1	14	11.0	8.0	14737
532784	1004024	P00002342	M	26-35	5	B	3	1	16	14.0	5.0	4610
533119	1004064	P00119242	M	46-50	0	A	1	1	18	15.0	4.0	2346
533703	1004150	P00327642	M	26-35	0	B	3	0	18	17.0	14.0	3825
533880	1004187	P00111742	F	55+	20	C	2	1	15	14.0	12.0	16649
533881	1004187	P00100542	F	55+	20	C	2	1	16	14.0	12.0	20307
534320	1004271	P00344142	M	36-45	7	B	2	0	18	17.0	9.0	1565
535677	1004452	P00296242	F	26-35	7	B	2	1	8	6.0	5.0	8065
535679	1004452	P00263542	F	26-35	7	B	2	1	16	8.0	5.0	12547
535813	1004472	P00307142	F	46-50	16	B	0	1	8	6.0	5.0	6045
536467	1004560	P00054042	M	26-35	0	C	1	0	18	16.0	8.0	3136
536596	1004579	P00112042	F	18-25	4	B	1	1	18	17.0	14.0	3074
536944	1004644	P00327642	M	51-55	1	C	4+	0	18	15.0	8.0	3127
537361	1004708	P00344142	M	26-35	0	B	3	0	18	14.0	6.0	2351
537410	1004725	P00123742	M	36-45	5	A	2	0	11	8.0	5.0	4690
537417	1004725	P00349142	M	36-45	5	A	2	0	11	8.0	5.0	4645
2243 rows × 12 columns

14. Indexing and reindexing in pandas
Reindexing changes the row labels and column labels of a DataFrame. To reindex means to conform the data to match a given set of labels along a particular axis.

Multiple operations can be accomplished through indexing like :−

Reorder the existing data to match a new set of labels.
Insert missing value (NA) markers in label locations where no data for the label existed.
Create a new dataframe
First of all, I will create a new dataframe as follows:-

# let's create a new dataframe 

food = pd.DataFrame({'Place':['Home', 'Home', 'Hotel', 'Hotel'],
                   'Time': ['Lunch', 'Dinner', 'Lunch', 'Dinner'],
                   'Food':['Soup', 'Rice', 'Soup', 'Chapati'],
                   'Price($)':[10, 20, 30, 40]})

food
Place	Time	Food	Price($)
0	Home	Lunch	Soup	10
1	Home	Dinner	Rice	20
2	Hotel	Lunch	Soup	30
3	Hotel	Dinner	Chapati	40
Set an index
DataFrame has a set_index() method which takes a column name (for a regular Index) or a list of column names (for a MultiIndex). This method sets the dataframe index using existing columns.

I will create a new, re-indexed DataFrame with set_index() method as follows:-

food_indexed1=food.set_index('Place')

food_indexed1
Time	Food	Price($)
Place			
Home	Lunch	Soup	10
Home	Dinner	Rice	20
Hotel	Lunch	Soup	30
Hotel	Dinner	Chapati	40
food_indexed2=food.set_index(['Place', 'Time'])

food_indexed2
Food	Price($)
Place	Time		
Home	Lunch	Soup	10
Dinner	Rice	20
Hotel	Lunch	Soup	30
Dinner	Chapati	40
Reset the index
There is a function called reset_index() which transfers the index values into the DataFrame’s columns and sets a simple integer index. This is the inverse operation of set_index().

food_indexed2.reset_index()
Place	Time	Food	Price($)
0	Home	Lunch	Soup	10
1	Home	Dinner	Rice	20
2	Hotel	Lunch	Soup	30
3	Hotel	Dinner	Chapati	40
15. MultiIndex or Advanced indexing
In this section, I will explore indexing with a MultiIndex and other advanced indexing strategies.

Hierarchical indexing or MultiIndex
The MultiIndex object is the hierarchical analogue of the standard index object which stores the axis labels in pandas objects. A MultiIndex is an array of tuples where each tuple is unique. A MultiIndex can be created from a list of arrays (using MultiIndex.from_arrays()), an array of tuples (using MultiIndex.from_tuples()), a crossed set of iterables (using MultiIndex.from_product()), or a DataFrame (using MultiIndex.from_frame()). The Index constructor will attempt to return a MultiIndex when it is passed a list of tuples.

To demonstrate the concept of hierarchical or multiple indexing, first I will create a hypothetical dataframe as follows:-

sales=pd.DataFrame([['books','online', 200, 50],['books','retail', 250, 75], 
                    ['toys','online', 100, 20],['toys','retail', 140, 30],
                    ['watches','online', 500, 100],['watches','retail', 600, 150],
                    ['computers','online', 1000, 200],['computers','retail', 1200, 300],
                    ['laptops','online', 1100, 400],['laptops','retail', 1400, 500],
                    ['smartphones','online', 600, 200],['smartphones','retail', 800, 250]],
                    columns=['Items', 'Mode', 'Price', 'Profit'])


sales
Items	Mode	Price	Profit
0	books	online	200	50
1	books	retail	250	75
2	toys	online	100	20
3	toys	retail	140	30
4	watches	online	500	100
5	watches	retail	600	150
6	computers	online	1000	200
7	computers	retail	1200	300
8	laptops	online	1100	400
9	laptops	retail	1400	500
10	smartphones	online	600	200
11	smartphones	retail	800	250
Create the hierarchical index in pandas
We can create a hierarchical index in pandas using the set_index() function which is used for indexing. First the data is indexed on Items and then on Mode column as follows:-

sales1=sales.set_index(['Items', 'Mode'])

sales1
Price	Profit
Items	Mode		
books	online	200	50
retail	250	75
toys	online	100	20
retail	140	30
watches	online	500	100
retail	600	150
computers	online	1000	200
retail	1200	300
laptops	online	1100	400
retail	1400	500
smartphones	online	600	200
retail	800	250
The resultant dataframe will be a hierarchical dataframe as shown above.

View index in hierarchical index
One can view the details of index as shown below:-

# View index

sales1.index
MultiIndex(levels=[['books', 'computers', 'laptops', 'smartphones', 'toys', 'watches'], ['online', 'retail']],
           labels=[[0, 0, 4, 4, 5, 5, 1, 1, 2, 2, 3, 3], [0, 1, 0, 1, 0, 1, 0, 1, 0, 1, 0, 1]],
           names=['Items', 'Mode'])
Swap the column in hierarchical index
Now, I will swap the "Items" and "Mode" columns in the above hierarchical dataframe as shown below:-

# Swap the column  in multiple index

sales2=sales1.swaplevel('Mode', 'Items')

sales2
Price	Profit
Mode	Items		
online	books	200	50
retail	books	250	75
online	toys	100	20
retail	toys	140	30
online	watches	500	100
retail	watches	600	150
online	computers	1000	200
retail	computers	1200	300
online	laptops	1100	400
retail	laptops	1400	500
online	smartphones	600	200
retail	smartphones	800	250
16. Sorting in pandas
Pandas provides two kinds of sorting. They are:-

Sorting by label
Sorting by actual value
They are described below:-

1. Sorting by label
We can use the sort_index() method to sort the object by labels. DataFrame can be sorted by passing the axis arguments and the order of sorting. By default, sorting is done on row labels in ascending order.

The following examples illustrate the idea of sorting by label.

# sort the dataframe df2 by label

df2.sort_index()
User_ID	Product_ID	Gender	Age	Occupation	City_Category	Stay_In_Current_City_Years	Marital_Status	Product_Category_1	Product_Category_2	Product_Category_3	Purchase
0	1000001	P00069042	F	0-17	10	A	2	0	3	6.0	14.0	8370
1	1000001	P00248942	F	0-17	10	A	2	0	1	6.0	14.0	15200
2	1000001	P00087842	F	0-17	10	A	2	0	12	6.0	14.0	1422
3	1000001	P00085442	F	0-17	10	A	2	0	12	14.0	14.0	1057
4	1000002	P00285442	M	55+	16	C	4+	0	8	14.0	14.0	7969
5	1000003	P00193542	M	26-35	15	A	3	0	1	2.0	14.0	15227
6	1000004	P00184942	M	46-50	7	B	2	1	1	8.0	17.0	19215
7	1000004	P00346142	M	46-50	7	B	2	1	1	15.0	17.0	15854
8	1000004	P0097242	M	46-50	7	B	2	1	1	16.0	17.0	15686
9	1000005	P00274942	M	26-35	20	A	1	1	8	16.0	17.0	7871
10	1000005	P00251242	M	26-35	20	A	1	1	5	11.0	17.0	5254
11	1000005	P00014542	M	26-35	20	A	1	1	8	11.0	17.0	3957
12	1000005	P00031342	M	26-35	20	A	1	1	8	11.0	17.0	6073
13	1000005	P00145042	M	26-35	20	A	1	1	1	2.0	5.0	15665
14	1000006	P00231342	F	51-55	9	A	1	0	5	8.0	14.0	5378
15	1000006	P00190242	F	51-55	9	A	1	0	4	5.0	14.0	2079
16	1000006	P0096642	F	51-55	9	A	1	0	2	3.0	4.0	13055
17	1000006	P00058442	F	51-55	9	A	1	0	5	14.0	4.0	8851
18	1000007	P00036842	M	36-45	1	B	1	1	1	14.0	16.0	11788
19	1000008	P00249542	M	26-35	12	C	4+	1	1	5.0	15.0	19614
20	1000008	P00220442	M	26-35	12	C	4+	1	5	14.0	15.0	8584
21	1000008	P00156442	M	26-35	12	C	4+	1	8	14.0	15.0	9872
22	1000008	P00213742	M	26-35	12	C	4+	1	8	14.0	15.0	9743
23	1000008	P00214442	M	26-35	12	C	4+	1	8	14.0	15.0	5982
24	1000008	P00303442	M	26-35	12	C	4+	1	1	8.0	14.0	11927
25	1000009	P00135742	M	26-35	17	C	0	0	6	8.0	14.0	16662
26	1000009	P00039942	M	26-35	17	C	0	0	8	8.0	14.0	5887
27	1000009	P00161442	M	26-35	17	C	0	0	5	14.0	14.0	6973
28	1000009	P00078742	M	26-35	17	C	0	0	5	8.0	14.0	5391
29	1000010	P00085942	F	36-45	1	B	4+	1	2	4.0	8.0	16352
...	...	...	...	...	...	...	...	...	...	...	...	...
537547	1004733	P00244042	M	18-25	18	C	1	0	1	2.0	15.0	11543
537548	1004734	P00111042	M	51-55	1	B	1	1	15	2.0	15.0	20924
537549	1004734	P00345842	M	51-55	1	B	1	1	2	8.0	14.0	13082
537550	1004735	P00278242	M	46-50	3	C	3	0	1	8.0	14.0	11658
537551	1004735	P00313442	M	46-50	3	C	3	0	5	6.0	8.0	6863
537552	1004735	P0098642	M	46-50	3	C	3	0	6	8.0	8.0	16415
537553	1004735	P00119342	M	46-50	3	C	3	0	10	13.0	8.0	18526
537554	1004735	P00114042	M	46-50	3	C	3	0	5	14.0	8.0	7099
537555	1004735	P00135142	M	46-50	3	C	3	0	13	16.0	8.0	578
537556	1004736	P00194542	M	18-25	20	A	1	1	8	14.0	8.0	2183
537557	1004736	P00175242	M	18-25	20	A	1	1	2	14.0	8.0	12724
537558	1004736	P00101942	M	18-25	20	A	1	1	8	17.0	8.0	7796
537559	1004736	P00109142	M	18-25	20	A	1	1	8	17.0	8.0	7770
537560	1004736	P00084842	M	18-25	20	A	1	1	8	16.0	8.0	5940
537561	1004736	P00078142	M	18-25	20	A	1	1	8	16.0	8.0	7834
537562	1004736	P00146742	M	18-25	20	A	1	1	1	13.0	14.0	11508
537563	1004736	P00154642	M	18-25	20	A	1	1	8	13.0	14.0	6074
537564	1004736	P00117442	M	18-25	20	A	1	1	5	14.0	14.0	7084
537565	1004736	P00051142	M	18-25	20	A	1	1	8	14.0	14.0	7934
537566	1004736	P00048742	M	18-25	20	A	1	1	5	14.0	14.0	5350
537567	1004736	P00157542	M	18-25	20	A	1	1	8	14.0	14.0	1994
537568	1004736	P00250642	M	18-25	20	A	1	1	11	14.0	14.0	5930
537569	1004736	P00023142	M	18-25	20	A	1	1	5	14.0	14.0	7042
537570	1004736	P00162442	M	18-25	20	A	1	1	1	16.0	14.0	15491
537571	1004737	P00221442	M	36-45	16	C	1	0	1	2.0	5.0	11852
537572	1004737	P00193542	M	36-45	16	C	1	0	1	2.0	5.0	11664
537573	1004737	P00111142	M	36-45	16	C	1	0	1	15.0	16.0	19196
537574	1004737	P00345942	M	36-45	16	C	1	0	8	15.0	16.0	8043
537575	1004737	P00285842	M	36-45	16	C	1	0	5	15.0	16.0	7172
537576	1004737	P00118242	M	36-45	16	C	1	0	5	8.0	16.0	6875
537577 rows × 12 columns

Order of sorting
By passing the Boolean value to ascending parameter, the order of the sorting can be controlled.

sort the dataframe df2 by label in reverse order
df2.sort_index(ascending=False)

Sorting by columns
By passing the axis argument with a value 0 or 1, the sorting can be done on the row or column labels.

The default value of axis=0. In this case, sorting can be done by rows.

If we set axis=1, sorting is done by columns.

sort the dataframe df2 by columns
df2.sort_index(axis=1)

2. Sorting by values
The second method of sorting is sorting by values. Pandas provides sort_values() method to sort by values. It accepts a 'by' argument which will use the column name of the DataFrame with which the values are to be sorted.

The following example illustrates the idea:-

df2.sort_values(by=['Product_Category_1'])
User_ID	Product_ID	Gender	Age	Occupation	City_Category	Stay_In_Current_City_Years	Marital_Status	Product_Category_1	Product_Category_2	Product_Category_3	Purchase
133832	1002649	P00114942	M	26-35	16	C	2	0	1	15.0	16.0	19479
205338	1001676	P00155442	M	18-25	4	B	4+	0	1	11.0	15.0	7872
205336	1001676	P00251642	M	18-25	4	B	4+	0	1	2.0	4.0	4466
429787	1000163	P00222942	M	18-25	4	A	1	0	1	2.0	8.0	4430
429786	1000163	P00184442	M	18-25	4	A	1	0	1	6.0	8.0	3912
429785	1000163	P00030842	M	18-25	4	A	1	0	1	2.0	15.0	8133
429784	1000163	P00182742	M	18-25	4	A	1	0	1	2.0	14.0	11673
330703	1002986	P00016342	M	26-35	4	A	2	1	1	2.0	8.0	11598
429783	1000163	P00354042	M	18-25	4	A	1	0	1	6.0	16.0	3923
429782	1000163	P00237542	M	18-25	4	A	1	0	1	15.0	16.0	19097
429781	1000163	P00025442	M	18-25	4	A	1	0	1	2.0	9.0	8284
429773	1000162	P00334242	F	18-25	4	C	4+	0	1	8.0	14.0	19102
429772	1000162	P00182742	F	18-25	4	C	4+	0	1	2.0	14.0	15187
107002	1004458	P00070342	F	26-35	4	B	1	0	1	2.0	14.0	11804
205330	1001675	P00143642	F	26-35	6	B	1	1	1	2.0	6.0	4282
106995	1004458	P00338442	F	26-35	4	B	1	0	1	16.0	9.0	15772
330702	1002986	P0098342	M	26-35	4	A	2	1	1	2.0	5.0	7844
106984	1004457	P00114942	M	36-45	14	C	1	0	1	15.0	16.0	19409
205341	1001676	P00221442	M	18-25	4	B	4+	0	1	2.0	5.0	15408
429814	1000169	P00080342	M	26-35	7	B	3	0	1	6.0	8.0	15447
330700	1002986	P00193542	M	26-35	4	A	2	1	1	2.0	5.0	11829
106965	1004454	P00184442	M	26-35	20	C	1	0	1	6.0	8.0	11439
106968	1004454	P00112642	M	26-35	20	C	1	0	1	2.0	5.0	15795
429804	1000166	P00345642	M	18-25	4	B	1	1	1	15.0	16.0	7958
106970	1004454	P00031842	M	26-35	20	C	1	0	1	5.0	12.0	4216
429801	1000165	P00293842	M	18-25	16	A	1	0	1	2.0	9.0	15666
106972	1004454	P00173842	M	26-35	20	C	1	0	1	2.0	15.0	4044
106973	1004455	P00080342	M	36-45	7	B	1	0	1	6.0	8.0	15249
429799	1000165	P00201442	M	18-25	16	A	1	0	1	6.0	8.0	15915
106976	1004455	P00183442	M	36-45	7	B	1	0	1	2.0	8.0	12010
...	...	...	...	...	...	...	...	...	...	...	...	...
38029	1005848	P00117542	M	51-55	20	A	0	1	18	16.0	8.0	3857
335244	1003643	P00054042	M	26-35	17	C	1	0	18	12.0	15.0	3029
266269	1005012	P00058642	M	51-55	15	A	1	1	18	14.0	9.0	3769
360529	1001503	P00220942	M	26-35	12	A	2	0	18	13.0	16.0	3117
239326	1000937	P00117542	M	26-35	15	A	2	1	18	11.0	13.0	3862
534320	1004271	P00344142	M	36-45	7	B	2	0	18	17.0	9.0	1565
382999	1004918	P00054042	F	18-25	12	C	1	0	18	14.0	15.0	3136
421525	1004852	P00286042	M	36-45	0	C	3	1	18	2.0	14.0	2252
421526	1004852	P00325542	M	36-45	0	C	3	1	18	2.0	14.0	3041
421527	1004852	P00054042	M	36-45	0	C	3	1	18	2.0	14.0	2280
357843	1001140	P00327642	F	46-50	2	B	2	1	18	8.0	17.0	3800
115211	1005786	P00119242	M	26-35	6	B	1	1	18	16.0	5.0	3011
138949	1003490	P00058642	M	26-35	0	C	4+	1	18	17.0	16.0	3082
478741	1001717	P00058642	F	51-55	6	B	1	0	18	17.0	6.0	3007
57997	1002945	P00117542	F	36-45	17	C	4+	1	18	15.0	18.0	2324
249091	1002348	P00344042	M	51-55	12	C	4+	1	18	8.0	14.0	1510
397412	1001181	P00037442	M	36-45	7	A	3	1	18	18.0	12.0	2274
193495	1005880	P00344142	M	26-35	1	A	1	1	18	16.0	16.0	1570
499138	1004852	P00281242	M	36-45	0	C	3	1	18	6.0	8.0	2367
16263	1002496	P00327642	M	51-55	1	B	1	0	18	14.0	4.0	2347
349842	1005880	P00313742	M	26-35	1	A	1	1	18	11.0	15.0	1645
115157	1005775	P00117542	M	26-35	11	A	4+	0	18	17.0	6.0	3771
499206	1004867	P00117542	M	26-35	16	A	3	0	18	5.0	14.0	3763
335200	1003635	P00327642	M	51-55	1	C	1	0	18	2.0	14.0	3837
397461	1001182	P00313742	M	0-17	10	B	3	0	18	11.0	14.0	3141
312626	1000169	P00313742	M	26-35	7	B	3	0	18	2.0	15.0	3113
352980	1000352	P00037442	M	18-25	4	A	0	0	18	2.0	5.0	3119
239271	1000929	P00271542	M	26-35	15	A	1	0	18	11.0	16.0	3105
460422	1004869	P00068442	F	46-50	6	C	3	1	18	8.0	15.0	3751
492245	1003810	P00119242	M	51-55	7	C	1	0	18	8.0	9.0	3888
537577 rows × 12 columns

Sort by multiple columns
df2.sort_values(by=['Product_Category_1', 'Product_Category_2'])

Sort in descending order
df2.sort_values(by='Product_Category_1', ascending=False)

17. Categorical data in pandas
We can check the data types of variables in the dataset with the following command:-

df3 = df.copy()

df3.dtypes
User_ID                         int64
Product_ID                     object
Gender                         object
Age                            object
Occupation                      int64
City_Category                  object
Stay_In_Current_City_Years     object
Marital_Status                  int64
Product_Category_1              int64
Product_Category_2            float64
Product_Category_3            float64
Purchase                        int64
dtype: object
We can see that our dataset has 5 categorical variables. They are Product_ID, Gender, Age, City_Category and Stay_In_Current_City_Years. They have data types as object.

Now, I will explore these categorical variables.

Description of categorical data
The describe() method on categorical data will produce similar output to a Series or DataFrame of type string.

df3['Gender'].describe()
count     537577
unique         2
top            M
freq      405380
Name: Gender, dtype: object
The Gender category has 537577 counts, 2 unique values and frequency of top value M is 405380.

df3['Age'].describe()
count     537577
unique         7
top        26-35
freq      214690
Name: Age, dtype: object
There are 7 unique categories in Age variable. The most frequent category is 26-35 with frequency count of 214690.

df3['City_Category'].describe()
count     537577
unique         3
top            B
freq      226493
Name: City_Category, dtype: object
There are 3 unique categories in City_Category variable. The most frequent category is B with frequency count of 226493.

Working with categorical data
Categorical data has a categories and a ordered property, which list their possible values and whether the ordering matters or not. These properties are exposed as s.cat.categories and s.cat.ordered.

If we don't manually specify categories and ordering, they are inferred from the passed arguments.

s.cat.categories

s.cat.ordered

where s is a series object.

Unique values in categorical data
We can get the unique values in a series object by unique() method. It returns categories in the order of appearance, and it only includes values that are actually present.

df3['Gender'].unique()
array(['F', 'M'], dtype=object)
df3['Age'].unique()
array(['0-17', '55+', '26-35', '46-50', '51-55', '36-45', '18-25'],
      dtype=object)
Rename categories
Renaming categories is done by assigning new values to the Series.cat.categories property or by using the rename_categories() method.

Append new categories
Appending categories can be done by using the add_categories() method.

Remove categories
Removing categories can be done by using the remove_categories() method. Values which are removed are replaced by np.nan.

Setting categories
If we want to remove and add new categories in one step (which has some speed advantage), or simply set the categories to a predefined scale, we can use set_categories() method.

Reordering categories
Reordering the categories is possible via the Categorical.reorder_categories() and the Categorical.set_categories() methods.

Operations on categorical data
There are several operations like Series.min(), Series.max(), Series.median() and Series.mode() which are possible with categorical data.

Frequency counts of categorical data
Series methods like Series.value_counts() will return the frequency counts of the categories present in the series.

df3['Gender'].value_counts()
M    405380
F    132197
Name: Gender, dtype: int64
df3['City_Category'].value_counts()
B    226493
C    166446
A    144638
Name: City_Category, dtype: int64
Series.value_counts() will return the frequency counts of the categories in descending order. To get the categories in ascending order we should set ascending=True as follows:-

df3['Gender'].value_counts(ascending=True)
F    132197
M    405380
Name: Gender, dtype: int64
df3['City_Category'].value_counts(ascending=True)
A    144638
C    166446
B    226493
Name: City_Category, dtype: int64
18. Basic functionality in pandas
Series basic functionality
The following table lists the important attributes or methods in Series basic functionality.

axes - Returns a list of the row axis labels
dtype - Returns the dtype of the object.
empty - Returns True if series is empty.
ndim - Returns the number of dimensions of the underlying data, by definition 1.
size - Returns the number of elements in the underlying data.
values - Returns the Series as ndarray.
head() - Returns the first n rows.
tail() - Returns the last n rows.
Dataframe basic functionality
The following tables lists the important attributes or methods in Dataframe basic functionality.

T - Transposes rows and columns.
axes - Returns a list with the row axis labels and column axis labels as the only members.
dtypes - Returns the dtypes in this object.
empty - True if NDFrame is entirely empty [no items]; if any of the axes are of length 0.
ndim - Number of axes / array dimensions.
shape - Returns a tuple representing the dimensionality of the Dataframe.
size - Number of elements in the NDFrame.
values - Numpy representation of NDFrame.
head() - Returns the first n rows.
tail() - Returns last n rows.
19. Descriptive statistics in pandas
There exists a large number of methods for computing descriptive statistics and other related operations on Series, DataFrame, and Panel. Most of these are aggregations (hence producing a lower-dimensional result) like sum(), mean(), and quantile(), but some of them, like cumsum() and cumprod(), produce an object of the same size. Generally speaking, these methods take an axis argument, just like ndarray.{sum, std, …}, but the axis can be specified by name or integer.

Series: no axis argument needed.
DataFrame: “index” (axis=0, default), “columns” (axis=1).
Panel: “items” (axis=0), “major” (axis=1, default), “minor” (axis=2).
Functions and description
The following table list down the important functions under Descriptive Statistics in Python Pandas.

1 count() - Number of non-null observations
2 sum() - Sum of values
3 mean() - Mean of values
4 median() - Median of values
5 mode() - Mode of values
6 std() - Standard deviation of the values
7 min() - Minimum value
8 max() - Maximum value
9 abs() - Absolute value
10 prod() - Product of values
11 cumsum() - Cumulative sum
12 cumprod() - Cumulative product
The dataframe is a heterogeneous data structure. So, the different column values have different data types. Generic operations don't work with all functions.

Functions like sum(), cumsum() work with both numeric and character (or) string data elements without any error. In practice, character aggregations are never used generally. These functions do not throw any exception.

Functions like abs(), cumprod() throw exception when the dataframe contains character or string data because such operations cannot be performed.

df4=df.copy()

df4.max(0)
User_ID                        1006040
Product_ID                    P0099942
Gender                               M
Age                                55+
Occupation                          20
City_Category                        C
Stay_In_Current_City_Years          4+
Marital_Status                       1
Product_Category_1                  18
Product_Category_2                  18
Product_Category_3                  18
Purchase                         23961
dtype: object
Summarizing data
The describe() function computes the summary statistics of the numerical columns in the dataframe.

This function gives the mean, std and IQR values. It excludes the character columns and gives summary about numeric columns. It includes the argument which is used to pass necessary information regarding what columns need to be considered for summarizing. It takes the list of values; by default, 'number'.

object − Summarizes string columns
number − Summarizes numeric columns
all − Summarizes all columns together
df4.describe()
User_ID	Occupation	Marital_Status	Product_Category_1	Product_Category_2	Product_Category_3	Purchase
count	5.375770e+05	537577.00000	537577.000000	537577.000000	537577.000000	537577.000000	537577.000000
mean	1.002992e+06	8.08271	0.408797	5.295546	9.922686	12.665430	9333.859853
std	1.714393e+03	6.52412	0.491612	3.750701	5.022222	4.127122	4981.022133
min	1.000001e+06	0.00000	0.000000	1.000000	2.000000	3.000000	185.000000
25%	1.001495e+06	2.00000	0.000000	1.000000	5.000000	9.000000	5866.000000
50%	1.003031e+06	7.00000	0.000000	5.000000	9.000000	14.000000	8062.000000
75%	1.004417e+06	14.00000	1.000000	8.000000	15.000000	16.000000	12073.000000
max	1.006040e+06	20.00000	1.000000	18.000000	18.000000	18.000000	23961.000000
20. Statistical functions in pandas
Statistical functions help us to understand and analyze the behavior of data. In this section, I will discuss few statistical functions, which we can apply on Pandas objects.

Percent_change
Series, datFrames and panel, all have the function pct_change(). This function compares every element with its prior element and computes the change percentage.

By default, the pct_change() operates on columns; if you want to apply the same row wise, then use axis=1() argument.

Covariance
Covariance is applied on series data. The series object has a method cov() to compute covariance between series objects. NA values will be excluded automatically.

Series.cov() can be used to compute covariance between series (excluding missing values).

Analogously, dataFrame.cov() to compute pairwise covariances among the series in the dataFrame, also excluding NA/null values.

df5=df.copy()


# view the covariance

df5.cov()
User_ID	Occupation	Marital_Status	Product_Category_1	Product_Category_2	Product_Category_3	Purchase
User_ID	2.939142e+06	-257.522212	15.787429	23.708294	14.679685	14.455050	4.602301e+04
Occupation	-2.575222e+02	42.564139	0.079192	-0.198560	-0.008768	0.112611	6.858232e+02
Marital_Status	1.578743e+01	0.079192	0.241683	0.037884	0.037090	0.025665	3.159307e-01
Product_Category_1	2.370829e+01	-0.198560	0.037884	14.067758	6.823287	0.988208	-5.868580e+03
Product_Category_2	1.467968e+01	-0.008768	0.037090	6.823287	25.222716	4.828654	-3.899162e+03
Product_Category_3	1.445505e+01	0.112611	0.025665	0.988208	4.828654	17.033138	5.542700e+01
Purchase	4.602301e+04	685.823205	0.315931	-5868.580224	-3899.162103	55.427003	2.481058e+07
Correlation
Correlation shows the linear relationship between any two array of values (series). There are multiple methods to compute the correlation. These methods are listed below:-

Method name Description

pearson (default) - Standard correlation coefficient
kendall - Kendall Tau correlation coefficient
spearman - Spearman rank correlation coefficient
All of these are currently computed using pairwise complete observations.

Any non-numeric columns will be automatically excluded from the correlation calculation.

# view the correlation

df5.corr()
User_ID	Occupation	Marital_Status	Product_Category_1	Product_Category_2	Product_Category_3	Purchase
User_ID	1.000000	-0.023024	0.018732	0.003687	0.001705	0.002043	0.005389
Occupation	-0.023024	1.000000	0.024691	-0.008114	-0.000268	0.004182	0.021104
Marital_Status	0.018732	0.024691	1.000000	0.020546	0.015022	0.012650	0.000129
Product_Category_1	0.003687	-0.008114	0.020546	1.000000	0.362231	0.063839	-0.314125
Product_Category_2	0.001705	-0.000268	0.015022	0.362231	1.000000	0.232961	-0.155868
Product_Category_3	0.002043	0.004182	0.012650	0.063839	0.232961	1.000000	0.002696
Purchase	0.005389	0.021104	0.000129	-0.314125	-0.155868	0.002696	1.000000
Data Ranking
Data Ranking produces ranking for each element in the array of elements. In case of ties, assigns the mean rank.

The rank() method produces a data ranking with ties being assigned the mean of the ranks (by default) for the group.

The rank() is also a dataframe method and can rank either the rows (axis=0) or the columns (axis=1). NaN values are excluded from the ranking.

It optionally takes a parameter ascending which true by default. If it is set to false, data is ranked in descending order, with larger values assigned a smaller rank.

The rank() supports different tie-breaking methods, specified with the method parameter as follows:-

average - average rank of tied group
min - lowest rank in the group
max - highest rank in the group
first - ranks assigned in the order they appear in the array
# view the top 25 rows of ranked dataframe

df5.rank(1).head(25)
User_ID	Occupation	Marital_Status	Product_Category_1	Product_Category_2	Product_Category_3	Purchase
0	7.0	4.0	1.0	2.0	3.0	5.0	6.0
1	7.0	4.0	1.0	2.0	3.0	5.0	6.0
2	7.0	3.0	1.0	4.0	2.0	5.0	6.0
3	7.0	2.0	1.0	3.0	4.5	4.5	6.0
4	7.0	5.0	1.0	2.0	3.5	3.5	6.0
5	7.0	5.0	1.0	2.0	3.0	4.0	6.0
6	7.0	3.0	1.5	1.5	4.0	5.0	6.0
7	7.0	3.0	1.5	1.5	4.0	5.0	6.0
8	7.0	3.0	1.5	1.5	4.0	5.0	6.0
9	7.0	5.0	1.0	2.0	3.0	4.0	6.0
10	7.0	5.0	1.0	2.0	3.0	4.0	6.0
11	7.0	5.0	1.0	2.0	3.0	4.0	6.0
12	7.0	5.0	1.0	2.0	3.0	4.0	6.0
13	7.0	5.0	1.5	1.5	3.0	4.0	6.0
14	7.0	4.0	1.0	2.0	3.0	5.0	6.0
15	7.0	4.0	1.0	2.0	3.0	5.0	6.0
16	7.0	5.0	1.0	2.0	3.0	4.0	6.0
17	7.0	4.0	1.0	3.0	5.0	2.0	6.0
18	7.0	2.0	2.0	2.0	4.0	5.0	6.0
19	7.0	4.0	1.5	1.5	3.0	5.0	6.0
20	7.0	3.0	1.0	2.0	4.0	5.0	6.0
21	7.0	3.0	1.0	2.0	4.0	5.0	6.0
22	7.0	3.0	1.0	2.0	4.0	5.0	6.0
23	7.0	3.0	1.0	2.0	4.0	5.0	6.0
24	7.0	4.0	1.5	1.5	3.0	5.0	6.0
Common statistical functions
There are a number of common statistical functions. These are listed below:-

Method - Description

count() - Number of non-null observations
sum() - Sum of values
mean() - Mean of values
median() - Arithmetic median of values
min() - Minimum
max() - Maximum
std() - Standard deviation
var() - Variance
skew() - Skewness
kurt() - Kurtosis
quantile() - Quantile
apply() - Generic apply
cov() - Covariance
corr() - Correlation
The apply() function takes an extra func argument and performs generic rolling computations. The func argument should be a single function that produces a single value from an ndarray input.

21. Window functions in pandas
For working with numerical data, Pandas provide few variants like rolling, expanding and exponentially moving weights for window statistics.

Among these are count, sum, mean, median, correlation, variance, covariance, standard deviation, skewness and kurtosis.

The rolling() and expanding() functions can be used directly from DataFrameGroupBy objects.

In this section, we work with rolling, expanding and exponentially weighted data through the corresponding objects, Rolling, Expanding and EWM.

.rolling() function
This function can be applied on a series of data. Specify the window=n argument and apply the appropriate statistical function on top of it.

df6=df.copy()

df6.rolling(window=3).mean()

Since the window size is 3, for first two elements there are nulls and from third the value will be the average of the n, n-1 and n-2 elements. We can also apply various functions.

.expanding() function
This function can be applied on a series of data. We specify the min_periods=n argument and apply the appropriate statistical function on top of it.

df6.expanding(min_periods=3).mean()

.ewm() function
ewm is applied on a series of data. We have to specify any of the com, span, halflife argument and apply the appropriate statistical function on top of it. It assigns the weights exponentially.

df6.ewm(com=0.5).mean()

Window functions are used in finding the trends within the data graphically by smoothing the curve. If there is a lot of variation in the data, then we can apply window functions to smooth out the curve or the trend.

21. Aggregations in pandas
Once the rolling, expanding and ewm objects are created, several methods are available to perform aggregations on data.

Apply aggregation on a whole dataframe
df6=df.copy

df6.aggregate(np.sum)

Apply aggregation on a single column of a dataframe
df6=df.copy()


df6['Purchase'].aggregate(np.sum)
5017668378
Apply multiple functions on a single column of a dataframe
df6['Purchase'].aggregate([np.sum, np.mean])
sum     5.017668e+09
mean    9.333860e+03
Name: Purchase, dtype: float64
Apply aggregation on multiple columns of a dataframe
df6[['Product_Category_1', 'Product_Category_2', 'Product_Category_3']].aggregate(np.mean)
Product_Category_1     5.295546
Product_Category_2     9.922686
Product_Category_3    12.665430
dtype: float64
Apply multiple functions on multiple columns of a dataframe
df6[['Product_Category_1', 'Product_Category_2', 'Product_Category_3']].aggregate([np.sum, np.mean])
Product_Category_1	Product_Category_2	Product_Category_3
sum	2.846764e+06	5.334208e+06	6.808644e+06
mean	5.295546e+00	9.922686e+00	1.266543e+01
Apply different functions to different columns of a dataframe
df6.aggregate({'Product_Category_1' : np.sum ,'Product_Category_2' : np.mean})
Product_Category_1    2.846764e+06
Product_Category_2    9.922686e+00
dtype: float64
23. Iteration in pandas
The behavior of basic iteration over Pandas objects depends on the type. When iterating over a Series, it is regarded as array-like, and basic iteration produces the values. Other data structures, like DataFrame and Panel, follow the dict-like convention of iterating over the keys of the objects.

Iterating a dataframe gives column names.

To iterate over the rows of the DataFrame, we can use the following functions −

iteritems() − to iterate over the (key,value) pairs
iterrows() − iterate over the rows as (index,series) pairs
itertuples() − iterate over the rows as namedtuples
24. Function application in pandas
There are three important methods that enable us to apply our own or another library's functions to pandas objects. These methods differentiate on their scope of usage. These functions expect to operate on an entire dataframe, row- or column-wise operation, or element wise operation. These methods are described below:-

Table wise Function Application: pipe()
Row or Column Wise Function Application: apply()
Element wise Function Application: applymap()
Table-wise Function Application:pipe()
Custom operations can be performed by passing the function and the appropriate number of parameters as pipe arguments. Thus, operation is performed on the whole DataFrame.

For example, if we want to add a value 10 to all the elements in the DataFrame. Then, we can make use of pipe() function as follows:-

def addten(x1,x2):

`return x1+x2`


df7=df.copy()

df7.pipe(addten,10)

Row or Column Wise Function Application: apply()
Arbitrary functions can be applied along the axes of a DataFrame or Panel using the apply() method. It takes an optional axis argument. By default, the operation performs column wise, taking each column as an array-like.

df7.apply(np.mean)

By passing axis parameter, operations can be performed row wise.

df7.apply(np.mean,axis=1)

df.apply(lambda x: x.max() - x.min())

Element Wise Function Application: applymap()
The methods applymap() on dataframe and analogously map() on series accept any Python function. It takes a single value and returns a single value.

df7.applymap(lambda x:x*100)

25. Pandas GroupBy operations
A groupby operation involves one of the following operations on the original object. They are as follows :−

Splitting the Object
Applying a function
Combining the results
The split step is the most straightforward out of these. In many situations, we may wish to split the data set into groups and perform operations on those groups.

In the apply functionality, we can perform the following operations :−

Aggregation − compute a summary statistic (or statistics) for each group. Some examples are :-

Compute group sums or means.

Compute group sizes / counts.

Transformation − perform some group-specific computations and return a like-indexed object. Some examples are :-

Standardize data (zscore) within a group.

Filling NAs within groups with a value derived from each group.

Filtration − discarding the data with some condition. Some examples are :-

Discard data that belongs to groups with only a few members.

Filter out data based on the group sum or mean.

Some combination of the above: GroupBy will examine the results of the apply step and try to return a sensibly combined result if it doesn't fit into either of the above two categories.
Split Data into Groups
Pandas object can be split into any of their objects. There are multiple ways to split an object as follows :-

obj.groupby('key')
obj.groupby(['key1','key2'])
obj.groupby(key,axis=1)
The following example illustrates the idea:-

df8=df.copy()

df8.groupby('Gender')
<pandas.core.groupby.groupby.DataFrameGroupBy object at 0x00000088672ECFD0>
# view groups of Gender column

df8.groupby('Gender').groups
{'F': Int64Index([     0,      1,      2,      3,     14,     15,     16,     17,
                 29,     30,
             ...
             537467, 537468, 537469, 537470, 537471, 537472, 537473, 537474,
             537475, 537476],
            dtype='int64', length=132197),
 'M': Int64Index([     4,      5,      6,      7,      8,      9,     10,     11,
                 12,     13,
             ...
             537567, 537568, 537569, 537570, 537571, 537572, 537573, 537574,
             537575, 537576],
            dtype='int64', length=405380)}
Group by with multiple columns
df8.groupby(['Gender', 'Age']).groups

Iterate through groups
With the groupby object in hand, we can iterate through the object similar to itertools.obj.

df8_grouped = df8.groupby('Gender')

for Age, Occupation in df8_grouped:

print Age

print Occupation

Select a group with get_group() method
Using the get_group() method, we can select a single group.

df8_grouped = df8.groupby('City_Category')

print(df8_grouped.get_group('A')

Aggregation functions with groupby
An aggregation function returns a single aggregated value for each group. Once the group by object is created, several aggregation operations can be performed on the grouped data as follows:-

# apply aggregation function sum with groupby

df8.groupby('Gender').sum()
User_ID	Occupation	Marital_Status	Product_Category_1	Product_Category_2	Product_Category_3	Purchase
Gender							
F	132605172667	891361	55223	739701	1329034.0	1658809.0	1164624021
M	406580175483	3453718	164537	2107063	4005174.0	5149835.0	3853044357
# alternative way to apply aggregation function sum

df8.groupby('Gender').agg(np.sum)
User_ID	Occupation	Marital_Status	Product_Category_1	Product_Category_2	Product_Category_3	Purchase
Gender							
F	132605172667	891361	55223	739701	1329034.0	1658809.0	1164624021
M	406580175483	3453718	164537	2107063	4005174.0	5149835.0	3853044357
Another way to see the size of each group is by applying the size() function as follows:-

# attribute access in python pandas

df8_grouped = df8.groupby('Gender')

print(df8_grouped.agg(np.size))
        User_ID  Product_ID     Age  Occupation  City_Category  \
Gender                                                           
F        132197      132197  132197      132197         132197   
M        405380      405380  405380      405380         405380   

        Stay_In_Current_City_Years  Marital_Status  Product_Category_1  \
Gender                                                                   
F                           132197          132197              132197   
M                           405380          405380              405380   

        Product_Category_2  Product_Category_3  Purchase  
Gender                                                    
F                 132197.0            132197.0    132197  
M                 405380.0            405380.0    405380  
Applying multiple aggregation functions at once
With grouped Series, you can also pass a list or dict of functions to do aggregation with, and generate DataFrame as output as follows:-

df8.groupby('Gender')['Purchase'].agg([np.sum, np.mean])
sum	mean
Gender		
F	1164624021	8809.761349
M	3853044357	9504.771713
Transformations
Transformation on a group or a column returns an object that is indexed the same size of that is being grouped. Thus, the transform should return a result that is the same size as that of a group chunk.

df9=df.copy()


score = lambda x: (x - x.mean()) / x.std()*10


print(df9.groupby('Gender')['Purchase'].transform(score).head(5))
0    -0.931414
1    13.534512
2   -15.647263
3   -16.420332
4    -3.040496
Name: Purchase, dtype: float64
Filtration
Filtration filters the data on a defined criteria and returns the subset of data. The filter() function is used to filter the data.

df10=df.copy()


df10.groupby('Gender').filter(lambda x: len(x) > 4)
User_ID	Product_ID	Gender	Age	Occupation	City_Category	Stay_In_Current_City_Years	Marital_Status	Product_Category_1	Product_Category_2	Product_Category_3	Purchase
0	1000001	P00069042	F	0-17	10	A	2	0	3	6.0	14.0	8370
1	1000001	P00248942	F	0-17	10	A	2	0	1	6.0	14.0	15200
2	1000001	P00087842	F	0-17	10	A	2	0	12	6.0	14.0	1422
3	1000001	P00085442	F	0-17	10	A	2	0	12	14.0	14.0	1057
4	1000002	P00285442	M	55+	16	C	4+	0	8	14.0	14.0	7969
5	1000003	P00193542	M	26-35	15	A	3	0	1	2.0	14.0	15227
6	1000004	P00184942	M	46-50	7	B	2	1	1	8.0	17.0	19215
7	1000004	P00346142	M	46-50	7	B	2	1	1	15.0	17.0	15854
8	1000004	P0097242	M	46-50	7	B	2	1	1	16.0	17.0	15686
9	1000005	P00274942	M	26-35	20	A	1	1	8	16.0	17.0	7871
10	1000005	P00251242	M	26-35	20	A	1	1	5	11.0	17.0	5254
11	1000005	P00014542	M	26-35	20	A	1	1	8	11.0	17.0	3957
12	1000005	P00031342	M	26-35	20	A	1	1	8	11.0	17.0	6073
13	1000005	P00145042	M	26-35	20	A	1	1	1	2.0	5.0	15665
14	1000006	P00231342	F	51-55	9	A	1	0	5	8.0	14.0	5378
15	1000006	P00190242	F	51-55	9	A	1	0	4	5.0	14.0	2079
16	1000006	P0096642	F	51-55	9	A	1	0	2	3.0	4.0	13055
17	1000006	P00058442	F	51-55	9	A	1	0	5	14.0	4.0	8851
18	1000007	P00036842	M	36-45	1	B	1	1	1	14.0	16.0	11788
19	1000008	P00249542	M	26-35	12	C	4+	1	1	5.0	15.0	19614
20	1000008	P00220442	M	26-35	12	C	4+	1	5	14.0	15.0	8584
21	1000008	P00156442	M	26-35	12	C	4+	1	8	14.0	15.0	9872
22	1000008	P00213742	M	26-35	12	C	4+	1	8	14.0	15.0	9743
23	1000008	P00214442	M	26-35	12	C	4+	1	8	14.0	15.0	5982
24	1000008	P00303442	M	26-35	12	C	4+	1	1	8.0	14.0	11927
25	1000009	P00135742	M	26-35	17	C	0	0	6	8.0	14.0	16662
26	1000009	P00039942	M	26-35	17	C	0	0	8	8.0	14.0	5887
27	1000009	P00161442	M	26-35	17	C	0	0	5	14.0	14.0	6973
28	1000009	P00078742	M	26-35	17	C	0	0	5	8.0	14.0	5391
29	1000010	P00085942	F	36-45	1	B	4+	1	2	4.0	8.0	16352
...	...	...	...	...	...	...	...	...	...	...	...	...
537547	1004733	P00244042	M	18-25	18	C	1	0	1	2.0	15.0	11543
537548	1004734	P00111042	M	51-55	1	B	1	1	15	2.0	15.0	20924
537549	1004734	P00345842	M	51-55	1	B	1	1	2	8.0	14.0	13082
537550	1004735	P00278242	M	46-50	3	C	3	0	1	8.0	14.0	11658
537551	1004735	P00313442	M	46-50	3	C	3	0	5	6.0	8.0	6863
537552	1004735	P0098642	M	46-50	3	C	3	0	6	8.0	8.0	16415
537553	1004735	P00119342	M	46-50	3	C	3	0	10	13.0	8.0	18526
537554	1004735	P00114042	M	46-50	3	C	3	0	5	14.0	8.0	7099
537555	1004735	P00135142	M	46-50	3	C	3	0	13	16.0	8.0	578
537556	1004736	P00194542	M	18-25	20	A	1	1	8	14.0	8.0	2183
537557	1004736	P00175242	M	18-25	20	A	1	1	2	14.0	8.0	12724
537558	1004736	P00101942	M	18-25	20	A	1	1	8	17.0	8.0	7796
537559	1004736	P00109142	M	18-25	20	A	1	1	8	17.0	8.0	7770
537560	1004736	P00084842	M	18-25	20	A	1	1	8	16.0	8.0	5940
537561	1004736	P00078142	M	18-25	20	A	1	1	8	16.0	8.0	7834
537562	1004736	P00146742	M	18-25	20	A	1	1	1	13.0	14.0	11508
537563	1004736	P00154642	M	18-25	20	A	1	1	8	13.0	14.0	6074
537564	1004736	P00117442	M	18-25	20	A	1	1	5	14.0	14.0	7084
537565	1004736	P00051142	M	18-25	20	A	1	1	8	14.0	14.0	7934
537566	1004736	P00048742	M	18-25	20	A	1	1	5	14.0	14.0	5350
537567	1004736	P00157542	M	18-25	20	A	1	1	8	14.0	14.0	1994
537568	1004736	P00250642	M	18-25	20	A	1	1	11	14.0	14.0	5930
537569	1004736	P00023142	M	18-25	20	A	1	1	5	14.0	14.0	7042
537570	1004736	P00162442	M	18-25	20	A	1	1	1	16.0	14.0	15491
537571	1004737	P00221442	M	36-45	16	C	1	0	1	2.0	5.0	11852
537572	1004737	P00193542	M	36-45	16	C	1	0	1	2.0	5.0	11664
537573	1004737	P00111142	M	36-45	16	C	1	0	1	15.0	16.0	19196
537574	1004737	P00345942	M	36-45	16	C	1	0	8	15.0	16.0	8043
537575	1004737	P00285842	M	36-45	16	C	1	0	5	15.0	16.0	7172
537576	1004737	P00118242	M	36-45	16	C	1	0	5	8.0	16.0	6875
537577 rows × 12 columns

26. Pandas merging and joining
Pandas has full-featured, high performance in-memory join operations that are very similar to relational databases like SQL. These methods perform significantly better than other open source implementations like base::merge.data.frame in R. The reason for this is careful algorithmic design and the internal layout of the data in DataFrame.

Pandas provides a single function, merge, as the entry point for all standard database join operations between DataFrame objects.

The syntax of the merge function is as follows:-

pd.merge(left, right, how='inner', on=None, left_on=None, right_on=None, left_index=False, right_index=False, sort=True)

The description of the parameters used is as follows−

left − A DataFrame object.
right − Another DataFrame object.
on − Columns (names) to join on. Must be found in both the left and right DataFrame objects.
left_on − Columns from the left DataFrame to use as keys. Can either be column names or arrays with length equal to the length of the DataFrame.
right_on − Columns from the right DataFrame to use as keys. Can either be column names or arrays with length equal to the length of the DataFrame.
left_index − If True, use the index (row labels) from the left DataFrame as its join key(s). In case of a DataFrame with a MultiIndex (hierarchical), the number of levels must match the number of join keys from the right DataFrame.
right_index − Same usage as left_index for the right DataFrame.
how − One of 'left', 'right', 'outer', 'inner'. Defaults to inner.
sort − Sort the result DataFrame by the join keys in lexicographical order. Defaults to True, setting to False will improve the performance substantially in many cases.
Now, I will create two different DataFrames and perform the merging operations on them as follows:-

# let's create two dataframes

batsmen = pd.DataFrame({
   'id':[1,2,3,4,5],
   'Name': ['Rohit', 'Dhawan', 'Virat', 'Dhoni', 'Kedar'],
   'subject_id':['sub1','sub2','sub4','sub6','sub5']})

bowler = pd.DataFrame(
   {'id':[1,2,3,4,5],
   'Name': ['Kumar', 'Bumrah', 'Shami', 'Kuldeep', 'Chahal'],
   'subject_id':['sub2','sub4','sub3','sub6','sub5']})


print(batsmen)


print(bowler)
   id    Name subject_id
0   1   Rohit       sub1
1   2  Dhawan       sub2
2   3   Virat       sub4
3   4   Dhoni       sub6
4   5   Kedar       sub5
   id     Name subject_id
0   1    Kumar       sub2
1   2   Bumrah       sub4
2   3    Shami       sub3
3   4  Kuldeep       sub6
4   5   Chahal       sub5
# merge two dataframes on a key

pd.merge(batsmen, bowler, on='id')
id	Name_x	subject_id_x	Name_y	subject_id_y
0	1	Rohit	sub1	Kumar	sub2
1	2	Dhawan	sub2	Bumrah	sub4
2	3	Virat	sub4	Shami	sub3
3	4	Dhoni	sub6	Kuldeep	sub6
4	5	Kedar	sub5	Chahal	sub5
# merge two dataframes on multiple keys

pd.merge(batsmen, bowler, on=['id', 'subject_id'])
id	Name_x	subject_id	Name_y
0	4	Dhoni	sub6	Kuldeep
1	5	Kedar	sub5	Chahal
Merge using 'how' argument
The how argument to merge specifies how to determine which keys are to be included in the resulting table. If a key combination does not appear in either the left or the right tables, the values in the joined table will be NA.

Here is a summary of the how options and their SQL equivalent names −

Merge Method - SQL Equivalent - Description
left - LEFT OUTER JOIN - Use keys from left object
right - RIGHT OUTER JOIN - Use keys from right object
outer - FULL OUTER JOIN - Use union of keys
inner - INNER JOIN - Use intersection of keys
# left join

pd.merge(batsmen, bowler, on='subject_id', how='left')
id_x	Name_x	subject_id	id_y	Name_y
0	1	Rohit	sub1	NaN	NaN
1	2	Dhawan	sub2	1.0	Kumar
2	3	Virat	sub4	2.0	Bumrah
3	4	Dhoni	sub6	4.0	Kuldeep
4	5	Kedar	sub5	5.0	Chahal
# right join

pd.merge(batsmen, bowler, on='subject_id', how='right')
id_x	Name_x	subject_id	id_y	Name_y
0	2.0	Dhawan	sub2	1	Kumar
1	3.0	Virat	sub4	2	Bumrah
2	4.0	Dhoni	sub6	4	Kuldeep
3	5.0	Kedar	sub5	5	Chahal
4	NaN	NaN	sub3	3	Shami
# outer join

pd.merge(batsmen, bowler, on='subject_id', how='outer')
id_x	Name_x	subject_id	id_y	Name_y
0	1.0	Rohit	sub1	NaN	NaN
1	2.0	Dhawan	sub2	1.0	Kumar
2	3.0	Virat	sub4	2.0	Bumrah
3	4.0	Dhoni	sub6	4.0	Kuldeep
4	5.0	Kedar	sub5	5.0	Chahal
5	NaN	NaN	sub3	3.0	Shami
# inner join

pd.merge(batsmen, bowler, on='subject_id', how='inner')
id_x	Name_x	subject_id	id_y	Name_y
0	2	Dhawan	sub2	1	Kumar
1	3	Virat	sub4	2	Bumrah
2	4	Dhoni	sub6	4	Kuldeep
3	5	Kedar	sub5	5	Chahal
27. Pandas concatenation operation
Pandas provides various facilities for easily combining together Series, DataFrame, and Panel objects.

The concat() function does all of the heavy lifting of performing concatenation operations along an axis while performing optional set logic (union or intersection) of the indexes (if any) on the other axes.

The syntax of the concat() function is as follows:-

pd.concat(objs, axis=0, join='outer', join_axes=None, ignore_index=False, keys=None, levels=None, names=None, verify_integrity=False, copy=True)

The description of the arguments is as follows:-

objs − This is a sequence or mapping of Series, DataFrame, or Panel objects.
axis − {0, 1, ...}, default 0. This is the axis to concatenate along.
join − {'inner', 'outer'}, default 'outer'. How to handle indexes on other axis(es). Outer for union and inner for intersection.
ignore_index − boolean, default False. If True, do not use the index values on the concatenation axis. The resulting axis will be labeled 0, ..., n - 1.
join_axes − This is the list of index objects. Specific indexes to use for the other (n-1) axes instead of performing inner/outer set logic.
keys : sequence, default None. Construct hierarchical index using the passed keys as the outermost level. If multiple levels passed, should contain tuples.
levels : list of sequences, default None. Specific levels (unique values) to use for constructing a MultiIndex. Otherwise they will be inferred from the keys.
names : list, default None. Names for the levels in the resulting hierarchical index.
verify_integrity : boolean, default False. Check whether the new concatenated axis contains duplicates. This can be very expensive relative to the actual data concatenation.
copy : boolean, default True. If False, do not copy data unnecessarily.
Now, I will create two dataframes and do concatenation:-

# let's create two dataframes

batsmen = pd.DataFrame({
   'id':[1,2,3,4,5],
   'Name': ['Rohit', 'Dhawan', 'Virat', 'Dhoni', 'Kedar'],
   'subject_id':['sub1','sub2','sub4','sub6','sub5']})

bowler = pd.DataFrame(
   {'id':[1,2,3,4,5],
   'Name': ['Kumar', 'Bumrah', 'Shami', 'Kuldeep', 'Chahal'],
   'subject_id':['sub2','sub4','sub3','sub6','sub5']})


print(batsmen)


print(bowler)
   id    Name subject_id
0   1   Rohit       sub1
1   2  Dhawan       sub2
2   3   Virat       sub4
3   4   Dhoni       sub6
4   5   Kedar       sub5
   id     Name subject_id
0   1    Kumar       sub2
1   2   Bumrah       sub4
2   3    Shami       sub3
3   4  Kuldeep       sub6
4   5   Chahal       sub5
# concatenate the dataframes


team=[batsmen, bowler]

pd.concat(team)
id	Name	subject_id
0	1	Rohit	sub1
1	2	Dhawan	sub2
2	3	Virat	sub4
3	4	Dhoni	sub6
4	5	Kedar	sub5
0	1	Kumar	sub2
1	2	Bumrah	sub4
2	3	Shami	sub3
3	4	Kuldeep	sub6
4	5	Chahal	sub5
# associate keys with the dataframes

pd.concat(team, keys=['x', 'y'])
id	Name	subject_id
x	0	1	Rohit	sub1
1	2	Dhawan	sub2
2	3	Virat	sub4
3	4	Dhoni	sub6
4	5	Kedar	sub5
y	0	1	Kumar	sub2
1	2	Bumrah	sub4
2	3	Shami	sub3
3	4	Kuldeep	sub6
4	5	Chahal	sub5
We can see the index of the resultant dataframe is duplicated. So each index is repeated.

If the resultant object has to follow its own indexing, we can set ignore_index option to True as follows:-

pd.concat(team, keys=['x', 'y'], ignore_index=True)
id	Name	subject_id
0	1	Rohit	sub1
1	2	Dhawan	sub2
2	3	Virat	sub4
3	4	Dhoni	sub6
4	5	Kedar	sub5
5	1	Kumar	sub2
6	2	Bumrah	sub4
7	3	Shami	sub3
8	4	Kuldeep	sub6
9	5	Chahal	sub5
We can see that the index changes completely and the Keys are also overridden.

If two objects need to be added along axis=1, then the new columns will be appended as follows:-

pd.concat(team, axis=1)
id	Name	subject_id	id	Name	subject_id
0	1	Rohit	sub1	1	Kumar	sub2
1	2	Dhawan	sub2	2	Bumrah	sub4
2	3	Virat	sub4	3	Shami	sub3
3	4	Dhoni	sub6	4	Kuldeep	sub6
4	5	Kedar	sub5	5	Chahal	sub5
Concatenating using append
A useful shortcut to concat are the append instance methods on Series and DataFrame. These methods actually predated concat. They concatenate along axis=0, namely the index as follows:−

batsmen.append(bowler)
id	Name	subject_id
0	1	Rohit	sub1
1	2	Dhawan	sub2
2	3	Virat	sub4
3	4	Dhoni	sub6
4	5	Kedar	sub5
0	1	Kumar	sub2
1	2	Bumrah	sub4
2	3	Shami	sub3
3	4	Kuldeep	sub6
4	5	Chahal	sub5
28. Reshaping by melt and pivot
Melt creates wide-to-long format dataframe
When we take a closer look at our original dataframe, we can see that our dataset is not in the tidy data format.

The columns Product_Category_1, Product_Category_2 and Product_Category_3 contain values of product_category rather than variables. We should reorganize our dataframe into tidy data format.

The melt() function is useful to convert a DataFrame from wide-to-long format where one or more columns are identifier variables, while all other columns are considered measured variables. The measured variables are then "unpivoted" to the row axis, leaving non-identifier columns, "variable" and "value". The names of those columns can be customized by supplying the var_name and value_name parameters.

We can convert our dataset into long data format using the melt() function as follows:-

df11=df.copy()

df11.columns
Index(['User_ID', 'Product_ID', 'Gender', 'Age', 'Occupation', 'City_Category',
       'Stay_In_Current_City_Years', 'Marital_Status', 'Product_Category_1',
       'Product_Category_2', 'Product_Category_3', 'Purchase'],
      dtype='object')
df12=(pd.melt(frame=df11, id_vars=['User_ID','Product_ID', 'Gender','Age','Occupation','City_Category',
                             'Marital_Status','Purchase'],                          
                    value_vars=['Product_Category_1','Product_Category_2','Product_Category_3'], 
                    var_name='Product_Category', value_name='Amount'))

df12.head(10)
User_ID	Product_ID	Gender	Age	Occupation	City_Category	Marital_Status	Purchase	Product_Category	Amount
0	1000001	P00069042	F	0-17	10	A	0	8370	Product_Category_1	3.0
1	1000001	P00248942	F	0-17	10	A	0	15200	Product_Category_1	1.0
2	1000001	P00087842	F	0-17	10	A	0	1422	Product_Category_1	12.0
3	1000001	P00085442	F	0-17	10	A	0	1057	Product_Category_1	12.0
4	1000002	P00285442	M	55+	16	C	0	7969	Product_Category_1	8.0
5	1000003	P00193542	M	26-35	15	A	0	15227	Product_Category_1	1.0
6	1000004	P00184942	M	46-50	7	B	1	19215	Product_Category_1	1.0
7	1000004	P00346142	M	46-50	7	B	1	15854	Product_Category_1	1.0
8	1000004	P0097242	M	46-50	7	B	1	15686	Product_Category_1	1.0
9	1000005	P00274942	M	26-35	20	A	1	7871	Product_Category_1	8.0
Pivot creates long-to-wide format dataframe
I have melt three columns Product_Category_1, Product_Category_2 and Product_Category_3 into a single column named Product_Category with melt() function. So, I have converted the above dataframe from wide to long format.

Now, I will convert the above column Product_Category from long to wide format with pivot() function. pivot() function takes 3 arguments with the following names - index, columns, and values. As a value for each of these parameters we need to specify a column name in the original table. Then the pivot() function will create a new table, whose row and column indices are the unique values of the respective parameters. The cell values of the new table are taken from column given as the values parameter.

This is illustrated below:-

df13=df12[['Product_Category', 'Amount']]

df14=df13.pivot(index=None, columns='Product_Category', values='Amount')

df14.head(25)
Product_Category	Product_Category_1	Product_Category_2	Product_Category_3
0	3.0	NaN	NaN
1	1.0	NaN	NaN
2	12.0	NaN	NaN
3	12.0	NaN	NaN
4	8.0	NaN	NaN
5	1.0	NaN	NaN
6	1.0	NaN	NaN
7	1.0	NaN	NaN
8	1.0	NaN	NaN
9	8.0	NaN	NaN
10	5.0	NaN	NaN
11	8.0	NaN	NaN
12	8.0	NaN	NaN
13	1.0	NaN	NaN
14	5.0	NaN	NaN
15	4.0	NaN	NaN
16	2.0	NaN	NaN
17	5.0	NaN	NaN
18	1.0	NaN	NaN
19	1.0	NaN	NaN
20	5.0	NaN	NaN
21	8.0	NaN	NaN
22	8.0	NaN	NaN
23	8.0	NaN	NaN
24	1.0	NaN	NaN
Reshaping with pivot_table function
Before calling the pivot() function, we need to ensure that our dataset does not have rows with duplicate values for the specified columns. If there are duplicate entries for rows in the dataset, the pivot() function, will throw a value error.

In this case, the pivot_table() method comes to rescue. It works like pivot, but it aggregates the values from rows with duplicate entries for the specified columns. The syntax of the pivot_table() function is given below:-

df.pivot_table(values=None, index=None, columns=None, aggfunc='mean', fill_value=None, 
margins=False, dropna=True, margins_name='All')

29. Reshaping by stacking and unstacking
There are two other methods called stack() and unstack() which closely resemble the pivot() method. These methods are designed to work together with multiindex objects. The functionality of these methods is described below:-

Stacking
Stacking means "pivot" a level of the (possibly hierarchical) column labels, returning a DataFrame with an index with a new inner-most level of row labels. So. stacking a dataframe means moving or pivoting the innermost column index to become the innermost row index.

It return a reshaped dataframe or series having a multi-level index with one or more new inner-most levels compared to the current dataframe. The new inner-most levels are created by pivoting the columns of the current dataframe.

if the columns have a single level, the output is a Series.
if the columns have multiple levels, the new index level(s) is (are) taken from the prescribed level(s) and the output is a DataFrame.
In this case, we look at a dataframe with single level hierarchical indices on both axes. Stacking takes the most-inner column index (height, weight), makes it the most inner row index and reshuffles the cell values accordingly.

cols=pd.MultiIndex.from_tuples([('weight', 'kg'), ('weight', 'pounds')])

df15=pd.DataFrame([[75,165], [60, 132]],
                 index=['husband', 'wife'],
                 columns=cols)

df15
weight
kg	pounds
husband	75	165
wife	60	132
df16=df15.stack()

df16
weight
husband	kg	75
pounds	165
wife	kg	60
pounds	132
Unstacking
It is the inverse operation of stacking. It means "pivot" a level of the (possibly hierarchical) row index to the column axis, producing a reshaped dataframe with a new inner-most level of column labels.

I will convert the stacked dataframe df16 back to original form as follows:-

df16.unstack()
weight
kg	pounds
husband	75	165
wife	60	132
30. Options and customization with pandas
Pandas provide API to customize some aspects of its behavior. In most cases, we would like to adjust the display related options.

The API is composed of five relevant functions. They are as follows :−

get_option()
set_option()
reset_option()
describe_option()
option_context()
Let us now understand how the functions operate.

1. get_option(param)
get_option() takes a single parameter and returns the value as given in the output below −

# display maximum rows

pd.get_option("display.max_rows")
60
# display maximum columns

pd.get_option("display.max_columns")
20
2. set_option(param,value)
set_option() takes two arguments and sets the value to the parameter as shown below −

# set maximum rows

pd.set_option("display.max_rows", 80)

pd.get_option("display.max_rows")
80
# set maximum columns

pd.set_option("display.max_columns", 30)

pd.get_option("display.max_columns")
30
3. reset_option(param)
reset_option() takes an argument and sets the value back to the default value.

# display maximum rows

pd.reset_option("display.max_rows")

pd.get_option("display.max_rows")
60
# display maximum columns

pd.reset_option("display.max_columns")

pd.get_option("display.max_columns")
20
4. describe_option(param)
describe_option() prints the description of the argument.

# description of the display maximum rows parameter

pd.describe_option("display.max_rows")
display.max_rows : int
    If max_rows is exceeded, switch to truncate view. Depending on
    `large_repr`, objects are either centrally truncated or printed as
    a summary view. 'None' value means unlimited.

    In case python/IPython is running in a terminal and `large_repr`
    equals 'truncate' this can be set to 0 and pandas will auto-detect
    the height of the terminal and print a truncated object which fits
    the screen height. The IPython notebook, IPython qtconsole, or
    IDLE do not run in a terminal and hence it is not possible to do
    correct auto-detection.
    [default: 60] [currently: 60]


5. option_context()
option_context() context manager is used to set the option in with statement temporarily. Option values are restored automatically when you exit with block.

# set the parameter value with option_context

with pd.option_context("display.max_rows",10):
   print(pd.get_option("display.max_rows"))
   print(pd.get_option("display.max_rows"))
10
10
There is a difference between the first and the second print statements. The first statement prints the value set by option_context() which is temporary within the with context itself. After the with context, the second print statement prints the configured value.

This concludes our discussion on Pandas and its data analysis tools.

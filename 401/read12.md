
# Pandas 

## Pandas in 10 

* Customarily, we import as follows: 

      import pandas as pd

### Object creation

*Creating a Series by passing a list of values, letting pandas create a default integer index:* 

        In [3]: s = pd.Series([1, 3, 5, np.nan, 6, 8])

        In [4]: s
        Out[4]: 
        0    1.0
        1    3.0
        2    5.0
        3    NaN
        4    6.0
        5    8.0
        dtype: float64

*Creating a DataFrame by passing a NumPy array, with a datetime index and labeled columns:* 

        In [5]: dates = pd.date_range("20130101", periods=6)

        In [6]: dates
        Out[6]: 
        DatetimeIndex(['2013-01-01', '2013-01-02', '2013-01-03', '2013-01-04',
                    '2013-01-05', '2013-01-06'],
                    dtype='datetime64[ns]', freq='D')

        In [7]: df = pd.DataFrame(np.random.randn(6, 4), index=dates, columns=list("ABCD"))

        In [8]: df
        Out[8]: 
                        A         B         C         D
        2013-01-01  0.469112 -0.282863 -1.509059 -1.135632
        2013-01-02  1.212112 -0.173215  0.119209 -1.044236
        2013-01-03 -0.861849 -2.104569 -0.494929  1.071804
        2013-01-04  0.721555 -0.706771 -1.039575  0.271860
        2013-01-05 -0.424972  0.567020  0.276232 -1.087401
        2013-01-06 -0.673690  0.113648 -1.478427  0.524988

*Creating a DataFrame by passing a dict of objects that can be converted to series-like.* 

        In [9]: df2 = pd.DataFrame(
        ...:     {
        ...:         "A": 1.0,
        ...:         "B": pd.Timestamp("20130102"),
        ...:         "C": pd.Series(1, index=list(range(4)), dtype="float32"),
        ...:         "D": np.array([3] * 4, dtype="int32"),
        ...:         "E": pd.Categorical(["test", "train", "test", "train"]),
        ...:         "F": "foo",
        ...:     }
        ...: )
        ...: 

        In [10]: df2
        Out[10]: 
            A          B    C  D      E    F
        0  1.0 2013-01-02  1.0  3   test  foo
        1  1.0 2013-01-02  1.0  3  train  foo
        2  1.0 2013-01-02  1.0  3   test  foo
        3  1.0 2013-01-02  1.0  3  train  foo 

### Viewing data 

*Here is how to view the top and bottom rows of the frame:* 

        In [13]: df.head()
        Out[13]: 
                        A         B         C         D
        2013-01-01  0.469112 -0.282863 -1.509059 -1.135632
        2013-01-02  1.212112 -0.173215  0.119209 -1.044236
        2013-01-03 -0.861849 -2.104569 -0.494929  1.071804
        2013-01-04  0.721555 -0.706771 -1.039575  0.271860
        2013-01-05 -0.424972  0.567020  0.276232 -1.087401

        In [14]: df.tail(3)
        Out[14]: 
                        A         B         C         D
        2013-01-04  0.721555 -0.706771 -1.039575  0.271860
        2013-01-05 -0.424972  0.567020  0.276232 -1.087401
        2013-01-06 -0.673690  0.113648 -1.478427  0.524988 

### Setting 

*Setting a new column automatically aligns the data by the indexes.* 

### Missing data 

*pandas primarily uses the value np.nan to represent missing data. It is by default not included in computations.* 

*Reindexing allows you to change/add/delete the index on a specified axis. This returns a copy of the data.* 

        In [55]: df1 = df.reindex(index=dates[0:4], columns=list(df.columns) + ["E"])

        In [56]: df1.loc[dates[0] : dates[1], "E"] = 1

        In [57]: df1
        Out[57]: 
                        A         B         C  D    F    E
        2013-01-01  0.000000  0.000000 -1.509059  5  NaN  1.0
        2013-01-02  1.212112 -0.173215  0.119209  5  1.0  1.0
        2013-01-03 -0.861849 -2.104569 -0.494929  5  2.0  NaN
        2013-01-04  0.721555 -0.706771 -1.039575  5  3.0  NaN

### Time series 

*pandas has simple, powerful, and efficient functionality for performing resampling operations during frequency conversion. This is extremely common in, but not limited to, financial applications.* 

### Categoricals 

*pandas can include categorical data in a DataFrame.* 



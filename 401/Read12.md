# 10 minutes to pandas

## Object creation

See the Data Structure Intro section.

Creating a Series by passing a list of values, letting pandas create a default integer index:

    s = pd.Series([1, 3, 5, np.nan, 6, 8])

    s
    Out[4]: 
    0    1.0
    1    3.0
    2    5.0
    3    NaN
    4    6.0
    5    8.0
    dtype: float64

## Viewing data

See the Basics section.

Here is how to view the top and bottom rows of the frame:

    df.head()
    Out[13]: 
                    A         B         C         D
    2013-01-01  0.469112 -0.282863 -1.509059 -1.135632
    2013-01-02  1.212112 -0.173215  0.119209 -1.044236
    2013-01-03 -0.861849 -2.104569 -0.494929  1.071804
    2013-01-04  0.721555 -0.706771 -1.039575  0.271860
    2013-01-05 -0.424972  0.567020  0.276232 -1.087401

    df.tail(3)
    Out[14]: 
                    A         B         C         D
    2013-01-04  0.721555 -0.706771 -1.039575  0.271860
    2013-01-05 -0.424972  0.567020  0.276232 -1.087401
    2013-01-06 -0.673690  0.113648 -1.478427  0.524988

## Getting

Selecting a single column, which yields a Series, equivalent to df.A:

    df["A"]
    Out[23]: 
    2013-01-01    0.469112
    2013-01-02    1.212112
    2013-01-03   -0.861849
    2013-01-04    0.721555
    2013-01-05   -0.424972
    2013-01-06   -0.673690
    Freq: D, Name: A, dtype: float64

Selecting via [], which slices the rows.

    df[0:3]
    Out[24]: 
                    A         B         C         D
    2013-01-01  0.469112 -0.282863 -1.509059 -1.135632
    2013-01-02  1.212112 -0.173215  0.119209 -1.044236
    2013-01-03 -0.861849 -2.104569 -0.494929  1.071804

    df["20130102":"20130104"]
    Out[25]: 
                    A         B         C         D
    2013-01-02  1.212112 -0.173215  0.119209 -1.044236
    2013-01-03 -0.861849 -2.104569 -0.494929  1.071804
    2013-01-04  0.721555 -0.706771 -1.039575  0.271860

## Selection by label

See more in Selection by Label.

For getting a cross section using a label:

    df.loc[dates[0]]
    Out[26]: 
    A    0.469112
    B   -0.282863
    C   -1.509059
    D   -1.135632
    Name: 2013-01-01 00:00:00, dtype: float64

Selecting on a multi-axis by label:

    df.loc[:, ["A", "B"]]
    Out[27]: 
                        A         B
        2013-01-01  0.469112 -0.282863
        2013-01-02  1.212112 -0.173215
        2013-01-03 -0.861849 -2.104569
        2013-01-04  0.721555 -0.706771
        2013-01-05 -0.424972  0.567020
        2013-01-06 -0.673690  0.113648

## Selection by position

See more in Selection by Position.

Select via the position of the passed integers:

    df.iloc[3]
    Out[32]: 
    A    0.721555
    B   -0.706771
    C   -1.039575
    D    0.271860
    Name: 2013-01-04 00:00:00, dtype: float64

By integer slices, acting similar to NumPy/Python:

    df.iloc[3:5, 0:2]
    Out[33]: 
                    A         B
    2013-01-04  0.721555 -0.706771
    2013-01-05 -0.424972  0.567020

## Boolean indexing

Using a single column’s values to select data.

    df[df["A"] > 0]
    Out[39]: 
                    A         B         C         D
    2013-01-01  0.469112 -0.282863 -1.509059 -1.135632
    2013-01-02  1.212112 -0.173215  0.119209 -1.044236
    2013-01-04  0.721555 -0.706771 -1.039575  0.271860

Selecting values from a DataFrame where a boolean condition is met.

    df[df > 0]
    Out[40]: 
                    A         B         C         D
    2013-01-01  0.469112       NaN       NaN       NaN
    2013-01-02  1.212112       NaN  0.119209       NaN
    2013-01-03       NaN       NaN       NaN  1.071804
    2013-01-04  0.721555       NaN       NaN  0.271860
    2013-01-05       NaN  0.567020  0.276232       NaN
    2013-01-06       NaN  0.113648       NaN  0.524988

## Missing data

pandas primarily uses the value np.nan to represent missing data. It is by default not included in computations. See the Missing Data section.

Reindexing allows you to change/add/delete the index on a specified axis. This returns a copy of the data.

    df1 = df.reindex(index=dates[0:4], columns=list(df.columns) + ["E"])

    df1.loc[dates[0] : dates[1], "E"] = 1

    df1
    Out[57]: 
                    A         B         C  D    F    E
    2013-01-01  0.000000  0.000000 -1.509059  5  NaN  1.0
    2013-01-02  1.212112 -0.173215  0.119209  5  1.0  1.0
    2013-01-03 -0.861849 -2.104569 -0.494929  5  2.0  NaN
    2013-01-04  0.721555 -0.706771 -1.039575  5  3.0  NaN

To drop any rows that have missing data.

    df1.dropna(how="any")
    Out[58]: 
                    A         B         C  D    F    E
    2013-01-02  1.212112 -0.173215  0.119209  5  1.0  1.0

## Stack

tuples = list(

    zip(

        *[

            ["bar", "bar", "baz", "baz", "foo", "foo", "qux", "qux"],

            ["one", "two", "one", "two", "one", "two", "one", "two"],

        ]

    )

    )



    index = pd.MultiIndex.from_tuples(tuples, names=["first", "second"])

    df = pd.DataFrame(np.random.randn(8, 2), index=index, columns=["A", "B"])

    df2 = df[:4]

    df2
    Out[95]: 
                        A         B
    first second                    
    bar   one    -0.727965 -0.589346
        two     0.339969 -0.693205
    baz   one    -0.339355  0.593616
        two     0.884345  1.591431

The stack() method “compresses” a level in the DataFrame’s columns.

    stacked = df2.stack()

    stacked
    Out[97]: 
    first  second   
    bar    one     A   -0.727965
                B   -0.589346
        two     A    0.339969
                B   -0.693205
    baz    one     A   -0.339355
                B    0.593616
        two     A    0.884345
                B    1.591431
    dtype: float64

## Pivot tables

See the section on Pivot Tables.

df = pd.DataFrame(

    {

        "A": ["one", "one", "two", "three"] * 3,

        "B": ["A", "B", "C"] * 4,

        "C": ["foo", "foo", "foo", "bar", "bar", "bar"] * 2,

        "D": np.random.randn(12),

        "E": np.random.randn(12),

    }

    )



    df
    Out[102]: 
            A  B    C         D         E
    0     one  A  foo -1.202872  0.047609
    1     one  B  foo -1.814470 -0.136473
    2     two  C  foo  1.018601 -0.561757
    3   three  A  bar -0.595447 -1.623033
    4     one  B  bar  1.395433  0.029399
    5     one  C  bar -0.392670 -0.542108
    6     two  A  foo  0.007207  0.282696
    7   three  B  foo  1.928123 -0.087302
    8     one  C  foo -0.055224 -1.575170
    9     one  A  bar  2.395985  1.771208
    10    two  B  bar  1.552825  0.816482
    11  three  C  bar  0.166599  1.100230

## Plotting

See the Plotting docs.

We use the standard convention for referencing the matplotlib API:

    import matplotlib.pyplot as plt

    plt.close("all")

The close() method is used to close a figure window.

    ts = pd.Series(np.random.randn(1000), index=pd.date_range("1/1/2000", periods=1000))

    ts = ts.cumsum()

    ts.plot();

![PLOT](https://pandas.pydata.org/pandas-docs/stable/_images/series_plot_basic.png)

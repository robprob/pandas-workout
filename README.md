# Pandas Workout (my solutions)
<i>Pandas Workout</i> by Reuven Lerner contains over 200 data analytics exercises based around the Python library, pandas. It has been a phenomenal resources to helping me both demonstrate and improve my data processing and analytical skills. Starting from the bottom up to more advanced topics, I completed every exercise in this >400 page book.

# My focus
While completing this book, I focused on finding unique or more efficient solutions that helped deepen my technical knowledge of the pandas library. I also corrected several minor errors from the author, mostly unintended behavior from potentially overlooked nuances.

For example, in Exercise 13, header=None is not used when reading in the nyc-temps.txt file, causing a row of data to be lost. In Exercise 30, pd.cut() cannot be used to categorize trip length, as it was specified that the "medium" category should be inclusive at both ends. I instead chose to create a function that correctly categorized the series using the .apply() method.

# What I learned
As previously stated, this book was incredibly helpful in improving my pandas skillset. Here are some of my biggest takeaways:
### General Data Wrangling
- Because it takes a slice of the column, .loc cannot be used to change the data type of a column, although it throws an error when attempting to do so without .loc.
- Join defaults 'left', merge defaults 'inner'.
- Renaming with 'df.columns = []' should be avoided, as this can rename them in the wrong order. Use' df.rename(columns={})' instead.
- lambda functions can be used in chained transformations and .loc accessors to input previous output instead of retyping.
### Time Series Analysis
- Setting a DatetimeIndex makes searching much more flexible, allowing use of df.resample('1D').mean() while taking advantage of a wide variety of attributes and methods, such as df.index.is_quarter_end. Additionally, using df.assign(day=df.index.day_name) with an advanced query/visualizaiton is helpful to benefit from the .loc features of the index while also being able to group by attribute.
### Visualization
- When using Seaborn to plot after .groupby(), selecting a single output column plots all groups on the same graph. If multiple output columns are selected, groups will be plotted separately.
### Memory and Performance
- There are many ways to easily save large amounts of memory while ensuring data is not lost. These include using pd.to_numeric() with the 'downcast' keyword, changing to a categorical dtype, or loading rows in smaller chunks to get a better idea of how to efficiently handle a large dataset. '(df.count() / df.nunique()).sort_values(ascending=False)' is helpful in determining which columns would benefit most from conversion to categorical data type.
- .isin() is incredibly powerful and efficient, even when only 1 value is used in the list.
- df.query() can become much more efficient in certain scenarios, particularly large datasets, and was worth becoming more comfortable with, similar to feather files and pyarrow as a deserialization engine/backend data type.

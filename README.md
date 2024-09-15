# Pandas Workout (my solutions)
<i>Pandas Workout</i> by Reuven Lerner contains over 200 data analytics exercises based around the Python library, pandas. It has been a phenomenal resources to helping me both demonstrate and improve my data processing and analytical skills. Starting from the bottom up to more advanced topics, I completed every exercise in this >400 page book.

# My focus
While completing this book, I focused on finding unique or efficient solutions that helped deepen my technical knowledge of the pandas library. I also corrected several minor errors from the author, such as incorrect methods of categorization or unintended behavior from overlooking nuances.

For example, in Exercise 13, header=None is not used when reading in the nyc-temps.txt file, causing a row of data to be lost. In Exercise 30, pd.cut() cannot be used to categorize trip length, as it was specified that the "medium" category should be inclusive at both ends. I instead chose to create a function that correctly categorized the series using the .apply() method.

# My biggest takeaways

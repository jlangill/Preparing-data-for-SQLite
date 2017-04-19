# Preparing-data-for-SQLite
Import CSV, clean data, upload to SQLite

Instructions
Import pandas and read the CSV file academy_awards.csv into a Dataframe using the read_csv method.
When reading the CSV, make sure to set the encoding to ISO-8859-1 so it can be parsed properly.
Start exploring the data in Pandas and look for data quality issues.
Use the head method to explore the first few rows in the Dataframe.
There are 6 unnamed columns at the end. Use the value_countsmethod to explore if any of them have valid values that we need.
You'll notice that the Additional Info column contains a few different formatting styles. Start brainstorming ways to clean this column up.
Before we filter the data, let's clean up the Year column by selecting just the first 4 digits in each value in the column, therefore excluding the value in parentheses:
Use Pandas vectorized string methods to select just the first 4 elements in each string.
E.g. df["Year"].str[0:2] returns a Series containing just the first 2 characters for each element in the Yearcolumn.
Assign this new Series to the Year column to overwrite the original column.
Convert the Year column to the int64 data type using astype. Make sure to reassign the integer Series object back to the Yearcolumn in the Dataframe or the changes won't be reflected.
Use conditional filtering to select only the rows from the Dataframe where the Year column is larger than 2000. Assign the new filtered Dataframe to later_than_2000.
Use conditional filtering to select only the rows from later_than_2000 where the Category matches one of the 4 awards we're interested in.
Create a list of strings named award_categories with the following strings:
Actor -- Leading Role
Actor -- Supporting Role
Actress -- Leading Role
Actress -- Supporting Role
Use the isin method in the conditional filter to return all rows in a column that match any of the values in a list of strings.
Pass in award_categories to the isin method to return all rows : later_than_2000[later_than_2000["Category"].isin(award_categories)]
Assign the resulting Dataframe to nominations.
Use the Series method map to replace all NO values with 0 and all YESvalues with 1.
Select the Won? column from nominations.
Then create a dictionary where each key is a value we want to replace and each value is the corresponding replacement value.
The following dictionary replace_dict = { True: 1, False: 0 } would replace all True values with 1 and all False values with 0.
Call the map function on the Series object and pass in the dictionary you created.
Finally, reassign the new Series object to the Won? column in nominations.
Create a new column Won that contains the values from the Won?column.
Select the Won? column and assign it to the Won column. Both columns should be in the Dataframe still.
Use the drop method to remove the extraneous columns.
As the required parameter, pass in a list of strings containing the following values:
Won?
Unnamed: 5
Unnamed: 6
Unnamed: 7
Unnamed: 8
Unnamed: 9
Unnamed: 10
Set the axis parameter to 1 when calling the drop method.
Assign the resulting Dataframe to final_nominations.


I am creating this thread because this question requires you to check several items from Q1 going forward. You need to make sure in Q1:

1- Your energy dataframe has length 227, starts with Afghanistan and ends with Zimbabwe.

2- Your GDP dataframe has length 264, starts with Aruba and ends with Zimbabwe (ScimEn has length 191).

3- Your dictionary replacements work as intended and contain no misspellings.

4- Your merges are on Country and not a combination of Country and Country Name. This means that you need to change the Country Name column to Country in the GDP dataframe. To see, why this matters, please see this example.

5- You accounted for the space between the paranthesis and the country name in your regexs. As an example, "Iran " should be replaced with "Iran". An easy way to carry this out is using .str.strip() on the Country column.

Another mistake learners commonly make is in their dataframes to be merged. An example,

```
df1 = pd.merge(energy, gdp,...)
df2 = pd.merge(df1, scimen,...)
```
You should not put the variables from the outer merges as inputs into the inner merges and vice versa.

Also, please do not clean the dataframes more than instructed in the question instructions. 
So, digit and paranthesis cleaning steps are required however trying to match countries through the dataframes other than this will result in incorrect answers such as replacing "Viet Nam" with "Vietnam" as an example.

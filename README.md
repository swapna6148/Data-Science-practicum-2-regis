# Data-Science-practicum-2-regis
Overview:

Reading the train, test, and validation datasets from Excel files.
Reading the locations and pincodes (Zip code) from text files and creating a dictionary to map locations to pincodes, adding a new column named "Pincode" to all three datasets by mapping location to Pincode.
Performing exploratory data analysis and checking for missing values
Cleaning the Bathrooms column by replacing non-integer values with NaN values, filling missing values with the mean of the column, and converting the data type to integer
cleaning the Facing column by replacing non-allowed values with NaN values, filling missing values with the mode of the column, and capitalizing all values in the validation dataset.
Cleaning the Furnishing column by replacing non-allowed values with NaN values and filling missing values with the mode of the column
cleaning the tenants column by replacing non-allowed values with NaN values and filling missing values with the mode of the column.
Cleaning the Area column by replacing non-numeric values with NaN values, filling missing values with the mean of the column, and converting the data type to float.

The label encoding technique is used to convert categorical variables into numerical values, which can be easily understood by machine learning models. However, it is important to note that label encoding can introduce an order or hierarchy among the categories.
After encoding the categorical variables, we are now visualizing the data using various techniques. The sns.distplot() function is used to plot the distribution of the target variable (Price), which helps us understand its spread and shape. The sns.heatmap() function is used to plot a correlation matrix between all numerical features, which can help identify the relationships and dependencies among them. It is important to note that correlation does not imply causation, and one should use additional techniques such as feature importance or permutation importance to identify the most important features for the machine learning model.

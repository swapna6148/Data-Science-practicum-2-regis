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

I worked on feature selection and training of regression models to predict the prices of houses. First, correlation matrix is computed and then chi-squared test is performed to select the features for model training. Based on correlation and chi-squared test, Furnishing, Facing, Bedrooms, Location, Area, and Locality are selected features. The dataset is split into train and test sets, and the train set is standardized using StandardScaler. Four regression models, Linear Regression, Decision Tree Regressor, Support Vector Regressor, and Random Forest Regressor are trained and evaluated on the train set.Cross-validation is used to evaluate the performance of each model. Root mean squared error (RMSE) is used as a metric to evaluate the models on the test set.The Random Forest Regressor is found to be the best model, with a mean error of 7106 and a standard deviation of +-582.

this week, I created a QQ plot and a scatter plot to visualize the residuals of the model. This is important to check if the model's errors are normally distributed and if there are any patterns in the residuals.

Also performed hyperparameter tuning using the RandomizedSearchCV function. Which is important to find the best combination of hyperparameters for the model to improve its performance.

Finally, we selected  the final model using the best hyperparameters found during hyperparameter tuning. This final model will be ready to be deployed for prediction of house prices in the coming week.

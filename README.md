# Data-Science-practicum-2-regis
# Accomdation Fare Predictor

Overview:

In my project my first step is to Perform EDA (Exploratory Data Analysis), data cleaning, and data processing The code first reads in the datasets using pandas.

The EDA starts with checking for missing values, which are found in the train and test datasets. The code then cleans the 'Bedrooms' and 'Bathrooms' columns using a function 'clean_bed' and 'clean_bath', respectively. The 'Bedrooms' column is cleaned by removing unnecessary text and converting the data type to integer. The 'Bathrooms' column is cleaned by converting integer values to the integer data type and all other values to None. A histogram is then plotted using seaborn to visualize the distribution of the 'Bathrooms' column.

The 'Facing' column is cleaned next using the 'clean_facing' function, which replaces any non-standard facing directions with None. The 'Furnishing' and 'Tenants' columns are cleaned using similar functions 'clean_furnish' and 'clean_ten', respectively, and any non-standard values are replaced with None. 

Finally, the 'Area' and 'Price' columns are cleaned using 'clean_area' and 'clean_price' functions, respectively, which remove unnecessary characters and convert the data type to integer. The 'Area' column is cleaned by converting the different units (square feet, square yard, ground) to a single unit (square feet) and any missing values are replaced with zero. The 'Price' column is cleaned by removing commas and converting the data type to integer. All cleaned datasets are saved back to their respective excel files.

Now we are performing data preprocessing tasks for a machine learning model. It is divided into several parts:

1. Splitting the data into train and test sets and assigning them to variables X_train, Y_train, X_test, and Y_test.

2. Importing KNNImputer from the scikit-learn library, creating an instance of the KNNImputer class, and specifying the number of neighbors and the option to add an indicator for missing values.

3. Creating lists of numerical column names in X_train and X_test.

4. Checking for the number of missing values in numerical columns of X_train.

5. Fitting the KNNImputer instance on X_train numerical columns using the fit() method.

6. Transforming X_train numerical columns with the fitted KNNImputer instance using the transform() method and storing the result in a new DataFrame called x_missing_train.

7. Transforming X_test numerical columns with the fitted KNNImputer instance using the transform() method and storing the result in a new DataFrame called x_missing_test.

8. Renaming the columns of x_missing_train and x_missing_test to match the original column names of the numerical columns.

9. Dropping the original numerical columns from df_train and df_test DataFrames and replacing them with the imputed numerical columns.

10. Displaying the first five rows of the updated df_test DataFrame.

So, the code performs missing value imputation using KNNImputer on numerical columns of the train and test sets, replaces the original columns with imputed columns, and displays the updated test set.

now performed feature selection and prepares the data for model training and evaluation. 

First, it selects the categorical columns to be encoded using label encoding. The columns selected are 'Bedrooms', 'Facing', 'Furnishing', 'Tennants', 'Locality', and 'Location'. LabelEncoder from the scikit-learn library is used to encode the categorical values in these columns into numerical labels.

Then, the distribution of the target variable 'Price' in the training data is visualized using seaborn's distplot function, which creates a histogram with a density curve.

Next, the correlation between the features and the target variable is explored using a heatmap visualization created with seaborn's heatmap function.

After exploring the data, feature selection is performed. First, the correlation matrix is computed using the corr method of the pandas DataFrame. The correlation values between the features and the target variable 'Price' are sorted in descending order, and the top features with high correlation are selected. These features are 'Bedrooms', 'Bathrooms', 'Furnishing', 'Area', 'Locality', 'Location', 'Facing', 'Tennants', and 'Pincode'. 

Next, the chi-squared test is performed to determine the statistical significance of the features. The features with a higher p-value are considered independent of the target variable and are removed from the dataset. The features that are removed are 'Tennants', 'Pincode', and 'Bathrooms'. 

Finally, the selected features are used to prepare the data for model training and evaluation. The selected features are used to create the feature matrix X and target variable vector y for both training and testing data. The selected features are also standardized using StandardScaler from the scikit-learn library to bring them to the same scale.

In, Model training we performed the process of training and evaluating different regression models for predicting a continuous target variable using a given training dataset. 

The four models used are Linear Regression, Decision Tree Regressor, Support Vector Regressor, and Random Forest Regressor. The dataset is split into training and testing sets, and the models are trained using only the training set. 

The evaluation metrics used for each model are root mean squared error (RMSE) and cross-validation scores with 10 folds. The lower the RMSE, the better the model's performance, while the cross-validation scores provide an estimate of the model's generalization performance.

After training and evaluating each model, the best-performing model is determined based on the mean RMSE score from cross-validation. In this case, the Random Forest Regressor had the best performance with a mean RMSE of 7106 and a standard deviation of +- 582. 

Finally, the residuals of the best model are plotted using a QQ plot and a scatter plot to check if the model's assumptions are met.

As, we can clearly see that the Random forest regressor is the best fit having least Prediction error and standard deviation compared to other regression model we used. so Random forest regressor is the best fit and we saved the random forest regression model using pickle library. The model is saved as a pickle file named 'model.pkl'.The 'predict_rent' function loads the saved model using the pickle.load() function and applies the predict() method of the loaded model to the preprocessed input dataframe. The predicted rent values are returned as a list.

Finally, the predicted rent values are converted to a pandas dataframe with column name 'Price', and saved as a CSV file named 'validated_prices.csv'.

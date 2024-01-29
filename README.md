************ Analysis of Salaries and other features of san francisco employees ****************


************ PROJECT DESCRIPTION ****************

in this project, we are not just going to analyze the salary of san francisco employees 

we are also going to apply some of the well-known machine-learning algorithms to other features

like gender, JobTitle ..etc

some of the algorithms used:

 - Logestic regression
 - Linear regression
 - Random forest

the project takes a CSV file for the San Francisco salaries and does the previously mentioned

processes.


************ Description of the important functions used, block by block, if the block is too big we will just include its index at the file like this "in[number] ************

1 - pd.read_csv("Salaries for San Francisco Employee.csv"):
This function is from the Pandas library.
It reads a CSV file and returns a DataFrame containing the data from the file.
In the code, it reads the CSV file named "Salaries for San Francisco Employee.csv" and stores the data in the DataFrame named df.

2 - pd.to_numeric(df[series], errors='coerce'):
This function is from the Pandas library.
It converts the values in a column to numeric format.
The df[series] refers to a specific column in the DataFrame df.
The errors='coerce' parameter handles any invalid or unconvertible values by replacing them with NaN (Not a Number) values.

3 - sns.distplot(df['BasePay']):
This function is from the Seaborn library.
It creates a histogram (distribution plot) for a given column.
The df['BasePay'] refers to the 'BasePay' column in the DataFrame df.

4 - sns.heatmap(df.isnull(), yticklabels=False, cbar=False):
This function is from the Seaborn library.
It creates a heatmap to visualize the presence of missing values in a DataFrame.
The df.isnull() returns a DataFrame of the same shape as df with boolean values indicating the presence of missing values.
The yticklabels=False parameter disables y-axis tick labels, and the cbar=False parameter disables the color bar.

5 - df[mask_BasePay]:
This is indexing notation in Pandas.
It filters the DataFrame df based on a provided Boolean mask, keeping only the rows that meet the specified condition.
The mask_BasePay is a Boolean mask generated using the between() function.

6 - df['JobTitle'].map(findJobTitle):
This function is from the Pandas library.
It applies a function to each value in a column.
The df['JobTitle'] refers to the 'JobTitle' column in the DataFrame df.
The findJobTitle is a user-defined function that maps job titles to broader job categories.

7 - def findJobTitle(row): ...:
This is a user-defined function that takes a job title as input and returns a broader job category based on predefined keywords.
It uses conditional statements to match keywords in the job title and assign a corresponding category.
The function is applied to the 'JobTitle' column using the map() function.

8 - sns.kdeplot(df['TotalPay'])
sns.kdeplot(df['BasePay']);
In summary, these two lines of code generate KDE plots to visualize the distributions of the 'TotalPay' and 'BasePay' columns in the DataFrame df.


9 - in[22]
The code groups the data by year and job title, calculating the average 'TotalPay' for each group.
It extracts the job titles for the year 2011 and stores them in a list.
Bar traces are created for each year (2011-2018), with job titles as x-axis values and average 'TotalPay' as y-axis values.
The traces are combined into a list called data.
The layout is set to group the bars together.
A Figure object is created with the data and layout.
The Figure is plotted inline using the Cufflinks library, resulting in a grouped bar chart showing the average 'TotalPay' for different job titles across multiple years.
In summary, the code generates a visual representation of how the average 'TotalPay' varies across different job titles for each year from 2011 to 2018.

10 - in[24]
The code creates bar traces for three variables: 'BasePay', 'OvertimePay', and 'Benefits'.
For each variable, a trace is created with job titles as x-axis values and average values of the respective variable as y-axis values.
The traces are combined into a list called data.
The layout is set to group the bars together.
A Figure object is created with the data and layout.
The Figure is plotted inline using the Cufflinks library, resulting in a grouped bar chart showing the average values of 'BasePay', 'OvertimePay', and 'Benefits' for different job titles.

11 - in[25]
The code installs the gender-guesser library using the !pip install command.
It imports the gender_guesser.detector module from the gender-guesser library.
An instance of the gender detector is created and assigned to the variable d.
The 'EmployeeName' column in the DataFrame df is processed to extract the first name using the apply(lambda x: x.split()[0]) function. This splits each full name into a list of words and selects the first element (the first name).
The extracted first names are then processed using the apply(lambda x: d.get_gender(x.lower())) function. This applies the gender detector to each first name, converting it to lowercase and using the get_gender() method to determine the likely gender.
The gender results are assigned to a new column called 'Gender' in the DataFrame df, indicating the predicted gender for each employee based on their first name.

12 - in[34] The simple linear regression
Prepare the data:

The code assumes you have a DataFrame named 'df' containing the necessary columns.
The data is split into input (X) and target (y) variables, with 'X' representing the features and 'y' representing the 'BasePay' column.
Split the data:

The data is split into training and testing sets using the train_test_split function from scikit-learn.
The 'X' and 'y' variables are divided into 'X_train', 'X_test', 'y_train', and 'y_test' sets, with a test size of 20% and a random state of 42 for reproducibility.
Create and train the regression model:

A linear regression model is created using the LinearRegression class from scikit-learn.
The model is trained using the training data with the fit method.
Evaluate the model:

The model's performance is evaluated using mean squared error (MSE) as the metric.
Predictions are made on both the training and testing sets.
The mean squared error is calculated by comparing the actual 'BasePay' values with the predicted values.
Make predictions:

Assuming you have a new DataFrame named 'new_data' with the same columns as the training data, you can make predictions using the trained model.
The new data is provided, and the model's prediction method is used to obtain the predicted 'BasePay' value for the given input features.

13 - in[54]
Subset the dataframe:

The code creates a subset of the original dataframe named 'df_subset' containing the relevant columns, including the target variable ('BasePay') and the input features ('OvertimePay', 'OtherPay', 'Benefits', 'TotalPay', 'TotalPayBenefits').
Split the data:

The data is split into input features (X) and the target variable (y).
'X' contains all the columns from 'df_subset' except for 'BasePay', while 'y' contains only the 'BasePay' column.
Instantiate the Random Forest Regressor:

The code creates an instance of the Random Forest Regressor model.
Fit the model:

The model is fitted to the data using the fit method, with 'X' as the input features and 'y' as the target variable.
Get the feature importances:

The code retrieves the feature importances from the trained Random Forest Regressor model using the feature_importances_ attribute.
Create a dataframe for feature importance:

A dataframe named 'feature_importance' is created to store the feature names and their corresponding importance.
The 'Feature' column contains the names of the input features, and the 'Importance' column contains their corresponding importance scores.
Sort the features by importance:

The 'feature_importance' dataframe is sorted in descending order based on the 'Importance' column using the sort_values method.
Print the top n features:

The code selects the top 'n' features with the highest importance scores from the sorted 'feature_importance' dataframe.
'n' is set to 3 in the provided code.
The top features and their importance scores are printed to the console.
This analysis helps identify the most important features that contribute to predicting the 'BasePay' in the dataset, based on the Random Forest Regressor model.


************ HOW TO INSTALL AND RUN ****************

The project is written in Jupyter Notebook which is an open-source web application, you need to 

install it in order to run the project, after installing it you just need to upload it to Jupyter  

the .ipynb file we provided, all needed packages will be installed after running the code. 


************* HOW TO USE THE CODE ****************

You just need to run the code, it contains a description of each part of the code, just run it

and you will get the outputs.






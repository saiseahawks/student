---
layout: post
title: Data Structures Write Up
description: A summary regarding the required elements from the MiraCosta course description
courses: {'compsci': {'week': 12}}
type: tangibles
comments: true
---

**CPT Project Overview**

Our CPT project is a video geam  website that allows users to select from multiple fun games to play and enjoy. Certain games are free to play while others need the user to create and account for. I specifically made the users feature and I would like to highlight the modify function that includes favorites which changes user data.



|Requirements|Response|
| :---------------- | :------: |
|From VSCode using SQLite3 Editor, show your unique collection/table in database, display rows and columns in the table of the SQLite database.|![database](<Screenshot 2024-04-16 at 11.43.23 PM.png>) This shows the SQLite3 database with all of the custom parameters and columns|

|From VSCode model, show your unique code that was created to initialize table and create test data.|![code](<Screenshot 2024-04-17 at 12.14.34 AM.png>) This model shows the initialization of all the users with individual and unique attributes.|


|Lists and Dictionaries|Response|
| :---------------- | :------: |
|In VSCode using Debugger, show a list as extracted from database as Python objects.|![Alt text](<Screenshot 2024-04-17 at 1.44.41 PM.png>) This list is extracted from the debugger showing each individual user and their unique characteristics and data|

|In VSCode use Debugger and list, show two distinct example examples of dictionaries, show Keys/Values using debugger.|![Alt text](<Screenshot 2024-04-17 at 2.03.13 PM.png>) This dictionary contains two dictionaries for the NFL api and the Games project|


|APIs and JSON|Response|
| :---------------- | :------: |
|In VSCode, show Python API code definition for request and response using GET, POST, UPDATE methods. Discuss algorithmic condition used to direct request to appropriate Python method based on request method.|![Alt text](<Screenshot 2024-04-17 at 12.44.36 AM.png>)Post functions takes data from the body input and creates the user after checking if it already exists!![code](<Screenshot 2024-04-17 at 12.44.46 AM.png>)![code](<Screenshot 2024-04-17 at 12.45.03 AM.png>) The algorithmic condition for directing requests to the appropriate Python method based on the request method involves inspecting the HTTP method of the incoming request. Using conditional statements, such as if or elif, the server determines which function or method should handle the request. For instance, in a Flask application, the request.method attribute is examined, and based on its value (e.g., GET, POST, UPDATE), the server routes the request to the corresponding function designed to handle that specific HTTP method. |

|In VSCode, show algorithmic conditions used to validate data on a POST condition.|![code](<Screenshot 2024-04-17 at 12.51.21 AM.png>)This code shows how the POST condition algorithimically checks the validation of the data|

|In Postman, show URL request and Body requirements for GET, POST, and UPDATE methods. Also, in Postman, show the JSON response data for 200 success conditions on GET, POST, and UPDATE methods.|![text](<Screenshot 2024-04-17 at 12.54.55 AM.png>)![text](<Screenshot 2024-04-17 at 12.56.02 AM.png>)![text](<Screenshot 2024-04-17 at 12.56.54 AM.png>)|

|In Postman, show the JSON response for error for 400 when missing body on a POST request.|![text](<Screenshot 2024-04-17 at 12.59.46 AM.png>)|

|In Postman, show the JSON response for error for 404 when providing an unknown user ID to a UPDATE request.|![text](<Screenshot 2024-04-18 at 11.56.46 AM.png>)|


|Frontend|Response|
| :---------------- | :------: |
|In Chrome inspect, show response of JSON objects from fetch of GET, POST, and UPDATE methods.|![text](<Screenshot 2024-04-17 at 2.17.43 PM.png>)![text](<Screenshot 2024-04-17 at 2.16.34 PM.png>)![text](<Screenshot 2024-04-17 at 2.13.05 PM.png>)|

|In the Chrome browser, show a demo (GET) of obtaining an Array of JSON objects that are formatted into the browsers screen.|![text](<Screenshot 2024-04-17 at 1.07.09 AM.png>)|

|In JavaScript code, describe fetch and method that obtained the Array of JSON objects.|This HTML document with embedded JavaScript fetches data from an API endpoint and dynamically populates a table with the retrieved data. It uses the Fetch API to make a GET request to the specified URL, and upon receiving a successful response, it processes the JSON data and dynamically generates table rows and cells to display the data. Error handling is implemented to redirect users to error pages in case of server errors or blocked access. Overall, this code provides a dynamic way to display API data in an HTML table with error handling capabilities.|

|In JavaScript code, show code that performs iteration and formatting of data into HTML.|![text](<Screenshot 2024-04-17 at 1.10.50 AM.png>)This code shows how the JS function outputs the returned backend data into a visible HTML database|

|In the Chrome browser, show a demo (POST or UPDATE) gathering and sending input and receiving a response that show update. Repeat this demo showing both success and failure.|Success:![text](<Screenshot 2024-04-17 at 1.13.47 AM.png>)![text](<Screenshot 2024-04-17 at 1.15.21 AM.png>) Failure: no response to click of button|

|In JavaScript code, show and describe code that handles success. Describe how code shows success to the user in the Chrome Browser screen.|The code redirects upon success to a page where the newly entered data can be viewed. Typically this is set to the favorite page which is normally changed.![image](<Screenshot 2024-04-18 at 11.21.26 AM.png>)|

|In JavaScript code, show and describe code that handles failure. Describe how the code shows failure to the user in the Chrome Browser screen.|![image](<Screenshot 2024-04-18 at 11.17.22 AM.png>) |


|Optional/Extra, Algorithm Analysis|Response|
| :---------------- | :------: |
|Show algorithms and preparation of data for analysis. This includes cleaning, encoding, and one-hot encoding.|![text](<Screenshot 2024-04-17 at 10.22.23 PM.png>)|

|Show algorithms and preparation for predictions.|![text](<Screenshot 2024-04-17 at 10.26.32 PM.png>)|

|Discuss concepts and understanding of Linear Regression algorithms.|Linear Regression aims to find the best-fitting linear relationship between the independent variables and the dependent variable. It uses the ordinary least squares method to minimize the sum of squared differences between the observed and predicted values. Assumptions include linearity, independence of errors, homoscedasticity, and normality of residuals. It's sensitive to outliers and multicollinearity.|

|Discuss concepts and understanding of Decision Tree analysis algorithms.|Decision Trees partition the feature space into regions and predict the target variable based on the majority class or average value in each region. They're easy to interpret and visualize. Prone to overfitting, especially with deep trees. Techniques like pruning, setting maximum depth, or using ensemble methods like Random Forests mitigate overfitting.|


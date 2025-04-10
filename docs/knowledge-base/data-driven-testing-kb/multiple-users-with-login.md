---
title: Multiple Users with Login
page_title: Multiple Users with Login
description: How to configure a test to use the same data source row multiple times. 
position: 1
---
## Repeating Actions for Multiple Users with Login

After loading the input data using data binding (an Excel file), I want to get the specific row item in the data multiple times. Here is the business scenario:

1. Login as user1 and perform some actions/test.

2. Login as user2 and perform some actions/test.

3. Login as user1 and perform some verification.

All of my users are stored in the data source which is data bound to my test. To be specific "How do I fetch/point a desired row to the application value."
 
There is another approach that would avoid having to go to code and looking up records in the data source. If you structure your tests the right way you can data bind everything and achieve your test cases: Create two main login tests:

* **MainTestA**
 
* **MainTestB**

These tests only login in the user. Data bind these tests to your Excel spreadsheet. Next create two sub-tests:

1. **SubTestA** performs the actions and assume the user is already logged in.

2. **SubTestB** performs the verifications and assume the user is already logged in.

These tests can either use the same Excel file as the main tests, or you can data bind them to separate Excel files. If you use a different Excel file the sub-test will execute all the rows in the Excel file before returning to the main test.

* Modify **MainTestA** to call **SubTestA** via Test-as-step feature. After calling the sub-test add steps to log out the user.

* Modify **MainTestB** to call **SubTestB** via Test-as-step feature. After calling the sub-test add steps to log out the user.

Create a test list - **EndToEndTestListA**. Add **MainTestA** and **MainTestB** to it. Now when you run **EndToEndTestListA** it will execute in this manner:

1. **MainTestA** will begin execution. It will run for all the rows in the login Excel file.

2. For each row it will call **SubTestA** to perform the same actions for each user.

3. If **SubTestA** is bound to a separate data file it will run all the rows in that data file before returning to **MainTestA**.

4. When **MainTestA** is done executing **MainTestB** will begin executing.

5. It will run in the same manner as **MainTestA** except it will call **SubTestB** instead of **SubTestA**.
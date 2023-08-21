---
title: Dynamic Data Binding
page_title: Dynamic Data Binding
description: I want my test to dynamically bind to a different data set at run-time. The data I want the test to use will depend on certain conditions of my application, but the test steps will always be the same.
previous_url: /user-guide/knowledge-base/data-driven-testing/dynamic-data-binding.aspx, user-guide/knowledge-base/data-driven-testing/dynamic-data-binding
position: 1
---
#Dynamic Data Binding#

*I want my test to dynamically bind to a different data set at run-time. The data I want the test to use will depend on certain conditions of my application, but the test steps will always be the same.*

##Solution 1##

First, be aware that dynamically binding data is not currently a built-in feature in Test Studio. You can only bind a test to a single data source. However, there is a trick you can implement in code to achieve the same result. The trick relies on swapping the data file to which a test is bound at run time. 

1. Start with a master test. This test may be data bound, but it's not required.

2. Use some criteria and your code to decide which data file you want to use during that test run.

3. Swap the physical file on disk with the real file you want to use in your data bound test.

4. Have your master test call a sub-test that is bound to this data file.

For example:

1. Create a sub-test and bind it to an Excel spreadsheet named *Book1.xlsx*.

2. In a coded step in your main test, swap *Book1.xlsx* for the file you actually want to be used by your sub-test.

3. Keep in mind that when Test Studio binds a test to an Excel file, it actually makes a copy of the file in the **Project\Data** folder. Ensure you swap the file located in the **Project\Data** folder, and not the file in its original location.

##Solution 2##

Put your data into a SQL data base and <a href="/features/data-driven-testing/bind-test-data-source" target="_blank">Use T-SQL to Pull the Data</a> you want from the database. Optionally, you can <a href="/knowledge-base/data-driven-testing-kb/sql-random-row" target="_blank">Generate a Random Number</a> in your T-SQL to point to the row of data to pull.

##Solution 3##

You can <a href="/advanced-topics/coded-samples/general/execution-extensions" target="_blank">Create Your Own Test Extension DLL</a> and implement the OnInitializeDataSource in which you can do pretty much anything in code. Place the DLL into the following directory:

* **C:\Program Files (x86)\Progress\Test Studio\Bin\Plugins\**

 

It will be called for every test you execute. Whatever OnInitializeDataSource creates and returns will be used as the data source, overriding any file to which the test may have been previously bound.
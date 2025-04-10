---
title: SQL Random Row
page_title: SQL Random Row
description: I would like to use a single, random row of data for each execution of a test that is data bound to a SQL Database.
position: 1
---
## Use T-SQL to Pull a Random Row from a SQL Database

*I would like to use a single, random row of data for each execution of a test that is data bound to a SQL Database.*

## Solution

This is possible with T-SQL. Here's how to do it:

1. <a href="/features/data-driven-testing/sql-database-example" target="_blank">Add a SQL Database Source</a> to the project. Here's what the sample database looks like in SQL Server Management Studio Express:

	![Create DB][1]


2. <a href="/features/data-driven-testing/bind-test-data-source" target="_blank">Bind the Test</a> to the SQL Database. Here's what the Setup Binding dialog looks like before T-SQL is enabled:

	![Bind test][2]

3. Check **Use T-SQL**. Enter the following code into the **T-SQL Editor** section and click **Update**:

````SQL
SELECT TOP 1 [Name], [City], [Email], [Message]
FROM [myDataBase].[dbo].[table]
Where Email Like '%domain%'
ORDER By NEWID()
````

- Line 1 indicates how many rows and which columns to use.
	
- Line 2 indicates the database and table name.
	
- Line 3 indicates whether to filter based on text matching criteria. In this case, since all entries in the Email column contain domain, all rows are returned.
	
-  Line 4 sorts the rows by a unique identifier, which essentially randomizes them in the database.


4.&nbsp; Click **Update again** to see the randomization in action. 

![Random row][3]

5.&nbsp; The following test navigates to a site containing a sample contact form. Note that the Enter text steps already have the corresponding data columns <a href="/features/data-driven-testing/attach-columns-input-values" target="_blank">Attached to Input Values</a>.


![Bind columns][4]

6.&nbsp; Run the test. A random row will be used to data drive the test each time you execute it.

![Test execution][5]

	

[1]: /img/knowledge-base/data-driven-testing-kb/sql-random-row/fig1.png
[2]: /img/knowledge-base/data-driven-testing-kb/sql-random-row/fig2.png
[3]: /img/knowledge-base/data-driven-testing-kb/sql-random-row/fig3.png
[4]: /img/knowledge-base/data-driven-testing-kb/sql-random-row/fig4.png
[5]: /img/knowledge-base/data-driven-testing-kb/sql-random-row/fig5.png

	


---
title: Data Driving
page_title: Data Driving a Load Test
description: "Data drive / parameterize the dynamic targets in Test Studio load test. The http requests in a load test need to be parameterized. "
position: 13
---
# Data Driving

If you need each virtual user to be unique when communicating with your web application, use the data driven load testing feature. With a data driven load test, you can bind a dynamic target to a specific column from an external data source (for example, an Excel spreadsheet or a SQL database).

1.&nbsp; <a href="/features/data-driven-testing/add-data-source" target="_blank">Add an external data source to the project</a>.

2.&nbsp; <a href="/features/data-driven-testing/bind-test-data-source" target="_blank">Bind the Load Test</a> to that data source.

3.&nbsp; Open the specific <a href="/features/testing-types/load-testing/adding-user-profiles" target="_blank">user profile</a> that will use the data.

4.&nbsp; Locate the specific HTTP transaction (like an HTTP POST request) that will use the data. Click on the transaction.

![Edit User Profile][1]

A key-value pair appears for each dynamic target. 

5.&nbsp; Click the drop-down for the dynamic target you want to data-drive. A list appears containing the available columns in the data source. 

6.&nbsp; Click the drop-down item for the correct data source column. 

![Edit User Profile 2][2]

7.&nbsp; Click Save.

When your load test runs, each virtual user will use a different row from the data source. After using each row, the load test will start over again with the first row and repeat for the duration of the load test.

[1]: /img/features/testing-types/load-testing/data-driving/fig1.png
[2]: /img/features/testing-types/load-testing/data-driving/fig2.png
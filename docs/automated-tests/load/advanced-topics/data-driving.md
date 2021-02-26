---
title: Data Driven Load Testing
page_title: Data Driving a Load Test
description: "Data drive / parameterize the dynamic targets in Test Studio load test. The http requests in a load test need to be parameterized."
position: 2
---
# Data Driven Load Testing

If you need each virtual user to be unique when communicating with your web application, use the data driven load testing feature. With a data driven load test, you can bind a dynamic target to a specific column from an external data source (for example, an Excel spreadsheet or a SQL database).

## Bind a Load Test to Data Source

There are few simple steps to follow in order to use the external data source within a load test and these are desribed below.

1.&nbsp; <a href="/features/data-driven-testing/add-data-source" target="_blank">Add an external data source to the project</a>.

2.&nbsp; <a href="/features/data-driven-testing/bind-test-data-source" target="_blank">Bind the Load Test</a> to that data source.

3.&nbsp; Open the specific <a href="/features/testing-types/load-testing/adding-user-profiles" target="_blank">user profile</a> that will use the data.

4.&nbsp; Locate the specific HTTP transaction (like an HTTP POST request) that will use the data. Click on the transaction.

![Edit User Profile][1]

A key-value pair appears for each dynamic target - these that you selected from the <a href="/features/testing-types/load-testing/designing-load-tests/dynamic-targets#auto-detected-dynamic-targets" target="_blank">automatically detected dynamic targets</a>, or the <a href="/features/testing-types/load-testing/designing-load-tests/dynamic-targets#custom-dynamic-targets" target="_blank">custom targets</a>, which you manually added in the user profile.

## Choose the Column from Data Source to Bind to a Dynamic Target

5.&nbsp; Click the drop-down for the dynamic target you want to data-drive. A list appears containing the available columns in the data source.

6.&nbsp; Click the drop-down item for the correct data source column.

![Edit User Profile 2][2]

7.&nbsp; Click Save.

**Note!** When the load test runs, each virtual user will take a different row from the data source. After using each row, the load test will start over again with the first row and repeat for the duration of the load test.

[1]: /img/features/testing-types/load-testing/data-driving/fig1.png
[2]: /img/features/testing-types/load-testing/data-driving/fig2.png
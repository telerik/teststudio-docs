---
title: What is Data Driven Testing
page_title: What is Data Driven Testing
description: "Data Driven Testing in Test Studio. Parameterize the test in Test Studio. Use iterated data in a Test Studio test"
position: 0
---
# What is Data Driven Testing

Data Driven Testing is a testing methodology, in which the same sequence of test steps are performed repeatedly using a data source. The input values of the test steps and/or the values to expect for verification steps will be taken from the bound data source.

Test Studio supports data driven testing with both built-in data source or an external one. There are few different types of external data sources compatible with Test Studio and among these are Excel and SQL database.

## Get Started with the Data Driven Test

To get familiar with the capabilities of the data driven testing approach and how Test Studio handles it, you can start with a simple test to search different products in the Telerik site. <a href="/automated-tests/data-drive-test/local-data-driven-test" target="_blank">Here is a step-by-step tutorial</a> for building such test.

## go on with more complex scenario 
<br>
<br>
<br>
<br>
<br>
<br>
<br>

- [Local Data Source](/features/data-driven-testing/local-data-driven-test)
- [Excel spreadsheet](/features/data-driven-testing/add-data-source#add-an-excel-spreadsheet)
- [XML file](/features/data-driven-testing/add-data-source#add-an-xml-file)
- [CSV file](/features/data-driven-testing/add-data-source#add-a-csv-file)
- [SQL database](/features/data-driven-testing/add-data-source#add-a-database-source)

 

Create an external data driven test by following these steps:

1. [Add a data source to your test project](/features/data-driven-testing/add-data-source) - select from where to get the data.
1. [Bind the data source to your test](/features/data-driven-testing/bind-test-data-source)- since you may have multiple data source definitions in your test project, you need to bind your data driven test to a specific data source.
1. [Attach the data source columns to input values](/features/data-driven-testing/attach-columns-input-values) - connect the inputs of your test  to specific columns of the data source.
1. [Attach the data source columns to verifications](/features/data-driven-testing/attach-columns-verifications) - connect the expected values of verifications to specific columns of the data source

---
title: Overview
page_title: Data Driven Testing Overview
description: "Data Driven Testing in Test Studio. Parameterize the test in Test Studio. Use iterated data in a Test Studio test"
position: 0
publish: false 
---
# Data Driven Testing

Data Driven Testing is a testing methodology in which the same sequence of test steps are performed repeatedly, using a data source to drive the input values of those steps and/or the values to expect, when performing verification steps. 

Test Studio supports can be used for data driven testing. It supports five different external data sources:

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

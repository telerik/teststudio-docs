---
title: What is Data Driven Testing
page_title: What is Data Driven Testing
description: "Data Driven Testing in Test Studio. Parameterize the test in Test Studio. Use iterated data in a Test Studio test"
position: 0
---
# What is Data Driven Testing

Data Driven Testing is a testing methodology, in which the same sequence of test steps are performed repeatedly using a data source. The input values of the test steps and/or the values to expect for verification steps will be taken from the bound data source.

Test Studio supports data driven testing with both built-in data source or an external one. There are few different types of external data sources compatible with Test Studio and among these are Excel and SQL database.

## Get Started with Data Driven Testing

To get familiar with the capabilities of the data driven testing approach and how Test Studio handles it, you can start with this __<a href="/automated-tests/data-drive-test/local-data-driven-test" target="_blank">step-by-step tutorial</a>__ to prepare a sample test to data drive.

## Choose an External Data Source for Data Driven Testing

Test Studio allows you to use different type of data sources within a project. Here is a list of the supported types:

- [Excel spreadsheet](/features/data-driven-testing/add-data-source#add-an-excel-spreadsheet)
- [XML file](/features/data-driven-testing/add-data-source#add-an-xml-file)
- [CSV file](/features/data-driven-testing/add-data-source#add-a-csv-file)
- [SQL database](/features/data-driven-testing/add-data-source#add-a-database-source)

> __Tip__
><br>
><br>
> You can follow the <a href="/automated-tests/data-drive-test/external-data-driven-test" target="_blank">steps in this article</a> to __data drive a test using an external source by your choice__.

## Combine Tests Executed as Steps with the Data Driven Methodology

Test Studio encourages the reuse of common tests by providing the option to execute tests as steps. Any of the "parent" test, or the one used as step - "child" test, can be data driven.

What possible combinations there are and what execution outcome you can expect from these? You can read an <a href="/automated-tests/data-drive-test/multi-level-tests" target="_blank">article on the topic</a>, which describes the options in details.
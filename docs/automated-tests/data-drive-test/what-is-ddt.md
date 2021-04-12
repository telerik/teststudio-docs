---
title: Data Driven Testing
page_title: What is Data Driven Testing
description: "Data Driven Testing in Test Studio. Parameterize the test in Test Studio. Use iterated data in a Test Studio test"
position: 0
---
# What is Data Driven Testing and How Test Studio Fits for It

Data Driven Testing is a testing methodology in which the same sequence of test steps is performed repeatedly using a data source. The input values of the test steps and/or the expected values for the verification steps are taken from the bound data source.

Test Studio supports data driven testing with both a built-in data source or an external one. There are a few different types of external data sources compatible with Test Studio. Excel and SQL databases are among them.

## Get Started with Data Driven Testing

To get familiar with the capabilities of the data driven testing approach and the way how Test Studio handles it, you can start with this __<a href="/automated-tests/data-drive-test/local-data-driven-test" target="_blank">step-by-step tutorial</a>__ and prepare a sample test.

## Choose an External Data Source for Data Driven Testing

Test Studio allows you to use different types of data sources within a project. Here is a list of the supported types:

- <a href="/features/data-driven-testing/add-data-source#add-an-excel-spreadsheet" target="_blank">Excel spreadsheet</a>
- <a href="/features/data-driven-testing/add-data-source#add-an-xml-file" target="_blank">XML file</a>
- <a href="/features/data-driven-testing/add-data-source#add-a-csv-file" target="_blank">CSV file</a>
- <a href="/features/data-driven-testing/add-data-source#add-a-database-source" target="_blank">Database</a>

> __Tip__
><br>
><br>
> Follow the <a href="/automated-tests/data-drive-test/external-data-driven-test" target="_blank">steps in this article</a> to data drive a test using an external source of your choice.

## Combine Tests Executed as Steps with the Data Driven Methodology

Test Studio encourages the reuse of common tests by providing the option to <a href="/features/custom-steps/test-as-step" target="_blank">execute tests as steps</a>. Any *parent* test and any test executed as a step can be data driven.

To learn more about the possible test combinations and expected execution outcome, visit the <a href="/automated-tests/data-drive-test/multi-level-tests" target="_blank">dedicated article</a>.

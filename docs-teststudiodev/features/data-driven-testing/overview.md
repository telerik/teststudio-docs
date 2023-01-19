---
title: Overview
page_title: Data Driven Testing Overview - Test Studio Dev Documentation
description: Data Driven Testing is a testing methodology in which the same sequence of test steps are performed repeatedly using a data source
position: 0
---
# Data Driven Testing

Data Driven Testing is a testing methodology in which the same sequence of test steps are performed repeatedly using a data source to drive the input values of those steps and/or the values to expect when performing verification steps. Test Studio can be used for data driven testing. It supports five different data sources:

- <a href="/features/data-driven-testing/local-data-driven-test" target="_blank">Local Data Source</a>
- <a href="/features/data-driven-testing/add-data-source#add-an-excel-spreadsheet" target="_blank">Excel spreadsheet</a>
- <a href="/features/data-driven-testing/add-data-source#add-an-xml-file" target="_blank">XML file</a>
- <a href="/features/data-driven-testing/add-data-source#add-a-csv-file" target="_blank">CSV file</a>
- <a href="/features/data-driven-testing/add-data-source#add-a-database-source" target="_blank">SQL database</a>

How to create a __data driven test using local data__ follow these directions. 

Create an external data driven test by following these steps:

1. <a href="/features/data-driven-testing/add-data-source" target="_blank">Add a data source to your test project</a> - select from where to get the data.
1. <a href="/features/data-driven-testing/bind-test-data-source" target="_blank">Bind the data source to your test</a> - since you may have multiple data source definitions in your test project, you need to bind your data driven test to a specific data source.
1. <a href="/features/data-driven-testing/attach-columns-input-values" target="_blank">Attach the data source columns to input values</a> - connect the inputs of your test  to specific columns of the data source.
1. <a href="/features/data-driven-testing/attach-columns-verifications" target="_blank">Attach the data source columns to verifications</a> - connect the expected values of verifications to specific columns of the data source

---
title: Fix Trimmed Numeric Values
page_title: Fix Trimmed Numeric Values
description: External data source from CSV file is trimmed after the numeric separator. Data is not the same when you bind it to a test. IP values are not full in data driven test.
position: 6
---
#Numeric Values from External Data Source are Trimmed#

##Problem##

When you have a data driven test with CSV external source and for example try typing in an IP address like this "192.168.0.0", the value can get trimmed to just "192.168". The reason why the IP address is trimmed is because of the Ole DB driver, which TestStudio is using under the hood. In details the Ole DB driver is asked to create an in-memory DataTable. The first row defines the column's name and the other rows are the actual data. As each cell value, including the column names, are scanned a data type is extrapolated.

All rows that have IPs like this "192.168.0.0" could get trimmed based on the Windows' Culture settings, where the **"."** is a numeric separator. The DB driver matches this to a "numeric" value and trims it to "192.168".

##Solution##

There are two possible solution for the above issue.

1.&nbsp;You need to add double quotation marks around the IP values, and the DB driver will read the value as a string. 

> If a single row is not escaped with double quotation marks, the whole column will be interpreted as numeric and will be trimmed after the second numeric separator.

2.&nbsp;Another possible solution is to change the Windows' Culture settings, so the numeric separator is not **"."** anymore. 



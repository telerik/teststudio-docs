---
title: Unable to Show Data Tables In Excel Data Source
page_title: Unable to Show Data Data Tables in Excel Data Source
description: "Test Studio data driven test throws an error Test Studio data bound test cannot bind excel file cannot select the sheets from the bound excel file error: The 'Microsoft.ACE.OLEDB.12.0' provider is not registered on the local machine"
position: 1
---
# Unable to Show Data Tables in Excel Data Source

> This could happen on machines with no Microsoft Office or Data Connectivity Component installed or if the Microsoft Office package is 64-bit version.

If running a data driven test on remote machine you get your test failed and the following exception could be found in the log:

```
The 'Microsoft.ACE.OLEDB.12.0' provider is not registered on the local machine
```

<br>
<br>

Another option to face the same error in the application log is to bind an Excel file to a test, and try to select a sheet - the list is empty. 

![No sheets][1]

## Solution

Download and install the **32-bit version** of <a href="https://www.microsoft.com/en-us/download/details.aspx?id=13255" target="_blank">Microsoft Access Database Engine 2010</a>. It will install the required drivers for communication between Test Studio and the Microsoft Office files for all of the above cases.

[1]: /img/troubleshooting-guide/test-execution-problems-tg/unable-to-show-data/fig1.png
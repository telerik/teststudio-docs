---
title: Extracted Variables in Code
page_title: Get/Set Extracted Variables in Code
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/code-samples/general/extracted-variables-in-code.aspx, /user-guide/code-samples/general/extracted-variables-in-code
position: 1
---
# Get/Set Extracted Variables in Code #

Use the *SetExtractedValue()* method to set the value of an extraction variable so it can be used later in a standard action or verification step:

```C#
string area = "Atlanta";
SetExtractedValue("extractedID", area);
```
```VB
Dim area As String = "Atlanta"
SetExtractedValue("extractedID", area)
```

Use the *GetExtractedValue()* method to use the extracted variable in a coded step:

```C#
object myData = GetExtractedValue("varname");
```
```VB
Dim myData As Object = GetExtractedValue("varname")
```


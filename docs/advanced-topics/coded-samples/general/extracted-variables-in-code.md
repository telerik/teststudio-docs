---
title: Extracted Variables in Code
page_title: Get/Set Extracted Variables in Code
description: "Get/Set Extracted Variables in Code in Test Studio coded test."
previous_url: /user-guide/code-samples/general/extracted-variables-in-code.aspx, /user-guide/code-samples/general/extracted-variables-in-code
position: 1
---
# Get/Set Extracted Variables in Code #

> Using Extracted variables in Test Studio tests can be accomplished as well <a href="/features/recorder/verifications/extraction" target="_blank">without using code</a>.

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

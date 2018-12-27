---
title: Extracted Variables in Code
page_title: Get/Set Extracted Variables in Code | Test Studio Dev Documentation
description: Get/Set Extracted Variables in Code
position: 1
---
# Get/Set Extracted Variables in Code #

Use the *SetExtractedValue()* method to set the value of an extraction variable so it can be used later in a standard action or verification step:

#### __[C#]__

    {{region }}

    string area = "Atlanta";
    SetExtractedValue("extractedID", area);
    {{endregion}}

#### __[VB]__

    {{region }}

    Dim area As String = "Atlanta"
    SetExtractedValue("extractedID", area)
    {{endregion}}

Use the *GetExtractedValue()* method to use the extracted variable in a coded step:

#### __[C#]__

    {{region }}

    object myData = GetExtractedValue("varname");
    {{endregion}}

#### __[VB]__

    {{region }}

    Dim myData As Object = GetExtractedValue("varname")
    {{endregion}}
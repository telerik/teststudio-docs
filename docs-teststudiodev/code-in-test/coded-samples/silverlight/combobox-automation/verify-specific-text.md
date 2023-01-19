---
title: Verify Specific Text
page_title: Verify Specific Text - Test Studio Dev Documentation
description: Verify Specific Text
position: 1
---
# Verify Silverlight ComboBox Contains Specific Text #

*I would like to iterate through a Silverlight ComboBox and verify that it contains specific text strings.*

## Solution ##

Here is the sample code to achieve that. 

#### __[C#]__

    {{region }}

    ComboBox cb = Pages.SilverlightToolkitSamples.SilverlightApp.Item0Combobox;
    bool found = cb.TextBlockContent.Contains(Data["Col1"].ToString());
    
    Log.WriteLine("Match found: " + found.ToString());
    Assert.IsTrue(found);
    {{endregion}}

#### __[VB]__

    {{region }}

    Dim cb As ComboBox = Pages.SilverlightToolkitSamples.SilverlightApp.Item0Combobox
    Dim found As Boolean = cb.TextBlockContent.Contains(Data("Col1").ToString())
    
    Log.WriteLine("Match found: " + found.ToString())
    Assert.IsTrue(found)
    {{endregion}}
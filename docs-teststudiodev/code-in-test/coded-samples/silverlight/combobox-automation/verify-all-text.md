---
title: Verify All Text
page_title: Verify All Text - Test Studio Dev Documentation
description: Verify All Text
position: 1
---
# Verify All Text in a Silverlight ComboBox 

Here is the sample code to accomplish that.

````C#
    ComboBox cb = Pages.SilverlightToolkitSamples.SilverlightApp.Item0Combobox;
    
    string full = cb.TextBlockContent.ToString();
    full = full.Trim();
    
    Log.WriteLine(full);
    Assert.AreEqual(full, "All Add Delete Edit Navigation None");
````
````VB
    Dim cb As ComboBox = Pages.SilverlightToolkitSamples.SilverlightApp.Item0Combobox
    
    Dim full As String = cb.TextBlockContent.ToString()
    full = full.Trim()
    
    Log.WriteLine(full)
    Assert.AreEqual(full, "All Add Delete Edit Navigation None")
````
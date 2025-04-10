---
title: Verify Specific Text
page_title: Verify Specific Text
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Verify Silverlight ComboBox Contains Specific Text

I would like to iterate through a Silverlight ComboBox and verify that it contains specific text strings.

## Solution

This is possible with a coded solution:

````C#
ComboBox cb = Pages.SilverlightToolkitSamples.SilverlightApp.Item0Combobox;
bool found = cb.TextBlockContent.Contains(Data["Col1"].ToString());
 
Log.WriteLine("Match found: " + found.ToString());
Assert.IsTrue(found);
````
````VB
Dim cb As ComboBox = Pages.SilverlightToolkitSamples.SilverlightApp.Item0Combobox
Dim found As Boolean = cb.TextBlockContent.Contains(Data("Col1").ToString())
 
Log.WriteLine("Match found: " + found.ToString())
Assert.IsTrue(found)
````
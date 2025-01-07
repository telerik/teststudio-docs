---
title: Verify All Text
page_title: Verify All Text
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Verify All Text in a Silverlight ComboBox

This is possible with a coded solution:

```C#
ComboBox cb = Pages.SilverlightToolkitSamples.SilverlightApp.Item0Combobox;
 
string full = cb.TextBlockContent.ToString();
full = full.Trim();
 
Log.WriteLine(full);
Assert.AreEqual(full, "All Add Delete Edit Navigation None");
```

```VB
Dim cb As ComboBox = Pages.SilverlightToolkitSamples.SilverlightApp.Item0Combobox
 
Dim full As String = cb.TextBlockContent.ToString()
full = full.Trim()
 
Log.WriteLine(full)
Assert.AreEqual(full, "All Add Delete Edit Navigation None")
```



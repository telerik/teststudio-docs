---
title: Attach Data Columns
page_title: Attach Data Columns in Code
description: "Attach Data Columns in Code in Test Studio coded test. Data bind a value in coded test in Test Studio."
previous_URL: /user-guide/code-samples/general/attach-columns-to-input-values-in-code.aspx
position: 1
---
# Attach Columns to Input Values in Code 

*I would like to attach a column from my data table to an input value in code. (This is more easily accomplished through the <a href="/features/data-driven-testing/attach-columns-input-values" target="_blank">Test Studio UI</a>.)*

## Solution 

Use the Data object in conjunction with the column name or index.

In this example on Bing.com, I added the *SbFormQText* element to the <a href="/features/elements-explorer/overview" target="_blank">Elements Explorer</a> via the Add To Project Elements feature from the <a href="/features/elements-menu/overview" target="_blank">Elements Menu</a>. Now I can reference that element in code and data drive its input text:

````C#
//Reference a column by name
Pages.Bing.SbFormQText.Text = Data["Col1"].ToString();
  
//Reference a column by index (zero based)
Pages.Bing.SbFormQText.Text = Data[0].ToString();
````
````VB
'Reference a column by name
Pages.Bing.SbFormQText.Text = Data("Col1").ToString()
 
'Reference a column by index (zero based)
Pages.Bing.SbFormQText.Text = Data(0).ToString()
````

This method can also be applied to a **Verification**:

````C#
//Reference a column by name
Assert.IsTrue(ActiveBrowser.ContainsText(Data["Col1"].ToString()));
  
//Reference a column by index (zero based)
Assert.IsTrue(ActiveBrowser.ContainsText(Data[0].ToString()));
````
````VB
'Reference a column by name
Assert.IsTrue(ActiveBrowser.ContainsText(Data("Col1").ToString()))
 
'Reference a column by index (zero based)
Assert.IsTrue(ActiveBrowser.ContainsText(Data(0).ToString()))
````

---
title: Use Data Source Columns in Code
page_title: Use Data Source Columns in Code
description: "How to use the data source in a coded step. I want to data drive a coded step."
position: 7
---
# Use Data Source Columns in Code

Test Studio allows you to insert any custom code in the tests - that includes the option to convert an already recorded step to code and use it that way.

Given that, you may need to use the values from the data source in a coded steps and this article describes how to access the data columns through code.


#### __[C#]__

	{{region }}

	//Reference a column by name
	Pages.Bing.SbFormQText.Text = Data["Numbers"].ToString();

	//Reference a column by index (zero based)
	Pages.Bing.SbFormQText.Text = Data[0].ToString();

	{{endregion}}

#### __[VB]__

	{{region }}

	'Reference a column by name
	Pages.Bing.SbFormQText.Text = Data("Numbers").ToString()

	'Reference a column by index (zero based)
	Pages.Bing.SbFormQText.Text = Data(0).ToString()

	{{endregion}}


```C#
//Reference a column by name
Pages.Bing.SbFormQText.Text = Data["Col1"].ToString();
  
//Reference a column by index (zero based)
Pages.Bing.SbFormQText.Text = Data[0].ToString();
```
```VB
'Reference a column by name
Pages.Bing.SbFormQText.Text = Data("Col1").ToString()
 
'Reference a column by index (zero based)
Pages.Bing.SbFormQText.Text = Data(0).ToString()
```

This method can also be applied to a **Verification**:

```C#
//Reference a column by name
Assert.IsTrue(ActiveBrowser.ContainsText(Data["Col1"].ToString()));
  
//Reference a column by index (zero based)
Assert.IsTrue(ActiveBrowser.ContainsText(Data[0].ToString()));
```
```VB
'Reference a column by name
Assert.IsTrue(ActiveBrowser.ContainsText(Data("Col1").ToString()))
 
'Reference a column by index (zero based)
Assert.IsTrue(ActiveBrowser.ContainsText(Data(0).ToString()))
```

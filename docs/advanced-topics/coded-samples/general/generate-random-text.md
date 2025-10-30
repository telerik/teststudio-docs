---
title: Generate Random Text
page_title: Generate Random Text
description: "Learn how to generate random text in Test Studio coded tests using .NET’s System.Random class. Includes step-by-step examples for creating random strings and automating input scenarios."
position: 1
---
# Generate Random Text

*I would like to generate random text in Test Studio. This text will be used in an input control or for a similar purpose.*

> __Tip!__
> <br>
> Test Studio provides a <a href="/features/random-gens-steps/random-string" target="_blank">built-in step to generate random text</a> out-of-the-box. 

## Solution 

The .NET Framework provides the <a href="http://msdn.microsoft.com/en-us/library/system.random.aspx" target="_blank">System.Random</a> class which can be used to generate random text.

In this example, we'll navigate to Bing.com and enter random text into the search box.

```C#
ActiveBrowser.NavigateTo("http://www.bing.com");
 
//Define the length of the text
int length = 8;
//Define the included characters
string charSet = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
 
Random random = new Random();
string randomText = new String(Enumerable.Repeat(charSet, length).Select(set => set[random.Next(set.Length)]).ToArray());
 
Find.ById<HtmlInputSearch>("sb_form_q").Text = randomText;
Find.ById<HtmlInputSubmit>("sb_form_go").Click();
```
```VB
ActiveBrowser.NavigateTo("http://www.bing.com")
 
'Define the length of the text
Dim length As Integer = 8
'Define the included characters
Dim charSet As String = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ"
 
Dim random As New Random()
Dim randomText As String = New [String](Enumerable.Repeat(charSet, length).[Select](Function([set]) [set](random.[Next]([set].Length))).ToArray())
 
Find.ById(Of HtmlInputSearch)("sb_form_q").Text = randomText
Find.ById(Of HtmlInputSubmit)("sb_form_go").Click()
```

__See also:__ Check our blog post <a href="https://www.telerik.com/blogs/how-can-i-input-random-data-into-my-test-run" target="_blank">**How to input random data in your test**</a>.

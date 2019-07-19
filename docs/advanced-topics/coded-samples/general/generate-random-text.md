---
title: Generate Random Text
page_title: Generate Random Text
description: "Generate Random Text in Test Studio coded test. Progress Telerik Testing Framework generate random text and enter it in search box."
previous_url: /user-guide/code-samples/general/generate-random-text.aspx, /user-guide/code-samples/general/generate-random-text
position: 1
---
#Generate Random Text#

I would like to generate random text in Test Studio. This text will be used in an input control or for a similar purpose.

##Solution##

There are two possible approaches: with or without code.

##Without code##

See our article on the <a href="/features/verifications/Extraction" target="_blank">Extraction</a> feature.

##With code##

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
 
Find.ById<HtmlInputText>("sb_form_q").Text = randomText;
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


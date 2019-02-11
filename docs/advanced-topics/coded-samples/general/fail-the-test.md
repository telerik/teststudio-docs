---
title: Fail the Test
page_title: Fail the Test
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# How to Fail the Test on a Condition #

There are two ways to accomplish this: *Assert* and *Throw New Exception* statements. Any unhandled exception within the coded step will fail the test step (and test) immediately.

## Assert Statements ##

This is most easily achieved with standard (and non-coded) <a href="/features/verifications/advanced-verification" target="_blank">Verification</a> and <a href="/features/verifications/Wait" target="_blank">Wait</a> steps. You can resort to code, however, for more in-depth scenarios. See <a href="/testing-framework/write-tests-in-code/intermediate-topics-wtc/html-control-suite-wtc/html-asserts" target="_blank">here</a> for more information.
 
The following code contains basic examples for demonstration purposes:

```C#
ActiveBrowser.NavigateTo("http://demos.telerik.com/aspnet-mvc/grid");
HtmlTable table = Find.ByExpression<HtmlTable>("id=Grid", "|", "tagIndex=table:1");
Assert.IsNotNull(table);
 
int r = table.Rows.Count;
Assert.AreEqual(r, 10);
Assert.IsTrue(table.InnerText.Contains("Mario"));
```
```VB
ActiveBrowser.NavigateTo("http://demos.telerik.com/aspnet-mvc/grid")
Dim table As HtmlTable = Find.ByExpression(Of HtmlTable)("id=Grid", "|", "tagIndex=table:1")
Assert.IsNotNull(table)
 
Dim r As Integer = table.Rows.Count
Assert.AreEqual(r, 10)
Assert.IsTrue(table.InnerText.Contains("Mario"))
```

## Throw New Exception ##

When an *Assert* statement is not appropriate, you can throw your own exception. In the example below, the *FileNotFoundException* will result in failure if the specified file does not exist on disk.

```C#
string fileName = "C:\\test.txt";
 
if (System.IO.File.Exists(fileName) == true)
{
    Log.WriteLine("File Exists: " + fileName);
}
else
{
    throw new System.IO.FileNotFoundException("File does not exist: ", fileName);
}
```
```VB
Dim fileName As String = "C:\test.txt"
 
If System.IO.File.Exists(fileName) = True Then
    Log.WriteLine("File Exists: " + fileName)
Else
    Throw New System.IO.FileNotFoundException("File does not exist: ", fileName)
End If
```
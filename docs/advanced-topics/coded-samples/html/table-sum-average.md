---
title: Table Sum & Average
page_title: Table Sum & Average
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/code-samples/html/table-sum-and-average.aspx, /user-guide/code-samples/html/table-sum-and-average
position: 1
---
# HTML Table Sum and Average

*I would like to get the sum and the average of the values in a certain column of an HTML table.*

## Solution

This is possible with a coded solution. The example below is against <a href="http://www.w3schools.com/html/html_tables.asp" target="_blank">this W3Schools site</a>.

```C#
HtmlTable table = Find.ByTagIndex<HtmlTable>("table", 0);
 
double r = table.Rows.Count;
double sum = 0;
 
for (int i = 0; i < r; i++)
{
    HtmlTableRow row = table.Rows[i];
    HtmlTableCell cell = row.Cells[1];
     
    string num = cell.TextContent.Substring(0, 2);
    int j = i + 1;
    Log.WriteLine("Row" + j.ToString() + ": " + num);
     
    double percent = Convert.ToDouble(num);
    sum  = sum + percent;
}
 
Log.WriteLine("Sum: " + sum.ToString());
double average = sum / r;
Log.WriteLine("Average: " + average.ToString());
Assert.IsTrue(sum == 90);
```
```VB
Dim table As HtmlTable = Find.ByTagIndex(Of HtmlTable)("table", 0)
 
Dim r As Double = table.Rows.Count
Dim sum As Double = 0
 
For i As Integer = 0 To r - 1
    Dim row As HtmlTableRow = table.Rows(i)
    Dim cell As HtmlTableCell = row.Cells(1)
 
    Dim num As String = cell.TextContent.Substring(0, 2)
    Dim j As Integer = i + 1
    Log.WriteLine("Row" + j.ToString() + ": " + num)
 
    Dim percent As Double = Convert.ToDouble(num)
    sum = sum + percent
Next
 
Log.WriteLine("Sum: " + sum.ToString())
Dim average As Double = sum / r
Log.WriteLine("Average: " + average.ToString())
Assert.IsTrue(sum = 90)
```



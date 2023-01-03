---
title: Table Sum & Average
page_title: Table Sum & Average - Test Studio Dev Documentation
description: Table Sum & Average
position: 1
---
# HTML Table Sum and Average #

*I would like to get the sum and the average of the values in a certain column of an HTML table.*

## Solution ##

This is possible with a coded solution. The example below is against <a href="http://www.w3schools.com/html/html_tables.asp" target="_blank">this W3Schools site</a>.

#### __[C#]__

    {{region }}

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
    {{endregion}}

#### __[VB]__

    {{region }}

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
    {{endregion}}



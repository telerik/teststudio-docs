---
title: Random Row
page_title: Random Row - Test Studio Dev Documentation
description: Random Row
position: 1
---
# Random Row from Excel Data Source

*Is there a way to data drive a step in a test script so that each time the script is run, the test step will select a random row from the Excel data source?*

## Solution

In code, generate a random number based on the number of rows. Then use the corresponding text from that row's cell in the applicable test step.

1.Create a basic test against Bing.com to enter a value in the Search field and click on the Search button.
2.Convert any of the recorded steps into code.
3.Enter the below code into the coded step. The **searchQuery.xlsx** Excel file contains five rows of data.

	* **Note:** Ensure you <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">Add an Assembly Reference</a> to *Microsoft.Office.Interop.Excel*. You can download a version of that file on Microsoft's website that matches your version of MS Office.

````C#
    Random random = new Random();
    int num = random.Next(1, 6);
    
    string input = @"C:\Data\searchQuery.xlsx";
    
    Microsoft.Office.Interop.Excel.Application app = new Microsoft.Office.Interop.Excel.Application();
    Microsoft.Office.Interop.Excel.Workbook inputBook = app.Workbooks.Open(input, 0, false, 5, "", "", false, Microsoft.Office.Interop.Excel.XlPlatform.xlWindows, "", true, false, 0, true, false, false);
    Microsoft.Office.Interop.Excel.Worksheet inputSheet = (Microsoft.Office.Interop.Excel.Worksheet)((inputBook.Worksheets).get_Item(1));
                
    string value = ((Microsoft.Office.Interop.Excel.Range)inputSheet.Cells[num, 1]).Text as string;
    app.Quit();
    app = null;
    
    Pages.Bing.SbFormQText.Text = value;
````
````VB
    Dim random As New Random()
    Dim num As Integer = random.[Next](1, 6)
    
    Dim input As String = "C:\Data\searchQuery.xlsx"
    
    Dim app As New Microsoft.Office.Interop.Excel.Application()
    Dim inputBook As Microsoft.Office.Interop.Excel.Workbook = app.Workbooks.Open(input, 0, False, 5, "", "", _
        False, Microsoft.Office.Interop.Excel.XlPlatform.xlWindows, "", True, False, 0, _
        True, False, False)
    Dim inputSheet As Microsoft.Office.Interop.Excel.Worksheet = DirectCast((inputBook.Worksheets.Item(1)), Microsoft.Office.Interop.Excel.Worksheet)
    
    Dim value As String = TryCast(DirectCast(inputSheet.Cells(num, 1), Microsoft.Office.Interop.Excel.Range).Text, String)
    app.Quit()
    app = Nothing
    
    Pages.Bing.SbFormQText.Text = value
````


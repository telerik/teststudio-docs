---
title: Random Row
page_title: Random Row
description: "Data drive a Test Studio test with random row from the data source for each test run execution iteration."
previous_url: /user-guide/code-samples/general/random-row.aspx, user-guide/code-samples/general/random-row.aspx, /user-guide/code-samples/general/random-row.aspx, user-guide/code-samples/general/random-row
position: 1
---
# Random Row from Excel Data Source

*Is there a way to data drive a step in a test script so that each time the script is run, the test step will select a random row from the Excel data source?*

## Solution

In code, generate a random number based on the number of rows. Then use the corresponding text from that row's cell in the applicable test step.

1. Create a basic test against Bing.com.

	![Basic test][1]

2. Right click step 2 and select **Edit in Code**.
3. Enter the below code into the coded step. The **searchQuery.xlsx** Excel file contains five rows of data.

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

## How to find and use Office PIA's without Visual Studio installed

1.&nbsp; Make sure that during the installation of Microsoft Office .NET Programmability Support was selected.

![.NET Programmability Support][2]

2.&nbsp; Then you will find the interop assemblies in the Windows Global Assembly Cache, specifically the folder: *C:\Windows\assembly\GAC_MSIL\Microsoft.Office.Interop.Excel\*

This is a hidden protected system folder which won't show up in an ordinary hard drive search. If you try to go to "C:\Windows\assembly" Windows recognizes this as a special folder and will show you the full contents of the GAC in a flattened list instead of the individual folders that make up the GAC.

[1]: /img/advanced-topics/coded-samples/general/random-row/fig1.png
[2]: /img/advanced-topics/coded-samples/general/random-row/fig2.png
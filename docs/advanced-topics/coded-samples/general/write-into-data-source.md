---
title: Write into Data Source
page_title: Write into Data Source
description: "Write into external Data Source Excel file during a Test Studio test run."
position: 1
---
# Write into Data Source

*I have a data driven test that checks whether a specific condition is met. I'd like to write a message into each corresponding row based on a condition.*

## Solution

This is possible with a coded solution. Here's an example:

Let's automate <a href="http://www.checkdomain.com/" target ="_blank">checkdomain.com</a> to check whether the domains listed in an Excel file are still available. We'll write Registered or Available into the first column of the Excel file for each domain name.

<table id="no-table" style="border:none;">
	<tr style="text-align: center; background-color: transparent; border:none;">
		<td style="text-align: center;">

![Before Test Run][1]
<strong>Before Test Run</strong>
</td>
		<td style="text-align: center;">

![After Test Run][2]
<strong>After Test Run</strong>
        </td>
	</tr>
</table>

Here's a sample test that automates this case:

![Test][3]

> **Note** Ensure you <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">Add an Assembly Reference</a> to Microsoft.Office.Interop.Excel. You can download a version of that file on Microsoft's website that matches your version of MS Office.

Here's the code from that sample:

````C#
    string dataSourcePath = this.ExecutionContext.DeploymentDirectory + @"\Data\domainResults.xlsx";
    string myPath = "C:\\domainResults.xlsx";

    if (!System.IO.File.Exists(myPath))
        {
        System.IO.File.Copy(dataSourcePath, myPath);
        }

    Microsoft.Office.Interop.Excel.Application excelApp = new Microsoft.Office.Interop.Excel.Application();
    Microsoft.Office.Interop.Excel.Workbook workbook = excelApp.Workbooks.Open(myPath);

    System.Threading.Thread.Sleep(1000);
    ActiveBrowser.RefreshDomTree();

    if (ActiveBrowser.ContainsText("already been registered"))
    {
        excelApp.Cells[Data.IterationIndex + 2 , 1] = "Registered";
    }
    if (ActiveBrowser.ContainsText("is still available"))
    {
        excelApp.Cells[Data.IterationIndex + 2 , 1] = "Available";
    }

    excelApp.Visible = true;
    excelApp.ActiveWorkbook.Save();

    workbook.Close(false, Type.Missing, Type.Missing);
    excelApp.Workbooks.Close();
    System.Runtime.InteropServices.Marshal.ReleaseComObject(workbook);

    excelApp.Quit();
    GC.Collect();
    System.Runtime.InteropServices.Marshal.ReleaseComObject(excelApp);
````
````VB
    Dim dataSourcePath As String = Me.ExecutionContext.DeploymentDirectory + "\Data\domainResults.xlsx"
    Dim myPath As String = "C:\domainResults.xlsx"
    
    If Not System.IO.File.Exists(myPath) Then
        System.IO.File.Copy(dataSourcePath, myPath)
    End If
    
    Dim excelApp As New Microsoft.Office.Interop.Excel.Application()
    Dim workbook As Microsoft.Office.Interop.Excel.Workbook = excelApp.Workbooks.Open(myPath)
    
    System.Threading.Thread.Sleep(1000)
    ActiveBrowser.RefreshDomTree()
    
    If ActiveBrowser.ContainsText("already been registered") Then
        excelApp.Cells(Data.IterationIndex + 2, 1) = "Registered"
    End If
    If ActiveBrowser.ContainsText("is still available") Then
        excelApp.Cells(Data.IterationIndex + 2, 1) = "Available"
    End If
    
    excelApp.Visible = True
    excelApp.ActiveWorkbook.Save()
    
    workbook.Close(False, Type.Missing, Type.Missing)
    excelApp.Workbooks.Close()
    System.Runtime.InteropServices.Marshal.ReleaseComObject(workbook)
    
    excelApp.Quit()
    GC.Collect()
    System.Runtime.InteropServices.Marshal.ReleaseComObject(excelApp)
````

## How to Find and Use Office PIA's

1.&nbsp; Make sure that during the installation of __Microsoft Office .NET Programmability Support__ was selected.

![.NET Programmability Support][4]

2.&nbsp; Then you will find the interop assemblies in the __Windows Global Assembly Cache__, specifically the folder: ___C:\Windows\assembly\GAC_MSIL\Microsoft.Office.Interop.Excel\___

This is a hidden protected system folder which won't show up in an ordinary hard drive search. If you try to go to "C:\Windows\assembly" Windows recognizes this as a special folder and will show you the full contents of the GAC in a flattened list instead of the individual folders that make up the GAC.

[1]: /img/advanced-topics/coded-samples/general/write-into-data-source/fig1.png
[2]: /img/advanced-topics/coded-samples/general/write-into-data-source/fig2.png
[3]: /img/advanced-topics/coded-samples/general/write-into-data-source/fig3.png
[4]: /img/advanced-topics/coded-samples/general/random-row/fig2.png

---
title: Write into Data Source
page_title: Write into Data Source | Test Studio Dev Documentation
description: Write into Data Source
position: 1
---
#Write into Data Source#

*I have a data driven test that checks whether a specific condition is met. I'd like to write a message into each corresponding row based on a condition.*

##Solution##

This is possible with a coded solution. Here's an example:

Let's automate <a href="http://www.checkdomain.com/" target ="_blank">checkdomain.com</a> to check whether the domains listed in an Excel file are still available. We'll write Registered or Available into the first column of the Excel file for each domain name.

<table id="no-table">
	<tr>
		<td>![Before Test Run][1] <br><br>**Before Test Run**</td>
		<td>![After Test Run][2] <br><br>**After Test Run**</td>
	</tr>
<table>

The test needs to navigate to checkdomain.com, enter the domain for the respective iteration and click on Submit. Add a coded step and insert the below code:

#### __[C#]__

    {{region }}

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
    {{endregion}}

#### __[VB]__

    {{region }} 

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
    {{endregion}}

**Note:** Add an Assembly Reference to Microsoft.Office.Interop.Excel.

[1]: /img/advanced-topics/coded-samples/general/write-into-data-source/fig1.png
[2]: /img/advanced-topics/coded-samples/general/write-into-data-source/fig2.png

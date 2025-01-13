---
title: Non-iterative Data Driving
page_title: Non-iterative Data Driving
description: "Test Studio - data drive a step in a test script to select a different sequential row from the data source by each test run. Non-iterative Data Driving in Test Studio"
previous_url: /user-guide/code-samples/general/non-iterative-data-driven-testing.aspx, /user-guide/code-samples/general/non-iterative-data-driven-testing
position: 1
---
# Non-iterative Data Driving

*Is there a way to data drive a step in a test script so that each time the script is run, the test step will select a different sequential row from the data source?*

## Solution

The solution is to save the number of the row into an XML file. Each time you execute the test, read the number of the row from the XML file and tell Test Studio to use this row from your data source.

1.&nbsp; Create an XML file which will contain the row number.

1.1 Right-click somewhere in the project folder and select **New > Text Document**. Rename it to "IterationIndex.xml".

1.2 Right-click on "IterationIndex.xml" > **Edit** and choose a program (Notepad, for example).

1.3 Write the following code into the file:

````XML
	<?xmlversion="1.0" encoding="UTF-8"?>
		<IterationValue> 
		<numVal>0</numVal>
	</IterationValue>
````

2.&nbsp; Create your data source, if you don't have one already. In my case this is an Excel file called "foo.xlsx" containing numbers from 1 to 20.

![File][1]

3.&nbsp; Open or create your project in Test Studio.

3.1 Start new project or open existing project.

3.2 Add the needed project references from <a href="/features/project-settings/script-options" target="_blank">Project Settings > Script Options</a> (learn how to add an assembly reference in the Standalone version <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">here</a>).
* *Microsoft.Office.Interop.Excel*
* *System.Xml*
* *System.Xml.Linq*

3.3 Create a new Web Test.

3.4 Add a <a href="/features/custom-steps/script-step" target="_blank">coded step</a> and click on the View Class button.

3.5 Create a method which will save the row number into the XML file:

````C#
public void SaveValue(int numVal)
{
    string path = @"C:\Box\NextRowOnEachRun\IterationValue.xml";
    XElement e = new XElement("IterationValue");
    e.Add(new XElement("numVal", numVal));
    e.Save(path);
}
````
````VB
Public Sub SaveValue(numVal As Integer)
	Dim path As String = "C:\Box\NextRowOnEachRun\IterationValue.xml"
	Dim e As New XElement("IterationValue")
	e.Add(New XElement("numVal", numVal))
	e.Save(path)
End Sub
````

3.6 Create a method which will load the row number from the XML file:

````C#
public int LoadValue()
{
    string path = @"C:\Box\NextRowOnEachRun\IterationValue.xml";
    XElement e = XElement.Load(path);
    int numVal = int.Parse(e.Element("numVal").Value);
    numVal++;

    return numVal;
}
````
````VB
Public Function LoadValue() As Integer
	Dim path As String = "C:\Box\NextRowOnEachRun\IterationValue.xml"
	Dim e As XElement = XElement.Load(path)
	Dim numVal As Integer = Integer.Parse(e.Element("numVal").Value)
	numVal += 1

	Return numVal
End Function
````

3.7 Create a method which will read the row from the Excel file:

````C#
public string ReadingExcel()
{
	int rowValue = LoadValue();
	string input = @"C:\Box\NextRowOnEachRun\foo.xlsx";
	Microsoft.Office.Interop.Excel.Application app = new Microsoft.Office.Interop.Excel.Application();
	Microsoft.Office.Interop.Excel.Workbook inputBook = app.Workbooks.Open(input, 0, false, 5, "", "", false, Microsoft.Office.Interop.Excel.XlPlatform.xlWindows, "", true, false, 0, true, false, false);
	Microsoft.Office.Interop.Excel.Worksheet inputSheet = (Microsoft.Office.Interop.Excel.Worksheet)((inputBook.Worksheets).get_Item(1));
	     
	string value = ((Microsoft.Office.Interop.Excel.Range)inputSheet.Cells[rowValue, 1]).Text as string; 
	app.Quit();
	app = null;
	 
	if (rowValue < 20)	{
	    SaveValue(rowValue);
	}
	else { 
        SaveValue(0); 
    }

	return value;
}
````
````VB
Public Function ReadingExcel() As String
	Dim rowValue As Integer = LoadValue()
	Dim input As String = "C:\Box\NextRowOnEachRun\foo.xlsx"
	Dim app As New Microsoft.Office.Interop.Excel.Application()
	Dim inputBook As Microsoft.Office.Interop.Excel.Workbook = app.Workbooks.Open(input, 0, False, 5, "", "", _
		False, Microsoft.Office.Interop.Excel.XlPlatform.xlWindows, "", True, False, 0, _
		True, False, False)
	Dim inputSheet As Microsoft.Office.Interop.Excel.Worksheet = DirectCast((inputBook.Worksheets).get_Item(1), Microsoft.Office.Interop.Excel.Worksheet)

	Dim value As String = TryCast(DirectCast(inputSheet.Cells(rowValue, 1), Microsoft.Office.Interop.Excel.Range).Text, String)
	app.Quit()
	app = Nothing

	If rowValue < 20 Then
		SaveValue(rowValue)
	Else
		SaveValue(0)
	End If

	Return value
End Function
````

See <a href="http://screencast.com/t/bqt6zXOj" target="_blank">this video</a> to see how this sample works.

## How to find and use Office PIA's without Visual Studio installed

1.&nbsp; Make sure that during the installation of Microsoft Office .NET Programmability Support was selected.

![.NET Programmability Support][2]

2.&nbsp; Then you will find the interop assemblies in the Windows Global Assembly Cache, specifically the folder: *C:\Windows\assembly\GAC_MSIL\Microsoft.Office.Interop.Excel\*

This is a hidden protected system folder which won't show up in an ordinary hard drive search. If you try to go to "C:\Windows\assembly" Windows recognizes this as a special folder and will show you the full contents of the GAC in a flattened list instead of the individual folders that make up the GAC.

[1]: /img/advanced-topics/coded-samples/general/non-iterative-data-driving/fig1.png
[2]: /img/advanced-topics/coded-samples/general/random-row/fig2.png

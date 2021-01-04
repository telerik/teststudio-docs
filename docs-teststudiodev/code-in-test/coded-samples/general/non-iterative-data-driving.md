---
title: Non-iterative Data Driving
page_title: Non-iterative Data Driving | Test Studio Dev Documentation
description: Non-iterative Data Driving
position: 1
---
#Non-iterative Data Driving#

*Is there a way to data drive a step in a test script so that each time the script is run, the test step will select a different sequential row from the data source?*

##Solution##

The solution is to save the number of the row into an XML file. Each time you execute the test, read the number of the row from the XML file and tell Test Studio to use this row from your data source.

1.&nbsp; Create an XML file which will contain the row number.

1.1 Right-click somewhere in the project folder and select **New > Text Document**. Rename it to "IterationIndex.xml".

1.2 Right-click on "IterationIndex.xml" > **Edit** and choose a program (Notepad, for example).

1.3 Write the following code into the file:

```XML
	<?xmlversion="1.0" encoding="UTF-8"?>
		<IterationValue> 
		<numVal>0</numVal>
	</IterationValue>
```

2.&nbsp; Create your data source, if you don't have one already. In my case this is an Excel file called "foo.xlsx" containing numbers from 1 to 20.

![File][1]

3.&nbsp; Open or create your project in Test Studio.

3.1 Start new project or open existing project.

3.2 Add the needed project references: 

* *Microsoft.Office.Interop.Excel*
* *System.Xml*
* *System.Xml.Linq*

3.3 Create a new Web Test.

3.4 Add a <a href="/code-in-test/features-in-code#Coded-Step" target="_blank">coded step</a> and click on the View Class button.

3.5 Create a method which will save the row number into the XML file:

#### __[C#]__

	{{region }}

	public void SaveValue(int numVal)
	{
		string path = @"C:\Box\NextRowOnEachRun\IterationValue.xml";
		XElement e = new XElement("IterationValue");
		e.Add(new XElement("numVal", numVal));
		e.Save(path);
	}
	{{endregion}}

#### __[VB]__

	{{region }}

	Public Sub SaveValue(numVal As Integer)
		Dim path As String = "C:\Box\NextRowOnEachRun\IterationValue.xml"
		Dim e As New XElement("IterationValue")
		e.Add(New XElement("numVal", numVal))
		e.Save(path)
	End Sub
	{{endregion}}

3.6 Create a method which will load the row number from the XML file:

#### __[C#]__

	{{region }}

	public int LoadValue()
	{
		string path = @"C:\Box\NextRowOnEachRun\IterationValue.xml";
		XElement e = XElement.Load(path);
		int numVal = int.Parse(e.Element("numVal").Value);
		numVal++;

		return numVal;
	}
	{{endregion}}

#### __[VB]__

	{{region }}

	Public Function LoadValue() As Integer
		Dim path As String = "C:\Box\NextRowOnEachRun\IterationValue.xml"
		Dim e As XElement = XElement.Load(path)
		Dim numVal As Integer = Integer.Parse(e.Element("numVal").Value)
		numVal += 1

		Return numVal
	End Function
	{{endregion}}

3.7 Create a method which will read the row from the Excel file:

#### __[C#]__

	{{region }}

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
	{{endregion}}

#### __[VB]__

	{{region }}

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
	{{endregion}}

[1]: images/non-iterative-data-driving/fig1.png
---
title: Execution Extensions
page_title: Execution Extension
description: "Test Studio has enhanced extensibility support for test execution. Integrate Test Studio better into your environment that contains custom results reporting and code defect tracking. Extend the Test Studio test execution with custom coded solutions in Execution Extension"
previous_url: /user-guide/code-samples/general/execution-extensions.aspx, /user-guide/code-samples/general/execution-extensions
position: 1
---
# Execution Extension 

Test Studio has enhanced extensibility support for test execution. This model helps integrate Test Studio better into your environment that contains custom results reporting and code defect tracking.

To demonstrate the execution extensibility model, let's build a simple Execution Extension to Test Studio that writes the results of a test list to a text file.

1.&nbsp; Create a Class Library project in Visual Studio. This example uses C#.

2.&nbsp; Add references to three DLLs from **C:\Program Files (x86)\Progress\Test Studio\Bin\**

 - ArtOfTest.WebAii.dll

 - ArtOfTest.WebAii.Design.dll

 - Telerik.TestStudio.Interfaces.dll

Also add the following **.NET** references (these are required for the demonstrated code):

 - System.Runtime.Serialization

 - System.Windows.Forms

3.&nbsp; Add the following using statements to the class file:

	
```C#
using System.IO;
using System.Data;
using System.Data.OleDb;
using System.Windows.Forms;
using ArtOfTest.WebAii.Design.Execution;
```
```VB
Imports System.IO
Imports System.Data
Imports System.Data.OleDb
Imports System.Windows.Forms
Imports ArtOfTest.WebAii.Design.Execution
```

4.&nbsp; The *ArtOfTest.WebAii.Design.Execution* namespace contains an IExecutionExtension that the class library needs to inherit and implement:

```C#
namespace ClassLibrary1
{
	public class Class1 : IExecutionExtension
	{
	}
}
```
```VB
Namespace ClassLibrary1
	Public Class Class1
		Implements IExecutionExtension
	End Class
End Namespace
```

5.&nbsp; Right click on **IExecutionExtension** and select **Implement Interface > Implement Interface**. This displays all the methods and notifications exposed by Test Studio. Here are definitions for each **IExecutionExtension** member:

 - The **OnInitializeDataSource()** function __cannot__ be left empty and should return **null** if not being used. Test Studio takes into consideration only the first non null data table (if you are using more than one plugin, the first one to return non null data table is used).

 - The rest of the functions, which you're not using, should be left empty (remove *throw new NotImplementedException*).


```C#
namespace ClassLibrary1
{
    public class Class1 : IExecutionExtension
    {
        #region IExecutionExtension Members

        // After each test is completed, ArtOfTest.Runner calls this method.
        // <param name="executionContext">The execution context the test is running under.</param>
        // <param name="result">The actual result of the test.</param>
        public void OnAfterTestCompleted(ExecutionContext executionContext, TestResult result)
        {
            // Your custom implementation here
        }

        // After the test list is completed, the Scheduling Server calls this method.
        // <param name="result">The entire RunResult object.</param>
        public void OnAfterTestListCompleted(RunResult result)
        {
            // Your custom implementation here.
        }

        // Before the test list begins execution, the Scheduling Server calls this method.
        // <param name="list">The test list that is about to start.</param>
        public void OnBeforeTestListStarted(TestList list)
        {
            // Your custom implementation here
        }

        // Before a test is about to start, ArtOfTest.Runner calls this method.
        // <param name="executionContext">The execution context the test is running under.</param>
        // <param name="test">The test we are about to start running.</param>
        public void OnBeforeTestStarted(ExecutionContext executionContext, ArtOfTest.WebAii.Design.ProjectModel.Test test)
        {
            // Your custom implementation here
        }

        // Use this to return your own data source.
        // <param name="executionContext">The execution context.</param>
        public System.Data.DataTable OnInitializeDataSource(ExecutionContext executionContext)
        {
            // Your custom implementation here
            return null;
        }

        // Called only on a step failure.
        // <param name="executionContext">The execution context a test is running under.</param>
        // <param name="stepResult">The step result that just failed.</param>
        public void OnStepFailure(ExecutionContext executionContext, ArtOfTest.WebAii.Design.AutomationStepResult stepResult)
        {
            // Your custom implementation here
        }

        #endregion
    }
}
```
```VB
Namespace ClassLibrary1
	Public Class Class1
		Implements IExecutionExtension
		#Region "IExecutionExtension Members"

		' After each test is completed, ArtOfTest.Runner calls this method.
		' <param name="executionContext">The execution context the test is running under.</param>
		' <param name="result">The actual result of the test.</param>
		Public Sub OnAfterTestCompleted(executionContext As ExecutionContext, result As TestResult)
			' Your custom implementation here
		End Sub

		' After the test list is completed, the Scheduling Server calls this method.
		' <param name="result">The entire RunResult object.</param>
		Public Sub OnAfterTestListCompleted(result As RunResult)
			' Your custom implementation here.
		End Sub

		' Before the test list begins execution, the Scheduling Server calls this method.
		' <param name="list">The test list that is about to start.</param>
		Public Sub OnBeforeTestListStarted(list As TestList)
			' Your custom implementation here
		End Sub

		' Before a test is about to start, ArtOfTest.Runner calls this method.
		' <param name="executionContext">The execution context the test is running under.</param>
		' <param name="test">The test we are about to start running.</param>
		Public Sub OnBeforeTestStarted(executionContext As ExecutionContext, test As ArtOfTest.WebAii.Design.ProjectModel.Test)
			' Your custom implementation here
		End Sub

		' Use this to return your own data source.
		' <param name="executionContext">The execution context.</param>
		Public Function OnInitializeDataSource(executionContext As ExecutionContext) As System.Data.DataTable
			' Your custom implementation here
			Return Nothing
		End Function

		' Called only on a step failure.
		' <param name="executionContext">The execution context a test is running under.</param>
		' <param name="stepResult">The step result that just failed.</param>
		Public Sub OnStepFailure(executionContext As ExecutionContext, stepResult As ArtOfTest.WebAii.Design.AutomationStepResult)
			' Your custom implementation here
		End Sub

		#End Region
	End Class
End Namespace
```

A few notes about the code above:
	
 - **ExecutionContext** - The context is an object that gives you mostly all other objects in context of the current execution. For example, from this object you can access the run-time Manager object, the ActiveBrowser, the Log object, the Find object, etc. These are the run-time objects are used to execute your test. If you use the <a href="/testing-framework/getting-started" target="_blank">Telerik Testing Framework</a> or coded steps, you are familiar with these objects. It also exposes the ExecutionContext.ExecutingTestAsStep property, which distinguishes between tests being run normally or as a subtest.

 - **Result objects** - RunResult contains a list of “TestResult” objects for each test that is executed. Each TestResult has an AutomationStepResult list that represents the result for each step that executed. You have access to all the metadata of the execution so you can generate your own reports.

 - **OnInitializeDataSource** - Bind a test to a custom data source by returning a DataTable from this method. Use that DataTable to data drive the test. As of internal build 2012.1.816, if this method returns a DataTable, it will be used regardless if the test is data bound or not. For older versions, it will only get called if the test is bound to a data source or if the InheritParentDataSource <a href="/features/test-maintenance/test-properties-standalone" target="_blank">Test Property</a> is checked.

 - **Scope of Variables** - Notice that OnBeforeTestListStarted() and OnAfterTestListCompleted() are called by the Scheduling Server, while OnBeforeTestExecution and OnAfterTestExecution are called by ArtOfTest.Runner on the Execution Server. This means that if you initialize variables inside of OnBeforeTestListStarted or OnAfterTestListCompleted, you will not reliably have access to these variables inside OnBeforeTestExecution or OnAfterTestExecution, and vice versa. To use the same variables in both sets of methods, you can <a href="http://msdn.microsoft.com/en-us/library/dd460709%28v=vs.110%29.aspx" target="_blank">lazy initialize</a> the variables to ensure that they are not null.

6.&nbsp; For the first example, we'll add code to the **OnAfterTestListCompleted** method to write the result of a test list as a basic string to a text file:

	
```C#
public void OnAfterTestListCompleted(RunResult result)
{
	string msg = string.Format("TestList '{0}' completed on '{1}'. ({2}/{3}) Passed", result.Name, result.EndTime, result.PassedCount, result.TestResults.Count);
	StreamWriter file = new StreamWriter("c:\\test-list-results.txt");
	file.WriteLine(msg);
	file.Close();
}
```
```VB
Public Sub OnAfterTestListCompleted(result As RunResult)
	Dim msg As String = String.Format("TestList '{0}' completed on '{1}'. ({2}/{3}) Passed", result.Name, result.EndTime, result.PassedCount, result.TestResults.Count)
	Dim file As New StreamWriter("c:\test-list-results.txt")
	file.WriteLine(msg)
	file.Close()
End Sub
```

7.&nbsp; Compile the class library.

8.&nbsp; Deploy the extension by copying the DLL from the **%Project Folder%\ClassLibrary1\ClassLibrary1\bin\Debug** to the following directory:

 - **C:\Program Files (x86)\Progress\Test Studio\Bin\Plugins\**

9.&nbsp; Now execute a test list. The result string is written to the defined text file.

## Example of OnInitializeDataSource Method

Let's see another example using the **OnInitializeDataSource** method. This assumes that your test is already <a href="/features/data-driven-testing/add-data-source" target="_blank">binded</a> to an Excel file, and each Excel file has matching column names.

1.&nbsp; Add the following code to that method:

```C#
public System.Data.DataTable OnInitializeDataSource(ExecutionContext executionContext)
{
    System.Data.DataTable table = null;
    var thread = new System.Threading.Thread(obj =>
    {
        try
        {
            System.Windows.Forms.OpenFileDialog ofd = new System.Windows.Forms.OpenFileDialog();
            ofd.Title = "Open Excel File";
            if (ofd.ShowDialog() == DialogResult.OK)
            {
                string excel = ofd.FileName;
                DataSet foo = ImportExcelXLS(excel, true);
                table = (foo.Tables[0]);
            }
        }
        catch (Exception ex)
        {
            NativeWindow a = new NativeWindow();
            a.AssignHandle(ArtOfTest.WebAii.Core.Manager.Current.ActiveBrowser.Window.Handle);
            MessageBox.Show(a, ex.Message);
        }
    });
    thread.SetApartmentState(System.Threading.ApartmentState.STA);
    thread.Start();
    thread.Join();
    return table;
}
```
```VB
Public Function OnInitializeDataSource(executionContext As ExecutionContext) As System.Data.DataTable
	Dim table As System.Data.DataTable = Nothing
	Dim thread = New System.Threading.Thread(Function(obj) 
	Try
		Dim ofd As New System.Windows.Forms.OpenFileDialog()
		ofd.Title = "Open Excel File"
		If ofd.ShowDialog() = DialogResult.OK Then
			Dim excel As String = ofd.FileName
			Dim foo As DataSet = ImportExcelXLS(excel, True)
			table = (foo.Tables(0))
		End If
	Catch ex As Exception
		Dim a As New NativeWindow()
		a.AssignHandle(ArtOfTest.WebAii.Core.Manager.Current.ActiveBrowser.Window.Handle)
		MessageBox.Show(a, ex.Message)
	End Try

End Function)
	thread.SetApartmentState(System.Threading.ApartmentState.STA)
	thread.Start()
	thread.Join()
	Return table
End Function
```

2.&nbsp; Now add the following *ImportExcelXLS* method within the same public class:

```C#
private static DataSet ImportExcelXLS(string FileName, bool hasHeaders)
{
    string HDR = hasHeaders ? "Yes" : "No";
    string strConn = null;
    if (FileName.Substring(FileName.LastIndexOf('.')).ToLower() == ".xlsx")
    {
        strConn = "Provider=Microsoft.ACE.OLEDB.12.0;Data Source=" + FileName + ";Extended Properties=\"Excel 12.0;HDR=" + HDR + ";IMEX=1\"";
    }
    else
    {
        strConn = "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=" + FileName + ";Extended Properties=\"Excel 8.0;HDR=" + HDR + ";IMEX=1\"";
    }

    DataSet output = new DataSet();

    using (OleDbConnection conn = new OleDbConnection(strConn))
    {
        conn.Open();

        DataTable schemaTable = conn.GetOleDbSchemaTable(
          OleDbSchemaGuid.Tables, new object[] { null, null, null, "TABLE" });

        foreach (DataRow schemaRow in schemaTable.Rows)
        {
            string sheet = schemaRow["TABLE_NAME"].ToString();

            OleDbCommand cmd = new OleDbCommand("SELECT * FROM [" + sheet + "]", conn);
            cmd.CommandType = CommandType.Text;

            DataTable outputTable = new DataTable(sheet);
            output.Tables.Add(outputTable);
            new OleDbDataAdapter(cmd).Fill(outputTable);
        }
    }
    return output;
}
```
```VB
Private Shared Function ImportExcelXLS(FileName As String, hasHeaders As Boolean) As DataSet
	Dim HDR As String = If(hasHeaders, "Yes", "No")
	Dim strConn As String = Nothing
	If FileName.Substring(FileName.LastIndexOf("."C)).ToLower() = ".xlsx" Then
		strConn = (Convert.ToString((Convert.ToString("Provider=Microsoft.ACE.OLEDB.12.0;Data Source=") & FileName) + ";Extended Properties=""Excel 12.0;HDR=") & HDR) + ";IMEX=1"""
	Else
		strConn = (Convert.ToString((Convert.ToString("Provider=Microsoft.Jet.OLEDB.4.0;Data Source=") & FileName) + ";Extended Properties=""Excel 8.0;HDR=") & HDR) + ";IMEX=1"""
	End If

	Dim output As New DataSet()

	Using conn As New OleDbConnection(strConn)
		conn.Open()

		Dim schemaTable As DataTable = conn.GetOleDbSchemaTable(OleDbSchemaGuid.Tables, New Object() {Nothing, Nothing, Nothing, "TABLE"})

		For Each schemaRow As DataRow In schemaTable.Rows
			Dim sheet As String = schemaRow("TABLE_NAME").ToString()

			Dim cmd As New OleDbCommand((Convert.ToString("SELECT * FROM [") & sheet) + "]", conn)
			cmd.CommandType = CommandType.Text

			Dim outputTable As New DataTable(sheet)
			output.Tables.Add(outputTable)
			New OleDbDataAdapter(cmd).Fill(outputTable)
		Next
	End Using
	Return output
End Function
```

3.&nbsp; Rebuild the class library, copy the resulting DLL file, and paste it into the Plugins folder (overwriting the existing file).

4.&nbsp; When you execute a data driven test, you are prompted to select an Excel file (.xls or .xlsx). You have two choices:

 - Select a new Excel file and press OK.

 - Press Cancel to use the original data source.

## Remote Execution Behavior

It was mentioned above in terms of the scope for variables, that some methods are executed only on the machine, where the scheduling server for the current remote setup is located. It is important to know how will the execution extension behave in case of different execution scenarios. For all of the listed configurations the built custom dll file needs to be copied in the **C:\Program Files (x86)\Progress\Test Studio\Bin\Plugins\** folder on each remote machine.

### Scheduling Server Setup

This feature allows only one machine to have a running <a href="/features/scheduling-test-runs/create-scheduling-server" target="_blank">scheduling server</a> and multiple machines to be connected to it and serve as <a href="/features/scheduling-test-runs/create-execution-server" target="_blank">execution clients</a>. In this case **the complete set of execution extension methods will be executed on the scheduling server machine** only.

All execution machines will **not execute *OnBeforeTestListStarted()* and _OnAfterTestListCompleted()_** and will only recognize the *OnBeforeTestStarted()* and *OnAfterTestCompleted()*.

### CI Setup

In the context of <a href="/advanced-topics/build-server/continious-integration-overview" target="_blank">Continuous Integration</a> setup - running test lists using the <a href="/features/test-runners/artoftest-runner" target="_blank">ArtOfTest.Runner.exe</a> with **the *list* option, will execute all methods** in the extension.

However, if using the *test* option to run a single test, the agent will **not execute *OnBeforeTestListStarted()* and _OnAfterTestListCompleted()_** and will only recognize the *OnBeforeTestStarted()* and *OnAfterTestCompleted()*.
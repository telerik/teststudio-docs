---
title: Access Performance Data
page_title: Access Performance Data
description: "access the results of a performance test in code in Test Studio coded step."
position: 1
---
#Access Performance Data#

In order to access the results of a performance test in code, it will be necessary to create an <a href="execution-extensions" target="_blank">execution extension</a> library. The approach to this problem is to use a <a href="/getting-started/test-execution/test-lists-type-standalone#Performance" target="_blank">performance test list</a> to execute one or many performance tests. Then at the end of the execution to collect the data from each one of the performance test results files.

### Preconditions

1. Add a reference to the VS project for the following library located in product installation **\bin** folder:
	- Telerik.TestStudio.Interfaces.dll
1. Include in the project listed below namespaces:
	- ArtOfTest.WebAii.Design.Execution.Profiler
	- ArtOfTest.WebAii.Design.Execution.Profiler.Storage
1. If not present - create *C:\temp* directory, where the new result file will be placed

### Sample Code

The following extension class will store the full path to each performance test result and its ID in a Dictionary data structure. This structure will be updated after each test completion in the *OnAfterTestCompleted()* method. Then at the end of the test list execution in *OnAfterTestListCompleted()* method - all files will be opened one by one to collect necessary data and save it in *C:\temp\lastPerformanceResults.txt* file.

```C#
namespace ExecutionExtensionSample
{
    using System.Collections.Generic;
    using System.Data;
    using ArtOfTest.WebAii.Design.Execution;
    using ArtOfTest.WebAii.Design;
    using ArtOfTest.WebAii.Design.ProjectModel;
    // namespaces to include:
    using ArtOfTest.WebAii.Design.Execution.Profiler;
    using ArtOfTest.WebAii.Design.Execution.Profiler.Storage;

    public class MyExecutionExtension : IExecutionExtension
    {
        // initialize the variable to save test ID and full path to the result file
        private Dictionary<System.Guid, string> testIdAndPath = new Dictionary<System.Guid, string>();

        public void OnAfterTestCompleted(ExecutionContext executionContext, TestResult result)
        {
            // add each test ID and result file path to the dictionary 
            testIdAndPath.Add(System.Guid.Parse(result.TestId.ToString()), result.ProfilerResultsPath);
        }

        public void OnAfterTestListCompleted(RunResult result)
        {
            // 5 sec timeout to let the last result file to be created - extend it if necessary
            System.Threading.Thread.Sleep(5000);

            // open a file stream writer to collect the data from results in a new file
            using (System.IO.StreamWriter file = new System.IO.StreamWriter(@"C:\temp\lastPerformanceResults.txt", true))
            {
                // loop over each result file 
                foreach (var resultFile in this.testIdAndPath)
                {
                    file.WriteLine("Result ID: " + resultFile.Key);
                    file.WriteLine("File Path: " + resultFile.Value);

                    // load the ProfileResultFile
                    ProfilerResultsFile resultsFile = ProfilerResultsFile.Load(resultFile.Key, resultFile.Value);

                    // print each step values in the new result file
                    foreach (ProfilerTestStep step in resultsFile.Steps)
                    {
                        // set here the necessary step property in [] to save in the new result file
                        file.WriteLine("Some Property Value: " + step.[..].ToString());
                    }
                }
            }
        }

        public void OnBeforeTestListStarted(TestList list)
        {
        }

        public void OnBeforeTestStarted(ExecutionContext executionContext, Test test)
        {
        }

        public DataTable OnInitializeDataSource(ExecutionContext executionContext)
        {
            return null;
        }

        public void OnStepFailure(ExecutionContext executionContext, AutomationStepResult stepResult)
        {
        }
    }
}
```
```VB
Imports System.Collections.Generic
Imports System.Data
Imports ArtOfTest.WebAii.Design.Execution
Imports ArtOfTest.WebAii.Design
Imports ArtOfTest.WebAii.Design.ProjectModel
Imports ArtOfTest.WebAii.Design.Execution.Profiler
Imports ArtOfTest.WebAii.Design.Execution.Profiler.Storage

Namespace ExecutionExtensionSample

    Public Class MyExecutionExtension
        Inherits IExecutionExtension

        Private testIdAndPath As Dictionary(Of System.Guid, String) = New Dictionary(Of System.Guid, String)()

        Public Sub OnAfterTestCompleted(ByVal executionContext As ExecutionContext, ByVal result As TestResult)
            testIdAndPath.Add(System.Guid.Parse(result.TestId.ToString()), result.ProfilerResultsPath)
        End Sub

        Public Sub OnAfterTestListCompleted(ByVal result As RunResult)
            System.Threading.Thread.Sleep(5000)
            Using file As System.IO.StreamWriter = New System.IO.StreamWriter("C:\temp\lastPerformanceResults.txt", True)
                For Each resultFile In Me.testIdAndPath
                    file.WriteLine("Result ID: " & resultFile.Key)
                    file.WriteLine("File Path: " & resultFile.Value)
                    Dim resultsFile As ProfilerResultsFile = ProfilerResultsFile.Load(resultFile.Key, resultFile.Value)
                    For Each [step] As ProfilerTestStep In resultsFile.Steps
                        file.WriteLine("Some Property Value: " & [step].....ToString())
                    Next
                Next
            End Using
        End Sub

        Public Sub OnBeforeTestListStarted(ByVal list As TestList)
        End Sub

        Public Sub OnBeforeTestStarted(ByVal executionContext As ExecutionContext, ByVal test As Test)
        End Sub

        Public Function OnInitializeDataSource(ByVal executionContext As ExecutionContext) As DataTable
            Return Nothing
        End Function

        Public Sub OnStepFailure(ByVal executionContext As ExecutionContext, ByVal stepResult As AutomationStepResult)
        End Sub
    End Class
End Namespace
```

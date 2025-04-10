---
title: Set Test Execution Time Limit 
page_title: Set Test Execution Time Limit 
description: In some automation scenarios it is necessary to limit a single test execution to a certain duration. How to limit the duration of test run. 

position: 1
---
## Set Test Execution Time Limit

In some automation scenarios it is necessary to limit a single test execution to a certain time frame. That is possible if the following approach is used. In an <a href="/advanced-topics/coded-samples/general/execution-extensions" target="_blank">execution extension</a> library is set timer that is re-set each time the new test starts. If the time expired before the timer is re-set - all processes related to test execution are killed. This will ensure if a test takes more than initially defined time interval to stop its execution and continue with the next test. Below is given sample execution extension library with time frame set to 5 minutes.


````C#
	
public class ExecutionTimeout : IExecutionExtension
{
    System.Timers.Timer stopWatch;
    int timeout = 300000;

    // After each test is completed, ArtOfTest.Runner calls this method.
    // <param name="executionContext">The execution context the test is running under.</param>
    // <param name="result">The actual result of the test.</param>
    public void OnAfterTestCompleted(ExecutionContext executionContext, TestResult result)
    {
        if (!executionContext.ExecutingTestAsStep && !executionContext.RunFromHereStepExecuted)
        {
            stopWatch.Stop();
        }
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
        Console.WriteLine(" --- Timer is ON --- ");
        if (!executionContext.ExecutingTestAsStep && !executionContext.RunFromHereStepExecuted)
        {
            stopWatch = new System.Timers.Timer(timeout);
            stopWatch.Elapsed += StopWatchElapsed;
            stopWatch.Start();
        }
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

    private void StopWatchElapsed(object sender, System.Timers.ElapsedEventArgs e)
    {
        var procsToKill = new string[] { "iexplore", "Chrome", "Safari", "firefox" };

        foreach (string pr in procsToKill)
        {
            KillProcessByName(pr);
            Console.WriteLine(" --- The process '{0}' is terminated --- ", pr);
        }
    }

    public void KillProcessByName(string procname)
    {
        Process[] processes = Process.GetProcessesByName(procname);

        foreach (Process process in processes)
        {
            try
            {
               process.Kill();
            }
            catch (Exception ex)
            {
                Console.Write(ex.ToString());
            }
        }
    }
}
````
````VB

Public Class ExecutionTimeout
	Implements IExecutionExtension
	Private stopWatch As System.Timers.Timer
	Private timeout As Integer = 300000

	' After each test is completed, ArtOfTest.Runner calls this method.
	' <param name="executionContext">The execution context the test is running under.</param>
	' <param name="result">The actual result of the test.</param>
	Public Sub OnAfterTestCompleted(executionContext As ExecutionContext, result As TestResult)
		If Not executionContext.ExecutingTestAsStep AndAlso Not executionContext.RunFromHereStepExecuted Then
			stopWatch.[Stop]()
		End If
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
		Console.WriteLine(" --- Timer is ON --- ")
		If Not executionContext.ExecutingTestAsStep AndAlso Not executionContext.RunFromHereStepExecuted Then
			stopWatch = New System.Timers.Timer(timeout)
			AddHandler stopWatch.Elapsed, AddressOf StopWatchElapsed
			stopWatch.Start()
		End If
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

	Private Sub StopWatchElapsed(sender As Object, e As System.Timers.ElapsedEventArgs)
		Dim procsToKill = New String() {"iexplore", "Chrome", "Safari", "firefox"}

		For Each pr As String In procsToKill
			KillProcessByName(pr)
			Console.WriteLine(" --- The process '{0}' is terminated --- ", pr)
		Next
	End Sub

	Public Sub KillProcessByName(procname As String)
		Dim processes As Process() = Process.GetProcessesByName(procname)

		For Each process__1 As Process In processes
			Try
				process__1.Kill()
			Catch ex As Exception
				Console.Write(ex.ToString())
			End Try
		Next
	End Sub
End Class

````

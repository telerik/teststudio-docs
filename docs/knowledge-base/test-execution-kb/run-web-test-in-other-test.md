---
title: Run a Web Test within Other Test
page_title: Run a Web Test within Other Test
description: Execute a Test Studio web test as part of any other test in code. 
position: 1
---
#How to Run a Web Test within Other Test

This scenario makes sense for example when there is a web test or test list located in another project that has to be executed in the current project. Such approach has to be implemented with caution though. The external test would be launched as separate to the main process and in case of its failure there could be not enough information on the reasons that happen. If the test is located in the same project then it could be executed <a href="/features/custom-steps/test-as-step" target="_blank">as a step</a> or in a <a href="/features/coded-steps/coded-step" target="_blank">coded step</a> using the expression: this.ExecuteTest("SampleTest.tstest").

To run an external test it has to be in a coded step. There a separate system process has to be started. The following code will run the ArtOfTest.Runner.exe with argument - a test list containing single or multiple tests to be executed. All possible arguments are listed in this <a href="/features/test-runners/artoftest-runner" target="_blank">article</a>.


```C#
    
// references to the project
using System.IO;
using System.Diagnostics;
	
[CodedStep(@"Run External Web Test")]
public void Run_Web_Test_CodedStep()
{
	// initialize new system process
	Process runWebTest = new Process();
	
	// define the process name to be started
    runWebTest.StartInfo.FileName = @"[PathToExecutable]\ArtOfTest.Runner.exe";
		
    // set the arguments
    runWebTest.StartInfo.Arguments = @" list=[PathToTheTestList]\SampleTestList.aiilist";
		
    // run the process
    runWebTest.Start();
		
    // wait until the test return an exit code
    runWebTest.WaitForExit();
		
    // get the exit code from the executed process 
    int exitCode = runWebTest.ExitCode;
		
    // check if this test step pass or fail. If return 0 - process complete normally, else - process fould.
    Assert.AreEqual(exitCode, 0);
}
    
```
```VB
    
Imports System.IO
Imports System.Diagnostics
	
<CodedStep("Run External Web Test")> _
   Public Sub Run_Web_Test_CodedStep()
	
	Dim runWebTest As New Process()
		
	runWebTest.StartInfo.FileName = "[PathToExecutable]\Telerik.MobileTesting.Runner.exe"
		
	runWebTest.StartInfo.Arguments = " list=[PathToTheTestList]\SampleTestList.aiilist"
		
	runWebTest.Start()
		
	runWebTest.WaitForExit()
		
	Dim exitCode As Integer = runWebTest.ExitCode		
		
	Assert.AreEqual(exitCode, 0)
	
End Sub
    
```

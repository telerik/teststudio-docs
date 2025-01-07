---
title: Run a Mobile Test within a Web Test
page_title: Run a Mobile Test within a Web Test
description: Run mobile Test within a Web Test with Test Studio. Execute mobile test as step in a web test in Test Studio. Run Mobiletests as part of a Test Studio web project. Integrate Mobile testing with Test Studio web tests. 
position: 1
publish: false
---
#How to Run a Mobile Test within a Web Test

A common testing scenario is to have a web based application that could interact both with web and mobile users. There is a way to develop and execute a web test that at certain step runs a mobile test. To complete that the following initial conditions are needed:

 - web test,
 - mobile test,
 - Mobile Testing Desktop Application running - it will run the Message Server.

Next step is to create a coded step in the web test that will start a system process. The following code will run the Telerik.MobileTesting.Runner.exe with arguments: 

 - Message Server's url and port
 - mobile project path
 - the relative path to and name of the mobile test

The code will wait for the end of the mobile test execution. After the process ends - the exit code is placed in assert statement to check if this step passed or failed depending on the mobile test status.

Detailed results of the mobile test execution will be present in the mobile project folder (*Results* sub-folder), where the mobile test is located. 

```C#
// Need to include the references:
using System.IO;
using System.Diagnostics;

[CodedStep(@"Run Mobile Test")]
public void Run_Mobile_Test_CodedStep()
{
    // initialize new system process
    Process runMobileTest = new Process();

    // define the process name to be started
    runMobileTest.StartInfo.FileName = @"[PathToExecutable]\Telerik.MobileTesting.Runner.exe";

    // set the arguments
    runMobileTest.StartInfo.Arguments = @"/C " +  " /msgServer=\"ws://localhost:8084\" /project=\"[PathToTheProject]\\DemoMobileProject\" /test=\"Web Tests\"\\Login.mttest";

    // run the process
    runMobileTest.Start();

    // wait until the test return an exit code
    runMobileTest.WaitForExit();

    // get the exit code from the executed process 
    int exitCode = runMobileTest.ExitCode;

    // check if this test step pass or fail. If return 0 - process complete normally, else - process fould.
    Assert.AreEqual(exitCode, 0);
}
```
```VB

Imports System.IO
Imports System.Diagnostics

<CodedStep("Run Mobile Test")> _
Public Sub Run_Mobile_Test_CodedStep()

    Dim runMobileTest As New Process()

    runMobileTest.StartInfo.FileName = "[PathToExecutable]\Telerik.MobileTesting.Runner.exe"

    runMobileTest.StartInfo.Arguments = "/C " +  " /msgServer=\"ws://localhost:8084\" /project=\"[PathToTheProject]\\DemoMobileProject\" /test=\"Web Tests\"\\Login.mttest";

    runMobileTest.Start()

    runMobileTest.WaitForExit()

    Dim exitCode As Integer = runMobileTest.ExitCode		

    Assert.AreEqual(exitCode, 0)

End Sub
```

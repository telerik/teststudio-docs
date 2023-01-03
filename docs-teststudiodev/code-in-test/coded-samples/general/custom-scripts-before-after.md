---
title: Custom Scripts Before/After Test
page_title: Custom Scripts Before/After Test - Test Studio Dev Documentation
description: Custom Scripts Before/After Test
position: 1
---
# Execute Custom Scripts Before/After the Test Run

* *I would like to invoke a custom script once the test finishes. The custom script must have access to newly-generated test results.*

* *I would like to invoke a custom script just before the test starts executing.*

## Solution

Override the **OnAfterTestCompleted(TestResult result)** method for the "after" script and the **OnBeforeTestStarted()** method for the "before" script. They are both members of the BaseTest class that are invoked once the test finishes or before it starts.

First, create a coded step in order to generate a code-behind file. Then open the code-behind class and add the override definition inside the BaseTest class.

### Visual Studio plugin

1.If your test doesn't contain any coded steps, click the <a href="/code-in-test/features-in-code#Code-Behind-File" target="_blank">Add Code-Behind File button</a>.
2.If you test contains a coded step, right click it and select **View Code** to go to the code-behind file.

![View code][3]

3.Write the override definition inside the BaseTest (but not inside another method/coded step).

### The Override Definition

The TestResult object lets you access the test results from the run that just finished (i.e. the one invoking the **OnAfterTestCompleted** method):

#### __[C#]__

    {{region }}

    public override void OnAfterTestCompleted(TestResult result)
    {
        string overall = Convert.ToString(result.Result);
        Log.WriteLine(overall);
        result.ExportToResultFile(@"C:\", result.TestName);
    }
    {{endregion}}

#### __[VB]__

    {{region }}

    Public Overrides Sub OnAfterTestCompleted(result As TestResult)
        Dim overall As String = Convert.ToString(result.Result)
        Log.WriteLine(overall)
        result.ExportToResultFile("C:\", result.TestName)
    End Sub
    {{endregion}}

The **OnBeforeTestStarted** method allows you to perform actions required for the initialization of your test (starting scripts, etc.):

#### __[C#]__

    {{region }}

    public override void OnBeforeTestStarted()
    {
        this.ExecuteTest("Folder1\\WebTest2.tstest");
    }
    {{endregion}}

#### __[VB]__

    {{region }}

    Public Overrides Sub OnBeforeTestStarted()
        Me.ExecuteTest("Folder1\WebTest2.tstest")
    End Sub
    {{endregion}}

You can use logic from assemblies in these methods. First add references to the assemblies.

[3]: images/custom-scripts-before-after/fig3.png

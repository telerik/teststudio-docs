---
title: Custom Scripts Before/After Test
page_title: Custom Scripts Before/After Test
description: "Add Custom Scripts Before/After Test execution in Test Studio. Execute certain actions before or after each test run in Test Studio."
position: 1
---
# Execute Custom Scripts Before/After the Test Run #

* *I would like to invoke a custom script once the test finishes. The custom script must have access to newly-generated test results.*

* *I would like to invoke a custom script just before the test starts executing.*

## Solution ##

Override the **OnAfterTestCompleted(TestResult result)** method for the "after" script and the **OnBeforeTestStarted()** method for the "before" script. They are both members of the BaseTest class that are invoked once the test finishes or before it starts. 
 
First, create a coded step in order to generate a code-behind file. Then open the code-behind class and add the override definition inside the BaseTest class.

### Standalone version ###

1. If your test doesn't contain any coded steps, add a <a href="/features/custom-steps/script-step" target="_blank">Script Step</a> in order to generate the code-behind file.
2. Once you add the script step, click **View Class** to make the BaseTest class visible.

![View Class button][1]

3. Add the override definition inside the BaseTest, but not inside another method/coded step. 

![Override definition][2]

### Visual Studio plugin ###

1. If your test doesn't contain any coded steps, click the <a href="/advanced-topics/coded-steps/code-behind-file" target="_blank">Add Code-Behind File button</a>.
2. If you test contains a coded step, right click it and select **View Code** to go to the code-behind file.

![View code][3]

3. Write the override definition inside the BaseTest (but not inside another method/coded step).

### The Override Definition ###

The TestResult object lets you access the test results from the run that just finished (i.e. the one invoking the **OnAfterTestCompleted** method):

```C#
public override void OnAfterTestCompleted(TestResult result)
{
    string overall = Convert.ToString(result.Result);
    Log.WriteLine(overall);
    result.ExportToResultFile(@"C:\", result.TestName);
}
```
```VB
Public Overrides Sub OnAfterTestCompleted(result As TestResult)
	Dim overall As String = Convert.ToString(result.Result)
	Log.WriteLine(overall)
	result.ExportToResultFile("C:\", result.TestName)
End Sub
```

The **OnBeforeTestStarted** method allows you to perform actions required for the initialization of your test (starting scripts, etc.):

```C#
public override void OnBeforeTestStarted(BeforeTestStartedArgs args)
{
    this.ExecuteTest("Folder1\\WebTest2.tstest");
}
```
```VB
Public Overrides Sub OnBeforeTestStarted(BeforeTestStartedArgs args)
	Me.ExecuteTest("Folder1\WebTest2.tstest")
End Sub
```

You can use logic from assemblies in these methods. First add references to the assemblies. For Test Studio Standalone version, see the article on how to <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">Add an Assembly Reference</a>.


[1]: /img/advanced-topics/coded-samples/general/custom-scripts-before-after/fig1.png
[2]: /img/advanced-topics/coded-samples/general/custom-scripts-before-after/fig2.png
[3]: /img/advanced-topics/coded-samples/general/custom-scripts-before-after/fig3.png

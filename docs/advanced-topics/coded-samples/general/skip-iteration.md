---
title: Skip Iteration
page_title: Skip Iteration
description: "Learn how to skip specific iterations in data-driven Test Studio tests based on custom conditions. Step-by-step guide with code examples for conditional test execution and data source inheritance."
position: 1
---
# How to Skip a Specific Iteration While Executing a Data-Bound Test

*You're executing a data-driven test. You need to skip one or more iterations based on a specific condition.*

## Solution

You'll need to create two tests. Let's call them **MainTest** and **Subtest**. Put the actual test steps you want to invoke (i.e. your test) in Subtest.

Now it's time to bind your test to a data source. Make **MainTest** (which is still empty) data-driven.

![Create two tests][1]

After this add **Subtest** via the <a href="/features/custom-steps/test-as-step" target="_blank">Test as Step</a> feature in MainTest. However, we're going to do that in a coded step. Here's what the code looks like: 

```C#
this.ExecuteTest("Subtest.tstest");
```
```VB
Me.ExecuteTest("Subtest.tstest")
```

For each iteration of **MainTest**, Test Studio will attempt to implement this code and run **SubTest**. Now we can implement conditional logic which determines whether we execute the above logic. In effect, this will control whether a given iteration executes the **SubTest**. If it doesn't, the iteration is effectively skipped - it will invoke no actions of any consequence. We'll skip the iteration even though it won't seem so from **MainTest**'s point of view (i.e. all the iterations will be listed in **MainTest**'s Log file).
 
Let's say we want to implement a data-driven test that navigates to <a href="http://www.random.org/" target="_blank">random.org</a>, generates a random number, and executes some steps if the number is even. First we record the required steps in MainTest. A step will <a href="/advanced-topics/coded-samples/general/extracted-variables-in-code" target="_blank">Extract</a> the generated number in a variable we're going to name num. Now we check whether this value is even and execute SubTest if it is:

```C#
if (Convert.ToInt16(this.GetExtractedValue("num")) % 2 == 0 )
{
     this.ExecuteTest("SubTest.tstest");
}
```
```VB
If Convert.ToInt16(Me.GetExtractedValue("num")) Mod 2 = 0 Then
    Me.ExecuteTest("SubTest.tstest")
End If
```

If you want to access data from your data source, set the **SubTest** to inherit its parent's data source:

![Inherint Parent Datasource][2]

**SubTest** will now be able to access **MainTest**'s data source and **MainTest**'s extracted variables. You can download a sample Test Studio project demonstrating this apporach from the following locations:

* <a href="/demoslibrary/DDTSkipIteration_C.zip">Download C# sample</a>

* <a href="/demoslibrary/DDTSkipIteration_VB.zip">Download VB sample</a>

The sample project follows the example seen in this article. The SubTest from the sample project navigates to <a href="http://www.telerik.com/" target="_blank">telerik.com</a> and performs a search. The value for the search is taken from MainTest's data source.

[1]: /img/advanced-topics/coded-samples/general/skip-iteration/fig1.png
[2]: /img/advanced-topics/coded-samples/general/skip-iteration/fig2.png
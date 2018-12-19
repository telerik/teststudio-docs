---
title: Known Issues
page_title: Known Issues 
description: "Known Issues"
publish: true
position: 0
slug: ms-known-issues
previous_url: /test-studio-mobile/troubleshooting-mb/known-issues,/test-studio-mobile/troubleshooting-mb
---

#Known Issues

##PROBLEM

After a Test Studio is upgraded, running coded tests created with previous Test Studio versions may fail with:

*Could not load file or assembly error*

![Could not load assembly](/img/test-studio-mobile/knowledge-base-tm/known-issues/fig5.png)

##SOLUTION

This is expected behavior for projects that have coded steps. All you have to do to resolve it is:

1. Open you test project root folder.

2. Open the Bin folder inside it and delete the file named *MyProjectName.dll*.

3. Run the test.


##PROBLEM

I am getting *TestProject.TestName does not contain a definition for "Context" and no extension method "Context" accepting a first argument of type TestProject.TestName could be found (are you missing a using directive or an assembly reference?)* compilation error in my C# project

![C# error](/img/test-studio-mobile/knowledge-base-tm/known-issues/fig1.png)

and 

*"Context is not a member of TestProject.TestName error in file C:\Users\[userName]\AppData\Local\Temp\tempFileName.tmp"* compilation error in my VB project.

![VB error](/img/test-studio-mobile/knowledge-base-tm/known-issues/fig2.png)

This compile error appears in case you have changed the class name in your code file.

![VB error](/img/test-studio-mobile/knowledge-base-tm/known-issues/fig3.png)

##SOLUTION

When you change the class name you should bind the test to the new class name. You can do this from the test properties.

![Bind the new class](/img/test-studio-mobile/knowledge-base-tm/known-issues/fig4.png)

<div id="instumentation-exception">
##PROBLEM

*While instrumenting a native Android application through the [built in method]({% slug ms-configure-android%}#Built-In-Configuration) I get the following exception:*

![Error while instrumenting Android app](/img/test-studio-mobile/knowledge-base-tm/known-issues/fig6.png)

This happens when the app to be instrumented has more than 65536 methods and is is installed on device running API level 20 and below. 

##SOLUTION

You should use device which is running API level 21 or higher or use the [manual]({% slug ms-configure-android%}#Manual) instrumentation.
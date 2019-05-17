---
title: Use External DLL in VS
page_title: Use External DLL in VS
description: "Use External DLL in the Test Studio project from the Visual Studio solution."
position: 1
---
# Use External DLL in VS #

*I need to reference and use an external DLL that contains global functions from a coded step in Visual Studio.*

## Solution ##

You'll find an attached sample Visual Studio Solution attached at bottom of the page. The solution contains two projects. One is a Test Studio project and the other is a "normal" Class Library Project. We use functions from the Class Library inside a coded step in the test project.

Note that the functions in the "Utility" project are contained within a non-static class. The constructor for this class takes the Manager object from the test project as an argument. Take a close look at this implementation because it allows the "Utility" project to directly interact with the test object.

Download the C# project <a href="/advanced-topics/coded-samples/samples/use-external-dll/MultiprojectSample.zip">here</a>.
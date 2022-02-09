---
title: Coding Options in Visual Studio Project
page_title: Coding Options in Visual Studio Project
description: "Extended code features in the Test Studio project created in Visual Studio plugin. All steps of a recorded steps can be converted to code in the Visual Studio Project. Preview code for a step in the Visual Studio Project."
position: 7
---
# Coding Options in VS Plugin

The Visual Studio project interface allows some additional coding options for the tests in the Test Studio project - you can preview the code of a step, or convert the whole test into code.

This article guides you through these options.

## Preview Code

Use the **Preview Code** button to see the corresponding code for your Test Studio test.

![Preview Code](/img/automated-tests/vs-plugin/code-options-in-vs/preview-code.png)

## Generate a Unit Test from Recorded Test

In the context of Visual Studio project you can convert the whole recorded test to a unit test. The **Generate unit test** button converts the selected Test Studio test into a unit test of your choice. The **Unit Test Template Selector** dialog appears and lets you choose a template, i.e. a testing framework. If you have defined some rows of data in the Data Tab, it is converted to XML and placed in a file, which you specify for use by the selected testing framework.

![Generate unit test button](/img/automated-tests/vs-plugin/code-options-in-vs/generate-unit-test.png)

The generation of a unit test creates a new test in the project using the selected template for unit test. While the original Test Studio test remains intact, changes made to it are not synced to the unit test. Likewise, changes made to the unit test are not synced back to the Test Studio test. A unit test cannot be converted back to a Test Studio test.

![Unit Test](/img/automated-tests/vs-plugin/code-options-in-vs/unit-test-generated.png)

Since fully coded tests are harder to maintain, we recommend using this feature sparingly and only when absolutely necessary.

> __Note__
><br>
><br>
> This conversion is a one-way process. You __cannot convert the coded unit test back__ into a Test Studio test.
><br>
Also, we do not guarantee the converted test will run perfectly. Sometimes the code needs a little tweaking before it works (e.g. if you have coded steps or dialog handling that does not convert properly).

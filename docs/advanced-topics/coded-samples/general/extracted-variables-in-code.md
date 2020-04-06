---
title: Extracted Variables in Code
page_title: Get/Set Extracted Variables in Code
description: "Get/Set Extracted Variables in Code in Test Studio coded test. Extract text from page, modify it and use it again in the Test Studio test recorded steps."
position: 1
---
# Get/Set Extracted Variables in Code

There are test scenarios in which you need to take, for example, the text content of an element and reuse it later in the test steps. Test Studio allows you to easily accomplish this <a href="/features/recorder/verifications/extraction" target="_blank">by using an Extraction step</a>.

The extracted variable can be used in a coded step as well - that way you can modify the value of the extracted variable in various ways, or use this to determine how a test should continue. In the cases when the variable's value requires any modification, you can assign the new value back to the same variable or a new one, and then use this back in the Test Studio UI steps. 

## Get the Value of an Extracted Variable

Use the *GetExtractedValue()* method to use the value of an extracted variable in a coded step:

```C#
object myData = GetExtractedValue("ExtrVarName");
```
```VB
Dim myData As Object = GetExtractedValue("ExtrVarName")
```

## Set a Value to an Extracted Variable

Use the *SetExtractedValue()* method to set the value of an extraction variable so it can be used later in a standard action or verification step:

```C#
string newValue = "newValueToAssign";
SetExtractedValue("ExtrVarName", newValue);
```
```VB
Dim newValue As String = "newValueToAssign"
SetExtractedValue("ExtrVarName", newValue)
```

## Example of Using the Extracted Variables in Code

A simple scenario to demonstrate the usage of extracted variables in code is to get the text content of an element, modify it as per the requirements, and assign it to a variable to be used in the next recorded steps in a test. A sample project to demonstrate this can be <a href="/demoslibrary/Get-Set-Extr-Var-in-Code.zip">downloaded from this link</a>.

The baseline of code to use should look similar to the one below:

```C#
// Assign the value of the extracted variable from the recorded step 'ExtractedVar' to a variable to use in the code
var extrVariableInCode = GetExtractedValue("ExtractedVar");

// Insert the necessary custom code to modify the exctracted value and assign it to a string variable
string newValue = "newValueToAssign";

// Assign the modified variable to a new extracted variable
SetExtractedValue("ModifiedExtrVariable", newValue);
```
```VB
' Assign the value of the extracted variable from the recorded step 'ExtractedVar' to a variable to use in the code
Dim extrVariableInCode As Object = GetExtractedValue("ExtractedVar")

' Insert the necessary custom code to modify the exctracted value and assign it to a string variable
Dim newValue As String = "newValueToAssign"

' Assign the modified variable to a new extracted variable
SetExtractedValue("ModifiedExtrVariable", newValue)
```
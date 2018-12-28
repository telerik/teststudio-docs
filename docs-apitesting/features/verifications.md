---
title: Verifications
page_title: Verifications
description: "Progress® Test Studio® for APIs - Verifications"
position: 0
publish: true
---

# Verifications

## Overview

The Verifications in Test Studio for APIs compare Variables with constants or other Variables. The result of the comparison determines the outcome of the corresponding Test Step.

Verifications can be used either as part of a dedicated [Verification step](/features/steps/verification) or directly inside of a [Http Request Step](/features/steps/http-request) (in its Verifications tab).



## Source and Expectation

The Source property of each Verification always points to a Variable Name.

> You could use the [Variable reference syntax](/features/variables#Referencing-Variables) in the Source property, but the Verification will always treat the resolved value as Variable Name.  

The Expectation property of the Verifications is a string, which may contain Variable references. The Variable references will be resolved at runtime, before executing the Comparison operation.




## Source Path

Sometimes the value in the Source Variable will be a complex value (like a JSON or XML) and you could use the Source Path property to reference parts of the original value using JSONPath or XPath.

> Test Studio for APIs displays simplified JSONPath for certain Variables in order to improve the user experience. For example, if you choose to verify Headers, you will directly type header name in the Path TextBox. If you choose StatusCode or ResponseTime, the Path TextBox is not available. 

See more about path expressions [here](/features/source-path-expressions).


## Verification Errors

When a verification fails, you will see a message, showing the difference between the expected value of the verification and the actual value that was received. Click on the "**View Error**" button to see the full text of the message and copy it to the clipboard if needed.

![Verification Error][1] 


## Comparison Operations

The String comparison operations first convert the value of the Source Variable and the Expectation to strings and then apply the comparison function:

- `Is Equal` - passes when the Source Value and the Expectation are equal.
- `Is Not Equal` - passes when the Source Value and the Expectation are not equal.
- `Contains Text` - passes when the Source Value contains the Expectation.
- `Does Not Contain Text` - passes when the Source Value does not contain the Expectation.
- `Starts With` - passes when the Source Value starts with the Expectation.
- `Does Not Start With` - passes when the Source Value does not start with the Expectation.
- `Ends With` - passes when the Source Value ends with the Expectation.
- `Does Not End With` - passes when the Source Value does not end with the Expectation.
- `Matches Regex` - passes when the Source Value matches the regex pattern in Expectation.
- `Does Not Match Regex` - passes when the Source Value does not match the regex pattern in Expectation.
- 'Is Null' - passes when the Source Value is null
- 'Is Not Null' - passes when the Source Value is not null

> You could choose to ignore tha case in the String operations. 

The Numeric comparison operations try to convert the value of the Source Variable and the Expectation to numbers and will fail if the conversion fails:

- `Is Equal Number` - passes when the Source Value and the Expectation are equal.
- `Is Not Equal Number` - passes when the Source Value and the Expectation are not equal.
- `Is Greater` - passes when the Source Value is greater than the Expectation.
- `Is Greater or Equal` - passes when the Source Value is greater or equal than the Expectation. 
- `Is Less` - passes when the Source Value is lesser than the Expectation.
- `Is Less or Equal` - passes when the Source Value is lesser or equal than the Expectation.


[1]: /img/features/verifications/verification-error.png
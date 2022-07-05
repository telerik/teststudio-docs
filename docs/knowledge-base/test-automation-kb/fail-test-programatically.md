---
title: Fail Step or Test Programatically
page_title: Fail test step or mark the entire test result as failed
description: Even if all test steps are successful, you might need to fail one step or the entire test at the end of the execution. You can do that programitacally in OnAfterTestCompleted method.
position: 1
---
# Fail Step or Test Programatically

## PROBLEM

All steps are successfully executed, but the might be errors in the scenario or in the application. Consider adding a verification step to ensure the state of the application is correct. In case there is no such verification available, you can apply the proposed solution.

## SOLUTION

You can change the result from specific step or the entire test programatically, after the test is completed. To do that, you need to override the method **OnAfterTestCompleted()** in a coded step.

1.&nbsp; Add a <a href="/features/custom-steps/script-step" target="_blank">coded step</a> to the current test.

2.&nbsp; Override the **OnAfterTestCompleted()** method outside of the coded step method. The logic inside this method will be executed after the last step of the test.

3.&nbsp; Check for a condition, which will be used to evaluate the state of the application and whether the step or test should be marked as failed.

```C#
public override void OnAfterTestCompleted(TestResult result)
{
    if (condition == false)
    {
        //result.StepResults.Last().ResultType = ArtOfTest.Common.Design.ResultType.Fail; //mark the last step as failed
        result.StepResults.Last().ParentTestResult.Result = ArtOfTest.Common.Design.ResultType.Fail; //mark the whole test as failed            
    }    
}
```
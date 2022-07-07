---
title: Fail Step or Test Programmatically
page_title: Fail test step or mark the entire test result as failed
description: Even if all test steps are successful, you might need to fail one step or the entire test at the end of the execution. You can do that programmatically in OnAfterTestCompleted method.
position: 1
---
# Fail Step or Test Programatically

## PROBLEM

All steps are successfully executed, but you might need to still fail the test due to internal errors in the application. Consider adding a verification step to ensure the state of the application is correct. In case there is no such verification available, you can apply the proposed solution.

## SOLUTION

You can change the result from specific step or the entire test programmatically, after the test is completed. To do that, you need to <a href="/advanced-topics/coded-samples/general/custom-scripts-before-after" target="_blank">override the method **OnAfterTestCompleted()**</a> in a coded step.

1.&nbsp; Add a <a href="/features/custom-steps/script-step" target="_blank">coded step</a> to the current test.

2.&nbsp; Override the **OnAfterTestCompleted()** method outside of the coded step method. The logic inside this method will be executed after the last step of the test.

3.&nbsp; Find a specific condition, which will be used to evaluate the state of the application and whether the step or test should be marked as failed.

```C#
namespace DemoProj
{

    public class testToFail : BaseWebAiiTest
    {
        #region [ Dynamic Pages Reference ]

        // Add your test methods here...
    
        [CodedStep(@"New Coded Step")]
        public void testToFail_CodedStep()
        {
            
        }

        public override void OnAfterTestCompleted(TestResult result)
        {
            if (condition == false)
                {
                    // Mark the last step as failed
                    //result.StepResults.Last().ResultType = ArtOfTest.Common.Design.ResultType.Fail; 

                    // Mark the whole test as failed 
                    result.StepResults.Last().ParentTestResult.Result = ArtOfTest.Common.Design.ResultType.Fail;             
                }    
        }
    }   
}
```

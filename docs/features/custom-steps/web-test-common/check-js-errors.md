---
title: Check for JS Errors
page_title: Check for JS Errors
description: "How to validate if there are any JS/JavaScript errors on the tested page with Test Studio. Verify if a page generates JS/JavaScript errors during a Test Studio test run/execution."
position: 8
---
# Check for JavaScript Errors

Insert a step to verify if there are any JS errors generated on the current page.

![Verify if any JS errors are present](/img/features/custom-steps/check-js-errors/fig1.png)

> The page in the current example does not actually contain JavaScript errors. These were generated on purpose to demonstrate the feature.

## Add Step to Check for JS Errors

If not modified the default added step will check for any JS errors and will pass if there are none. If some errors are detected the step will fail and list the errors and their count per error text in the step failure details. 

![Failed JSErrors Step Details](/img/features/custom-steps/check-js-errors/fig2.png)

The execution log file also contains the failure information. 

![Results Log with Failed JSErrors Step](/img/features/custom-steps/check-js-errors/fig3.png)

## Exclude JS Errors 

You can specify, though, which errors to be excluded from that count. The text of all errors to be excluded can be listed in the __ExcludedErrors__ property of the step. This field can be also data driven.

![ExcludedErrors Field in JSErrors Step](/img/features/custom-steps/check-js-errors/fig6.png)

The check is if the error text contains the text listed in the __ExcludedErrors__ field. The result after execution specifies there are no errors containing the populated error text.

![Exexution Log of Excluded Errors Step Passed](/img/features/custom-steps/check-js-errors/fig7.png)

Multiple errors can be excluded as well - separate the errors text with '|'. Be aware that single space charachter is also taken into account and could cause false positive results.

![ExcludedErrors Field in JSErrors Step with Multiple Errors Excluded](/img/features/custom-steps/check-js-errors/fig4.png)
![ExcludedErrors Field in JSErrors Step](/img/features/custom-steps/check-js-errors/fig8.png)

The log of the test execution provides details which are the excluded errors and if there are any other.

![Exexution Log of Excluded Multiple Errors Step Passed](/img/features/custom-steps/check-js-errors/fig5.png)
![Exexution Log of Excluded Errors Step Failed](/img/features/custom-steps/check-js-errors/fig9.png)

> __Note!__ The JS error check step detects only JavaScript errors. Any errors related to not loaded resources will not be detected. An example for such console error is listed below:<br>
<br>
> _Failed to load resource: the server responded with a status of 404 (Not Found)_
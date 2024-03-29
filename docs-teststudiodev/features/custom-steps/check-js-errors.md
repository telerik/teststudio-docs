---
title: Check for JS Errors
page_title: Check for JS Errors - Test Studio Dev Documentation
description: Check if there are any JavaScript errors in the browser console. 
slug: features/custom-steps/check-js-errors
position: 6
---
# Check for JavaScript Errors

The <a href="/features/recorder/step-builder" target="_blank">Step Builder</a> allows you to add steps which perform actions which cannot be recorded. The below described step can be found in the _Common_ section of Step Builder.

![Common Section](images/step-builder-common.png)

## Add Step to Check for JS Errors

Insert a _Check For JS Errors_ step to verify if there are any JS errors generated on the page. If not modified the default added step will check for any JS errors and will pass if there are none. If some errors are detected the step will fail and list the errors and their count per error text in the step failure details. 

![Failed JSErrors Step Details](images/check-js-errors/fig2.png)

The execution log file also contains the failure information. 

![Results Log with Failed JSErrors Step](images/check-js-errors/fig3.png)

## Exclude JS Errors 

You can specify, though, which errors to be excluded from that count. The text of all errors to be excluded can be listed in the __ExcludedErrors__ property of the step. This field can be also data driven.

![ExcludedErrors Field in JSErrors Step](images/check-js-errors/fig6.png)

The check is if the error text contains the text listed in the __ExcludedErrors__ field. The result after execution specifies there are no errors containing the populated error text.

![Exexution Log of Excluded Errors Step Passed](images/check-js-errors/fig7.png)

Multiple errors can be excluded as well - separate the errors text with '|'. Be aware that single space charachter is also taken into account and could cause false positive results.

![ExcludedErrors Field in JSErrors Step with Multiple Errors Excluded](images/check-js-errors/fig4.png)
![ExcludedErrors Field in JSErrors Step](images/check-js-errors/fig8.png)

The log of the test execution provides details which are the excluded errors and if there are any other.

![Exexution Log of Excluded Multiple Errors Step Passed](images/check-js-errors/fig5.png)
![Exexution Log of Excluded Errors Step Failed](images/check-js-errors/fig9.png)

> __Note:__ The JS error check step detects only JavaScript errors. Any errors related to not loaded resources will not be detected. An example for such console error is listed below:<br>
<br>
> _Failed to load resource: the server responded with a status of 404 (Not Found)_
---
title: Check for JS Errors
page_title: Check for JS Errors
description: "How to validate if there are any JS/JavaScript errors on the tested page with Test Studio. Verify if a page generates JS/JavaScript errors during a Test Studio test run/execution."
position: 8
---
# Check for JavaScript Errors

The __Check for JS errors__ feature allows you to verify if there are any JS errors generated on the current page.

This article demonstrates how to add this type of step into the test and how it works.

- [Add Check for JS Errors Step](#add-check-for-js-errors-step)
- [How Check for JS Errors Works?](#how-check-for-js-errors-works)
- [Exclude Specific JS Errors](#exclude-specific-js-errors)

## Add Check for JS Errors Step

Choose the __Check for JS errors__ option from the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a> and click on the __Add Step__ button in the lower right corner of the pane.

![Add Check for JS errors step][1]

## How Check for JS Errors Works?

> __Note!__
> <br>
> <br>
> The page in the current example does not actually contain JavaScript errors. These were generated on purpose to demonstrate the feature.

The default added step __checks for any JS errors__ and passes if there are none. In case any errors are detected, the step fails and lists in the <a href="/automated-tests/test-results/step-failure-details#step-failure-details-section" target="_blank">step failure details</a> the errors counting these per their text.

![Failed JSErrors Step Details][2]

The failure details are also listed in the <a href="/automated-tests/test-results/analyze-quick-run-results#generate-the-quick-execution-log" target="_blank">execution log</a>.

![Execution Log with Failed JS Errors Step][3]

## Exclude Specific JS Errors

The __ExcludedErrors__ property of the __Check for JS Errors__ step allows you to filter the errors and exclude some of them if you expect these. Insert the text to identify the errors that shouldn't be counted. Let's use _"test"_ and execute the same sample test again.

![ExcludedErrors Field in JSErrors Step][4]

The test checks if there are any JS errors on the page and excludes these which contain the text from the __ExcludedErrors__ property. Expected, the result shows there are no errors on the page, which don't contain _"test"_ in their message.

![Execution Log of Excluded Errors Step Passed][5]

## Exclude Multiple Different Errors

Multiple errors can be also excluded - separate the errors' text with '|'.

![ExcludedErrors Field in JSErrors Step with Multiple Errors Excluded][6]

The execution log from running the test lists details which are the excluded errors and if there are any other.

![Exexution Log of Excluded Multiple Errors Step Passed][7]

Single _space_ character is also taken into account and if it is added by mistake, it could cause false positive results.

![ExcludedErrors Field in JSErrors Step][8]

The execution log can help in identifying if any additional character is present.

![Exexution Log of Excluded Errors Step Failed][9]

> __Note!__
> <br>
> <br>
> The __Check for JS Errors__ step detects only JavaScript errors. Any errors related to not loaded resources will not be detected. An example for such console error is listed below:<br>
<br>
> `Failed to load resource: the server responded with a status of 404 (Not Found)`

[1]: /img/features/custom-steps/check-js-errors/step-builder-js-errors.png
[2]: /img/features/custom-steps/check-js-errors/fig2.png
[3]: /img/features/custom-steps/check-js-errors/fig3.png
[4]: /img/features/custom-steps/check-js-errors/extended-menu-js-errros.png
[5]: /img/features/custom-steps/check-js-errors/fig7.png
[6]: /img/features/custom-steps/check-js-errors/extended-menu-js-errros-2.png
[7]: /img/features/custom-steps/check-js-errors/fig5.png
[8]: /img/features/custom-steps/check-js-errors/extended-menu-js-errros-3.png
[9]: /img/features/custom-steps/check-js-errors/fig9.png

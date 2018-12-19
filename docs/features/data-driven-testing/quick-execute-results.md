---
title: Quick Execute Results
page_title: Quick Execute Results
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/data-driven-testing/data-driven-test-results.aspx, /user-guide/data-driven-testing/data-driven-test-results
position: 5
---
# Quick Execute Results


Let's look at an example of a [Local Data Driven Test](/features/data-driven-testing/local-data-driven-test), run with quick execute, and how to view and interpret the results.

Here is a Web Test that:

1. Navigates to http://www.google.com.
1. Sets the search query to Telerik.
1. Clicks the Search button.
1. Verifies the text block description of the first result.


The fourth step is data bound to a local data table:

![Local Test Data][1]

Click the **Run** button in the **Quick Execution** ribbon. The test steps should execute three times, once for each row in the built-in grid.


- The summary results read **Fail 11 passed out of total 12 executed**.
- There were four test steps, executed for three iterations, once for each row of data.
- Expand the drop-down menu to view the data used in each iteration.
- *Telerik* and *mobile app* both existed in the element text that step four verified.
- The data xyz did not exist in the element text so that iteration failed.

![Test Steps][2]

Click the blue **View Log** link to view:

- The overall result
- The result of each iteration
- The data used to drive each iteration
- Failure information

![View Log][3]

[1]: /img/features/data-driven-testing/quick-execute-results/fig1.png
[2]: /img/features/data-driven-testing/quick-execute-results/fig2.png
[3]: /img/features/data-driven-testing/quick-execute-results/fig3.png
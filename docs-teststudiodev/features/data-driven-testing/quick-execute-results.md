---
title: Quick Execute Results
page_title: Quick Execute Results | Test Studio Dev Documentation
description: How do results of a data driven test look like and how to analyze them in Test Studio Dev
position: 6
---
# Quick Execute Results

Let's look at an example of a <a href="/features/data-driven-testing/local-data-driven-test" target=blank>Local Data Driven Test</a> which runs the test to generate results and how to view and interpret the results.

Here is a similar web test that navigates to http://www.google.com, sets the search query to Telerik, clicks the Search button and at the end verifies whether the text block description of one of the results contains some . The fourth verification step is data bound to a local data table 

![Local Test Data][1]

Click the **Run** button in the **Quick Execution** ribbon. The test steps will execute four times - once for each row in the built-in grid.

The summary results are for the selected from dropdown iteration. Expand the drop-down menu to view the data used in each iteration and select any to see the respective iteration results.

![Selected Iteration result][2]

Click **View Log** to see the overall results for the test containing all iterations.

- The overall result for test
- The result of each iteration
- The data used to drive each iteration
- Failure information

![View Log][3]

[1]: images/quick-execute-results/fig1.png
[2]: images/quick-execute-results/fig2.png
[3]: images/quick-execute-results/fig3.png


- *Telerik* and *mobile app* both existed in the element text that step four verified.
- The data xyz did not exist in the element text so that iteration failed.
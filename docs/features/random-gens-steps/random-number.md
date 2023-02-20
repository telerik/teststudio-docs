---
title: Generate Random Number
page_title: Generate Random Number
description: "How to add a step to generate random number in Test Studio test? Use a built-in step to enter random number"
position: 1
---
# Generate Random Number Step

The __Generate Random Number__ step allows you to generate random number during test run-time and use it later in the test.

The article demonstrates how to add this type of step into the test.

Choose the __Generate Random Number__ option from the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a> and click on the __Add Step__ button in the lower right corner of the pane.

![Add Generate Random Number step](/img/features/random-data/random-number/fig1.png)

There are few notable properties of the step:

- __Min Value__ - the smallest number which can be assigned to the data bind variable.
- __Max Value__ - the largest number which can be assigned to the data bind variable.
- __DataBindVariableName__ - the name of <a href="/features/recorder/highlighting-menu/quick-steps/extraction#use-the-extracted-value-in-the-next-steps" target="_blank">extracted variable to use</a> to output the generated data.

![Generate Random Number step properties](/img/features/random-data/random-number/fig2.png)
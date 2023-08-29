---
title: Generate Random Date and Time
page_title: Generate Random Date and Time
description: "How to add a step to generate random date and/or time in Test Studio test? Use a built-in step to enter random date and time"
position: 3
---
# Generate Random Date and Time Step

The __Generate Random Date and Time__ step allows you to generate random date and/or time during test run-time and use it later in the test.

The article demonstrates how to add this type of step into the test.

Choose the __Generate Random Date and Time__ option from the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a> and click on the __Add Step__ button in the lower right corner of the pane.

![Add Generate Random Date and Time step][1]

There are few notable properties of the step:

- __Start Date__ - first date of a period for date generation.
- __End Date__ - last date of a period for date generation.
- __Date Time Format__ - format used for text representation of the date and time. Default is _MM/dd/yy H:mm_. Date time formats can be modified as per the <a href="https://learn.microsoft.com/en-us/dotnet/standard/base-types/custom-date-and-time-format-strings" target="_blank">custom date and time format specifiers provided by Microsoft</a>.
- __Regional Format__ - regional format used for date and time representation. Default is _en-US_.
- __Use System Reg Format__ - use system regional format used for date and time representation. Default is _false_.
- __DataBindVariableName__ - the name of <a href="/features/recorder/highlighting-menu/quick-steps/extraction#use-the-extracted-value-in-the-next-steps" target="_blank">extracted variable to use</a> to output the generated data.

![Generate Random Date and Time step properties][2]

[1]: /img/features/random-data/random-date/step-cuilder-dnt.png
[2]: /img/features/random-data/random-date/extended-menu-rnd-dnt.png
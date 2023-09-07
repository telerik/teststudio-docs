---
title: Generate Random String
page_title: Generate Random String
description: "How to add a step to generate random string in Test Studio test? Use a built-in step to enter random string"
position: 2
---
# Generate Random String Step

The __Generate Random String__ step allows you to generate random string during test run-time and use it later in the test.

The article demonstrates how to add this type of step into the test.

Choose the __Generate Random String__ option from the <a href="/features/custom-steps/overview" target="_blank">__Step Builder__</a> and click on the __Add Step__ button in the lower right corner of the pane.

![Add Generate Random String step][1]

There are few notable properties of the step:

- __Prefix__ - (optional) the prefix to add to the random string.
- __Suffix__ - (optional) the suffix to add to the random string.
- __Allowed Symbols__ - allowed symbols to be used in string generation. Applicable characters group are _a-zA-Z0-9_. If you need to define part of the alphabet, or use other characters, all symbols must be listed.
- __String Length__ - the length of the generated string excluding the prefix and suffix. The valid range is between 1 and 1000.
- __DataBindVariableName__ - the name of <a href="/features/recorder/highlighting-menu/quick-steps/extraction#use-the-extracted-value-in-the-next-steps" target="_blank">extracted variable to use</a> to output the generated data.

![Generate Random String step properties][2]

[1]: /img/features/random-data/random-string/step-builder-rnd-string.png
[2]: /img/features/random-data/random-string/extended-menu-rnd-str.png
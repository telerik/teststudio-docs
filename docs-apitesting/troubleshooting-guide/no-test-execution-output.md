---
title: No Test Execution Output
page_title: No Test Execution Output
description: "Progress® Test Studio® for APIs - Troubleshooting guide - No Test Execution Output"
position: 1
publish: true
---
# No Test Execution Output

If you run the tests and don't receive test execution output 

![NoTestExecutionOutput][1]

you can follow the steps below to troubleshoot the problem:

- start recording the test step requests with TestStudio for APIs or Fiddler and check whether a request is executed in the first place. 
- execute tests through the <a href="/features/command-line">command line interface</a> directly and check if the result is the same (there are no entries logged in the console).
- finally you need to reinstall the application which will solve the issue.

[1]: /img/troubleshooting-guide/no-test-execution-output/no-test-execution-output.png
---
title: Execute Selenium Test
page_title: Execute Selenium Test with Test Studio
description: Execute Selenium Test with Test Studio. Execute Selenium Test as part of Test Studio web test.
position: 1
---
# Execute Selenium Test with Test Studio

If you have written your selenium tests using C# then you can easily execute them using Test Studio. Steps to follow:

1.&nbsp; In Test Studio <a href="/getting-started/create-test-standalone/web-test" target="_blank">create a new test</a>.

2.&nbsp; Add a <a href="/advanced-topics/coded-steps/coded-step" target="_blank">coded step</a> in the test. 

3.&nbsp; Download selenium dlls from <a href="http://docs.seleniumhq.org/download/" target="_blank">here</a> and <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">add the assembly references</a>.

4.&nbsp; Make sure you add the using statements:

![using statements][1]

5.&nbsp; Paste/write the selenium test in the coded step:

![code sample][2]

The provided code sample above opens Firefox browser and navigates to Google.com. In the search field it types "webdriver" and hit the search button.

6.&nbsp; Click the <a href="/getting-started/test-execution/quick-execution" target="_blank">**Execute**</a> button to run the test. 

7.&nbsp; You can also execute the test as a part of a <a href="/getting-started/test-execution/test-lists-standalone" target="_blank">test list</a>.

8.&nbsp; As soon as the test is executed you can review the test result using the <a href="/troubleshooting-guide/troubleshooting-tools-tg/using-the-execution-log" target="_blank">execution log</a> or using the <a href="/getting-started/test-results/calendar" target="_blank">calendar</a> if executed as a part of a test list. The test can fail if an Assert statement fails.

> __Note!__ 
> <br>
> Test Studio web test always launches the selected browser upon execution. However, this shouldn't be the same browser in which the Selenium test runs as this might cause any inconsistency. 

[1]: /img/knowledge-base/test-execution-kb/execute-selenium-test/fig1.png
[2]: /img/knowledge-base/test-execution-kb/execute-selenium-test/fig2.png




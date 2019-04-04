---
title: Data Driven Tests With MSTest
page_title: Data Driven Tests With MSTest
description: How to configure data driven tests to be executed with MSTest.
position: 1
---
#How To Use Data Driven Tests With MSTest

*I want to execute data driven test with MStest.*

##Solution

1.&nbsp; Right click "Solution Items"and choose **Add > New Item**.

![Solution Items][1]

2.&nbsp; Highlight **Test Settings** on the left, again in the center, and give it a unique name. Click **Add**.

![Add test settings file][2]

3.&nbsp; The **Test Settings** window appears. Click **Deployment** on the left, check **Enable deployment ** and add the data folder as a deployment item.

![Enable deployment][3]	

3.&nbsp; On your <a href="/features/test-runners/mstest" target="_blank">MSTest command line</a> specify the .testsettings file to use during the test run.

[1]: /img/knowledge-base/data-driven-testing-kb/data-driven-test-with-mstest/fig1.png
[2]: /img/knowledge-base/data-driven-testing-kb/data-driven-test-with-mstest/fig2.png
[3]: /img/knowledge-base/data-driven-testing-kb/data-driven-test-with-mstest/fig3.jpg
[4]: /img/knowledge-base/data-driven-testing-kb/sql-random-row/fig4.png
[5]: /img/knowledge-base/data-driven-testing-kb/sql-random-row/fig5.png




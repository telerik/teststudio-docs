---
title: MSTest
page_title: MSTest
description: "Execute Test Studio with the Visual Studio command line runner MSTest. "
previous_url: /user-guide/test-runners/mstest.aspx, /user-guide/test-runners/mstest
position: 1
publish: false
---
# Executing Tests with MSTest

> Please note that **MSTest** is a command line utility from Microsoft that executes tests created in Visual Studio. This is not a command line tool that is a part of Test Studio. More information you can find <a href="https://msdn.microsoft.com/en-us/library/ms182487.aspx" target="_blank">here</a>.

You can also review our Telerik TV episode on <a href="http://tv.telerik.com/watch/automated-testing-tools/webui-test-studio-executing-webui-tests-with-mstest" target="_blank">Executing Tests with MSTest</a> for a video walk-through of this process.

1.&nbsp; Open Visual Studio. Create a project containing two tests. In this example, I've create two simple Web Tests: GoogleSearch and BingSearch.

2.&nbsp; Click **Test > Windows > Test List Editor**.

![Test List Editor][1]

**Note:** Read <a href="/getting-started/test-execution/visual-studio-2012-and-later-test-list" target="_blank">here</a> how to create test lists in Visual Studio 2012 or later.

3.&nbsp; Right click **List of Tests** and choose **New Test List**.

![New Test List][2]

4.&nbsp; Name the New Test List and click **OK**.

![Create New Test List][3]

5.&nbsp; From the **Test View** pane, drag and drop the tests into the **Test List Editor** and Save the project.

![Test View][4]

6.&nbsp; Close Visual Studio and open the Visual Studio Command Prompt.

7.&nbsp; Navigate to the project's directory.

- **C:\Users\Admin\Documents\Visual Studio 2010\Projects\MSTest-Tutorial\MSTest-Tutorial**

8.&nbsp; To execute a single test, enter the following:

- **mstest /testcontainer:.\GoogleSearch.tstest**

![Execute Test][5]

9.&nbsp; To execute a test list, enter the following:

- **mstest /testlist:SampleTestList /testmetadata:..\MSTest-Tutorial.vsmdi**

![Execute Test List][6]


10.&nbsp; Open Visual Studio and load the same project. Go the Solution Explorer pane.

11.&nbsp; Right click "Solution Items"and choose **Add > New Item**.

![Add New Item][7]

12.&nbsp; Highlight **Test Settings** on the left, again in the center, and give it a unique name. Click **Add**.

![Test Settings][8]

13.&nbsp; The **Test Settings** window appears. Click **Telerik Test Studio** on the left, and then click the **Web** tab.

![Web][9]

14.&nbsp; Change the browser to Firefox and click **Apply** and **Close**. Save the project.

15.&nbsp; Close Visual Studio and open the Visual Studio Command Prompt.

16.&nbsp; Navigate to the project's directory:

- **C:\Users\Admin\Documents\Visual Studio 2010\Projects\MSTest-Tutorial\MSTest-Tutorial**

17.&nbsp; To execute a test list with a custom settings file:
 
- **mstest /testlist:SampleTestList /testmetadata:..\MSTest-Tutorial.vsmdi /testsettings:..\FF.testsettings**

![Custom Settings][10]

18.&nbsp; To specify the output location for a results file, add: 

- **/resultsfile C:\Path\myResults.trx**

### See also
* <a href="/knowledge-base/data-driven-testing-kb/data-driven-test-with-mstest" target="_blank">How To Use Data Driven Tests With MSTest</a>


[1]: /img/features/test-runners/mstest/fig1.png
[2]: /img/features/test-runners/mstest/fig2.png
[3]: /img/features/test-runners/mstest/fig3.png
[4]: /img/features/test-runners/mstest/fig4.png
[5]: /img/features/test-runners/mstest/fig5.png
[6]: /img/features/test-runners/mstest/fig6.png
[7]: /img/features/test-runners/mstest/fig7.png
[8]: /img/features/test-runners/mstest/fig8.png
[9]: /img/features/test-runners/mstest/fig9.png
[10]: /img/features/test-runners/mstest/fig10.png


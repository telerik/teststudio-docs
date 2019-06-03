---
title: Test Lists (Visual Studio) 
page_title: Test Lists (Visual Studio)
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /getting-started/test-execution/visual-studio-2012-and-later-test-list
position: 1
---
# Test Lists (Visual Studio)

Although test lists are deprecated in Visual Studio 2012 you can still use them:

1. From the Solution Explorer right click the **Solution** and select **Add -> New item**.

	![Add item][1]

2. Type in the text box 'TestList.vsmdi' or any other item name that ends with '.vsmdi' and click add. 

	![Add .vsmdi file][2]

	**Note:** make sure not to click on any item as it would overwrite your input.

3. The .vsmdi file is created in 'Solution Items' sub folder right under your solution.

	![Solution items][3]

4. Double click TestList.vsmdi and which brings up the 'Test List Editor' in Visual Studio.

	![Test List Editor][4]

5. Right click **Lists of Tests** and select **New Test List**. 

	![Create new test list][5]

6. Name the Test List and click **OK**.

	![Name the test][6]

7. Click **All Loaded Tests** and drag the test you want into the **TestList1**. You can use Ctrl/Shift + Click to select multiple tests.

	![Add test to the test list][7]

> You can only create a test list and edit it in Visual Studio 2012 and later. In order to execute the test list you need to use <a href="/features/test-runners/mstest" target="_blank">**MSTest**</a> via the command line.
	

[1]: /img/general-information/test-execution/visual-studio-2012-and-later-test-list/fig1.png
[2]: /img/general-information/test-execution/visual-studio-2012-and-later-test-list/fig2.png
[3]: /img/general-information/test-execution/visual-studio-2012-and-later-test-list/fig3.png
[4]: /img/general-information/test-execution/visual-studio-2012-and-later-test-list/fig4.png
[5]: /img/general-information/test-execution/visual-studio-2012-and-later-test-list/fig5.png
[6]: /img/general-information/test-execution/visual-studio-2012-and-later-test-list/fig6.png
[7]: /img/general-information/test-execution/visual-studio-2012-and-later-test-list/fig7.png

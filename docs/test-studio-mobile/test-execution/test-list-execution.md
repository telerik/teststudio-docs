---
title: Test List Execution
page_title: Test List Execution
description: "Test List Execution in Test Studio Mobile"
publish: true
position: 0
slug: ms-testlist-execution
---

# Mobile Test Lists

1. In Test Studio Mobile you can execute one or more tests through a Test List. You can create a test list using the Create a List button:

	![add test list](/img/test-studio-mobile/test-execution/test-list-execution/fig1.png)

	or by right clicking on the TestList node in the project:

	![add test list](/img/test-studio-mobile/test-execution/test-list-execution/fig2.png)

2. A new dialog appears where you need to specify the test list type. Provide a name and click **OK**.

	![list type](/img/test-studio-mobile/test-execution/test-list-execution/fig3.png)

 > Android Hybrid tests can be added to Android test lists and iOS Hybrid tests can be added to iOS test lists.

3. In order to add a test in the test list, double click the list to open it in the middle pane of Test Studio and click on the Edit button:

	![edit](/img/test-studio-mobile/test-execution/test-list-execution/fig4.png)

4. Select one or multiple tests and add them in the test list by clicking the arrow and click **Done**. You can also add tests by double clicking them.

	![add test](/img/test-studio-mobile/test-execution/test-list-execution/fig5.png)

	The test now appears in the test list.

	![test list added](/img/test-studio-mobile/test-execution/test-list-execution/fig6.png)

	> You can also add tests using drag&drop directly from the project explorer into the test list.

5. In order to execute the test list ensure it is open and click on the **Run** button or press **F5**.

	![run test list](/img/test-studio-mobile/test-execution/test-list-execution/fig7.png)

	You can also run a single list on multiple devices from the same type. Open the test list, and click the small arrow right next to the play button and choose the **Run on multiple** option:

	![run on multiple](/img/test-studio-mobile/test-execution/test-list-execution/fig9.png)

<a id="results"></a>
The results of the test list run appear in the **Results** pane.

![results](/img/test-studio-mobile/test-execution/test-list-execution/fig8.png)

Double-click a test list in the Results view to see the result of each test. Double-clicking a test in this list drills down to show the steps of that test. The bread crumb trail at the top of the panel now shows the test list followed by the test name.

![Drill down the results](/img/test-studio-mobile/test-execution/test-list-execution/fig10.png)

Click the top level in the bread crumb trail to jump directly back to the test list result.

###See Also

*	[Playback a Test]({% slug ms-quick-execution%})
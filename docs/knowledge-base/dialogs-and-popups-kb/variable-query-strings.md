---
title: Variable Query Strings
page_title: Variable Query Strings
description: Often web applications are designed such that they use a variable or random query string in the URL address. The order status page at Newegg.com is a good example of this. Every time you go to their order status page, a random ID is added to the URL. Here is how Test Studio can handle these dynamic URLs.
position: 1
---
# How to Deal with Variable Query Strings in URLs

Often web applications are designed such that they use a variable or random query string in the URL address. The order status page at Newegg.com is a good example of this. Every time you go to their order status page, a random ID is added to the URL as shown in this screen shot:

![Random string][1]

When recording this type of web application using Test Studio's default recording settings, it will start recording multiple page nodes in the Elements Explorer each time you record a test that interacts with this type of web page. You will also see what will appear to be duplicate elements, one for each duplicate page node.
 
In this screen shot I recorded entering and leaving the Newegg order status page three times. Notice how there are three different logout elements under three different page nodes. All three are actually the same logout link on the same webpage:

![Duplicate elements][2]

## Solution

You can easily recover from what appears to be a mess. Before I explain how to clean up this mess, I'd like to reassure you that what looks like a mess in Elements Explorer is not really a problem during test execution. The framework actually doesn't use the page nodes during test execution. It only uses the Find Expressions for the elements that the test steps interact with. So even though you have multiple page nodes, each with their own element, executing the recorded test will work correctly since it is actually ignoring the variable URL.

To clean things up requires just two steps:

1. Modify the **CompareMode** property for all page nodes involved (click on a page node in Elements Explorer, then open the Properties window). Change it from **FullPathAndQuery** to **FullPath**.

	![Change compare mode][3]

2. After modifying each page node involved the Element Explorer will refresh itself. Now your duplicate pages will be merged into one. Any duplicate elements will be removed leaving behind only the unique elements displayed under the now truly unique page nodes. Here's a screenshot after performing this process on my test recording:

	![Mergeing nodes][4]

In order to avoid this duplication in the feature recording of your tests change change the **Compare Mode** in **Project Settings**:

1. Open Project Settings.

	<table id="no-table">
	<tr>
	<td>![Standalone][5]<br>**Standalone version**</td>
	<td>![VS Plugin][6]<br>**VS Plugin**</td>
	<tr>
	<table>

2. Click **Recording Options**.

3. Change the **Compare Mode** from **FullPathAndQuery** to **FullPath**.

	![Recording Options][7]

After making this change, recording your test scripts will automatically merge duplicate pages and elements into just one page node with the unique elements showing under it.

## Connecting to HTML Popup Windows

The other place you may have to deal with variable query strings is in the URL of pop-up windows. Unfortunately these have to be cleaned up manually after each recording. Test Studio currently does not have a feature to automatically strip or ignore the query strings when recording and/or executing a "Connect to pop-up window" test step. If you try to execute a test that connects to a pop-up window with a variable query string in the URL, the test will probably fail because you are almost guaranteed to get a different query string at run time then you had when you recorded your test script. Here's a screen shot of an example:

![Pop up URL][8]


The good news is that it's quite simple to strip the query string after recording your test script, allowing your test to work the way you intended. Simply delete all characters at the end of the URL, starting with the "?" character (which defines the start of a query string). Also check **IsUrlPartial** property. For example:

![Partial Match][9]


[1]: /img/knowledge-base/dialogs-and-popups-kb/variable-query-strings/fig1.png
[2]: /img/knowledge-base/dialogs-and-popups-kb/variable-query-strings/fig2.png
[3]: /img/knowledge-base/dialogs-and-popups-kb/variable-query-strings/fig3.png
[4]: /img/knowledge-base/dialogs-and-popups-kb/variable-query-strings/fig4.png
[5]: /img/knowledge-base/dialogs-and-popups-kb/variable-query-strings/fig5.png
[6]: /img/knowledge-base/dialogs-and-popups-kb/variable-query-strings/fig6.png
[7]: /img/knowledge-base/dialogs-and-popups-kb/variable-query-strings/fig7.png
[8]: /img/knowledge-base/dialogs-and-popups-kb/variable-query-strings/fig8.png
[9]: /img/knowledge-base/dialogs-and-popups-kb/variable-query-strings/fig9.png


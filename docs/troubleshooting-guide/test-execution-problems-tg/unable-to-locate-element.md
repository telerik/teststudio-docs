---
title: Unable to Locate Element
page_title: Unable to Locate Element
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/troubleshooting_guide/test-execution-problems/unable-to-locate-element.aspx, /user-guide/troubleshooting_guide/test-execution-problems/unable-to-locate-element
position: 1
---
# Unable to Locate Element

<div style="border: 1px solid currentColor; margin-bottom: 10px; background-color: #fafad2;">
<pre>
'5/27/2011 4:31:42 PM' - 'Fail' : 4. Click 'CLink'
------------------------------------------------------------
Failure Information:
~~~~~~~~~~~~~~~
Unable to locate element. Details: Attempting to find [Html] element using
Find logic
 (Html): [tagname 'Exact' a] AND [TextContent 'Exact' ABCDE]

Unable to locate element. Search failed!
</pre>
</div>

or

<div style="border: 1px solid currentColor; margin-bottom: 10px; background-color: #fafad2;">
<pre>
'6/3/2011 10:47:24 AM' - 'Fail' : 1. Verify element 'ListItem4' 'is' visible.
------------------------------------------------------------
Failure Information: 
~~~~~~~~~~~~~~~
Unable to locate element. Details: Attempting to find [Html] element using 
Find logic 
 (Html): [id 'Exact' rpbNavigator_i3_rtvROOFER][tagIndex 'Exact' li:2]

Unable to locate element. Search failed!
</pre>
</div>

There are many possible causes of this problem. Before we can fix it we have to narrow down what the root cause is. To do that we have to answer to the following questions:

1.&nbsp; Is the test on the right page when the error occurred? Obviously if the test did not advance to the correct page, or the server experienced a fatal error trying to render the page, the element the test is looking for won't be there.

2.&nbsp; Does the element actually exist on the page? Even if we're on the correct page, maybe the element isn't present for some reason. For example you have a "Save" button that isn't displayed until you make a change to the data being displayed.

3.&nbsp; Did the structure of the page change such that the find logic the test is using is no longer valid? Most of our customers are using test automation to test a website that is under development. Changes to the website may move the element to a new location, or give it a new name/ID which causes the test to be able unable to find the element where it used to be (or the name/ID it used to have).

- Is the element at a new location in the HTML?
- Did the name/ID for the element change?
- Does the element use a dynamic ID that's different every time you run the application?
- If the find logic is relying on some text content, did that text change?
- Is the element in a frame which has a dynamic ID, Name, URL or it uses a Dynamic query?


Let's go through the list above in order to narrow down what caused the failure.

## Was the test on the right page when the error occurred?

There are a couple of ways to determine this.

1.&nbsp; Open the test in Test Studio and run it from the **Record tab** and simply watch the test run in the browser window. Make careful note of what page was displayed when the test stops on the error. 

 To make this even easier you can select "**Auto-Pause On All Errors**" from the **Quick Execution Options** before running your test. By doing this Test Studio will automatically pause the test, leaving the browser open, when it detects the failure. Then you can easily see whether or not the test is on the right page.

![On Any Errors][1]

2.&nbsp; Another option is to look at the image that was captured after the test executes and detects the failure. You get to the image by clicking on the X of the failed step, then clicking the "Images" tab. This will display both the expected image and the actual image of what was displayed in the browser window at the time the error occurred.

![Step Failure Details][2]

If we determine that the test is not on the right page we have to further diagnose why not. Some possibilities include:

- The application is broken and the page won't load. You can determine if this is the case by manually testing your application. 

- The button was disabled when the test tried to click on it. Test scripts will run as fast as possible. Test Studio doesn't take the time to verify whether or not a button is clickable. It only verifies that it is present and visible. If there's a delay for any reason then Test Studio will try to click on it before it's ready. This end result is that the test didn't navigate to the next page. To overcome this you need to add a "<a href="/knowledge-base/verification-kb/disabled-attribute-html" target="_blank">Wait for enabled</a>" test step.

Maybe the button is disabled because the input validation didn't succeed. Some applications are designed such that the "Next/Submit/Search" button is only enabled after the user enters some data into the form. For HTML applications, setting "Simulate Real Typing" <a href="/features/test-maintenance/test-step-properties" target="_blank">test step property</a> for text input, or "Simulate Real Click" for checkboxes and other elements may help resolving this.

If your application uses jQuery, maybe you need to invoke the <a href="/advanced-topics/coded-samples/html/jQuery-events-do-not-fire" target="_blank">jQuery OnChange</a> event in order to make the data validation in your application run. 

- The test script didn't wait long enough for the page to load. As it was mentioned earlier, the test script will try to run as fast as possible. Test Studio makes its best effort to synchronize with your application being ready, but that's not always possible, especially if an AJAX post back is happening. There's no hook or indication we can reliably use to detect when this is occurring or when it is finished.

> We recommend adding a "<a href="/features/recorder/verifications/Wait" target="_blank">Wait for...</a>" test step to make the test synchronize with your application. Select some UI element (some piece of text) that will only show up when your application has finished loading the page to create the wait step. To delay the test execution certain time frame - an "<a href="/features/custom-steps/execution-delay" target="_blank">Execution Delay</a>" step could be introduced to the test as well. 

## Does the element actually exist on the page?

Start by using the same steps to determine if the test is on the right page. Look to see if the element can be seen on the page. If the test is trying to find an element that can't be easily seen on the web page (e.g. a hidden \<div> or a listbox item, etc.) look inside the DOM.

Let's take the second failure list above as an example. The find logic is saying find an element that has the id "*rpbNavigator_i3_rtvROOFER*" then find the third \<li> element (because it's zero based) underneath it. Here's what the DOM looked like when the test failed:

```
<div id="rpbNavigator_i3_rtvROOFER" >
	<div id="rpbNavigator_i3_rtvROOFER_RadTreeViewContextMenuROOFER" >
		<div id="rpbNavigator_i3_rtvROOFER_RadTreeViewContextMenuROOFER_detached" >
			<iframe src="javascript:'';"></iframe>
			<ul style="cssFloat: left">  </ul>
		</div>
		<input id="rpbNavigator_i3_rtvROOFER_RadTreeViewContextMenuROOFER_ClientState" >
	</div>
	<input id="rpbNavigator_i3_rtvROOFER_ClientState" >
</div>
```

Notice that there are no \<li> elements contained in the unordered list (the \<ul> element). Here's a case where the dropdown combobox doesn't get populated until you actually open the combobox. Opening the combobox initiates an AJAX postback which returns the list of items to populate in the combobox. The solution was to add a test step to open the combobox before our failing step.

## Did the structure of the page change? This can cause the find logic the test is currently trying to use to become invalid?

1.&nbsp; **Is the element at a new location in the HTML?**

If you use XPath or TagIndex to locate the element and the structure of the page has changed after the recording, the test might fail or Test Studio will click on a wrong element that has taken the place of the right element. In this case you should open the DOM  again and check whether the structure hasn't changed. Using only XPath or TagIndex for locating an element is not very reliable and we don't recommend it.

2.&nbsp; **Did the name/ID for the element change?**

Make sure the name/IDF didn't change after recording the test. You can compare the find expression for the particular element and the DOM tree of the application:

```
<html>
<head>
</head>
<body>
    <div id="myDiv">
        Test
    </div>
</body>
</html>
```

*DOM tree of our application which shows us the ID of the DIV.*

![id][3]

*Find expression of the DIV.*

3.&nbsp; **Does the element use a dynamic ID that's different every time you run the application?**

 If the ID is completely different every time then you shouldn't use it. The ID could be only partially dynamic. In this case you should change the find rule to **contains** and type only the static part of the ID:

![Contains][4]

4.&nbsp; **If the find logic is relying on some text content, did that text change?**

 Here you can use the same approach like in case of changing name/ID or dynamic IDs.

5.&nbsp; **Is the element in a frame which has a dynamic ID, Name, URL or it uses a Dynamic query?**

 This is remedied by using the tilde (~) character to indicate a partial match. This can be used in the BaseURL, Id, and Name fields. If the Src string contains a dynamic query, set UseQuery to False.

 Visit our <a href="/getting-started/test-recording/Frames" target="_blank">Frame article</a> for detailed information.

[1]: /img/troubleshooting-guide/test-execution-problems-tg/unable-to-locate-element/fig1.png
[2]: /img/troubleshooting-guide/test-execution-problems-tg/unable-to-locate-element/fig2.png
[3]: /img/troubleshooting-guide/test-execution-problems-tg/unable-to-locate-element/fig3.png
[4]: /img/troubleshooting-guide/test-execution-problems-tg/unable-to-locate-element/fig4.png
---
title: Ample Timetouts
page_title: Ample Timetouts
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Setting Ample Timeouts in your Test#

*Your tests often fail because of a synchronization issue. For instance, you're testing an ASP .NET application. You have a test step that clicks on a button. This button is dynamically generated after certain conditions are met. However, when these conditions are met, it still takes 40 seconds for the app to perform a postback and generate the button. Your test fails because Test Studio attempts to click on the button after it's supposed to have been generated, but without waiting an ample amount of time for it to appear. How can you avoid similar synchronization problems?*

##Solution##

The majority of test steps in any given test will consist of interactions with elements within the browser. If the element associated with a given step can't be found, the step doesn't immediately fail. Instead, it waits a set amount of time for the element to appear.
 
By default, each step is set to use the Global **WaitOnElementsTimeout** as defined in the <a href="/getting-started/test-execution/quick-execution" target="_blank">Quick Execution Options</a>. The default is 30,000 milliseconds (30 seconds), which can be adjust from the TimeOut ribbon:

![TimeOut][1]

The corresponding <a href="/getting-started/test-execution/test-list-settings" target="_blank">Test List Setting</a> is **ElementWaitTimeout**.
 
Each test step will wait 30 seconds for the element to appear in the page's DOM. So, if you have a button to be clicked but it's not there yet, the Click step will wait for 30 seconds for the element to appear. If it appears in that time, it will be clicked and the test will continue executing. If it's still not there after 30 seconds, the test will fail with a Timed Out: Waiting for Element exception. In most situations the elements will appear immediately and the 30 seconds timeout will be ample.
 
In other cases, however, you will need to increase the timeout for a step in order to get it to work. You can either increase the Global WaitOnElementsTimeout to affect all elements, or edit the properties of a single step. For a single step, change **UseStepWaitOnElementsTimeout** to True and increase the **WaitOnElementsTimeout** to an ample number.

![Step properties][2]

[1]: /img/knowledge-base/test-automation-kb/ample-timetouts/fig1.png
[2]: /img/knowledge-base/test-automation-kb/ample-timetouts/fig2.png
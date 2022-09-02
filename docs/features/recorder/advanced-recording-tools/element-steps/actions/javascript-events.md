---
title: JavaScript Events
page_title: JavaScript Events
description: "Test Studio recorder allows you to add steps to invoke JS events. Insert a test step to invoke JavaScript events on specific element. Invoke Onclick event during Test Studio test runtime. Invoke OnChange event, OnSubmit event and other JavaScript events during automated test execution."
position: 2
---
# JavaScript Events

Test Studio allows you to invoke JavaScript events against an element from the tested page. You can choose the suitable one from various built in events and add a step to your test.

JavaScript events are often used instead of simulating real user behavior.Find out how to include a step to trigger a JavaScript event. 

## Add a Step to Invoke a JavaScript Event

1.&nbsp; Create a test and start a recording session. Navigate to the tested application - in this example we use a web test and the <a href="https://www.telerik.com/" target="_blank">Telerik official page</a>.

2.&nbsp; If the recording browser window is large enough (it behaves differently if the browser window is shrunk) the __All Products__ list appears after you hover over it with the mouse. 

> __Note__
> 
> The recommended approach to automate opening the __All Products__ list is to use the _Mouse HoverOver Step_. But you can also use the __JS events__ related to that element and trigger the action through the JavaScript. 

3.&nbsp; Highlight the element and choose the option to <a href="/automated-tests/recording/hover-over-highlighting#build-step" target="_blank">Build Step...</a>.

4.&nbsp; The __Advanced Recording Tools__ window gets opened directly on its __Element Steps__ tab with that element selected in the DOM. Switch to the _Actions_ section and choose the __JavaScript Events__ dropdown. Choose the JavaScript event and click the **Add Step** button to inser the step into test. 

![Add step to invoke JavaScript Events][1]

5.&nbsp; Some of the <a href="/features/test-maintenance/test-step-properties" target="_blank">step properties</a> are specific for the JS event step and allow you to modify the event to be triggered.

![SJavaScript Event step properties][2]

## What Events Should Be Triggered? 

<a href="https://firefox-source-docs.mozilla.org/devtools-user/page_inspector/how_to/examine_event_listeners/index.html" target="_blank">Firefox Developer Tools shows all specific events bound to an element</a>. These can vary depending on the component and implementation. If you are not sure what events or sequence of events trigger the expected behavior of an element, you might need to contact the application development team.

## Create a JavaScript Event Step without Recording Session

The automated tests require maintenance and often you find out it is necessary to __add new steps in the already recorded test__ to ensure its stability when running on different environments. For such cases Test Studio provides the <a href="/automated-tests/test-execution/partial-test-execution" target="_blank">options for partial test execution</a>, which allow you to get to a certain point of the test and record the additional steps.

For the cases when the project and scenarios are quite complex, you can __add steps for an already recorded element__ and without starting a recording session. The below list guide you through the steps for this:

1.&nbsp; Open a test in which you need to add a step. Choose an element from the __Elements Explorer__.
<br>

2.&nbsp; Click the **Step Builder** pane to activate it. Under the __Actions__ and __Verification__ sections, you can see the options corresponding to the type of selected element.

3.&nbsp; Choose the __JavaScript Events__ section under __Actions__ and select the event you need. Click the **Add Step** button to insert the step in the test.

![Step Builder Verification][2]

> __Tip__
><br>
><br>
> Check <a href="https://www.telerik.com/videos/teststudio/how-to-add-test-steps-from-the-test-builder" target="_blank">this short video</a> demonstrating how to add a step for an existing element in Test Studio.

[1]: /img/features/recorder/advanced-recording-tools/element-steps/actions/javascript-events/fig1.png
[2]: /img/features/recorder/advanced-recording-tools/element-steps/actions/javascript-events/fig2.png

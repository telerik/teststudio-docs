---
title: Element Steps
page_title: Element Steps Overview
description: "Test Studio Advanced Recording Tools lets you add steps against a selected element during recording. Select an element from the DOM tree and switch to Element Steps tab to choose what step to add. Elements steps can be action or verification type."
position: 0
---
# Element Steps Tab

The __Advanced Recording Tools__ window allows you to build various steps specific for a given element. You can manually select an element from the <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">DOM Explorer tab</a> or use the <a href="/features/recorder/highlighting-menu/element-options" target="_blank">highlighting menu to bring up the step options for an element</a>.

Find out more about adding element steps below.

## Choose an Element to Build Step

If there is no element selected in the __DOM Explorer__, the __Element Steps__ remains empty.

![Select Element from DOM][1]

Choose an element from the DOM Explorer, or use the highlighting menu to locate an element in the DOM. The __Elements Steps__ tab shows the __Actions__ and __Verifications__ options relative for the selected element. Choose a step and click the **Add Step** button to add it into the test.

![Add Step][2]

## Actions

![Actions][3]

The __Actions__ section gives you the option to add different type of actions for an element - mouse clicks and actions, scrolling and JavaScript events. 

> __Tip__
> 
> The default mouse click steps and scrolling options can be added directly through the <a href="/automated-tests/recording/hover-over-highlighting#options-in-the-highlighting-menu" target="_blank">highlighting menu</a>. 

- __Mouse Actions__ are invoked as if the real user was directly using the mouse. They range from different Left and Right mouse button actions, for which you could <a href="/features/recorder/advanced-recording-tools/element-steps/actions/adv-mouse-actions" target="_blank">specifying where to send the click</a>, to <a href="/features/recorder/highlighting-menu/mouse-actions" target="_blank">hover over</a> and <a href="/features/recorder/advanced-recording-tools/element-steps/actions/drag-and-drop" target="_blank">drag&drop actions</a> to help covering all scenarios.

- <a href="/features/recorder/highlighting-menu/scroll-actions" target="_blank">__Scroll Actions__</a> are used to ensure that the element is visible on the screen. You can scroll the element to three different positions - top, bottom and center of the page.

- <a href="/features/recorder/advanced-recording-tools/element-steps/actions/javascript-events" target="_blank">__JavaScript Events__</a> are used to manually invoke an event against the highlighted element.

## Verifications

![Verifications][4]

Once you have added the necessary actions, you still have to verify that those actions lead to a successful result and everything happened as expected. There are several ways to verify elements in Test Studio:

- <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification" target="_blank">Quick Verification</a> - create an easy verification from the Quick Tasks menu.

- <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification" target="_blank">Advanced Verification</a> - craft a custom verification from the Sentence Verification Builder.

- <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/wait" target="_blank">Wait</a> - does not continue until the comparison is true.

- <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/extraction" target="_blank">Extraction</a> - extract an element's value and reuse it later in your test.

- <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/image-verification" target="_blank">Image Verification</a> - this feature is based on an element’s visual rendering rather than the properties or attributes of that element.

- <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/text-from-image" target="_blank">Text from Image</a> - this feature checks the text from an image and compares it to the expected value.

Verifications in Test Studio allow you to:

- Measure against multiple criteria at one time.
- Build these measurements in an interactive manner without code.
- Detect if elements are in a particular state (e.g. is visible, exists).
- Detect if attributes and properties compare with specific values.
- Verify content, attributes, images, image texts, styles, visibility, drop-down list selections, checkboxes, radio buttons, tables and property values.

Test Studio implements verification through "sentences" that compare a portion of an element to a value, such as:

- textbox content is equal to 'order 2011'
- image path contains 'http://www.telerik.com'
- wait for element to exist

> Test Studio cannot read and verify against the contents of a PDF file loaded in the browser, as it does not have a DOM structure like a traditional web page. If you can store that information in a file type such as XLS, XML, CSV, or a SQL database, then you can use the <a href="/features/data-driven-testing/Overview" target="blank">Data Driving</a> feature. 

[1]: /img/features/recorder/advanced-recording-tools/element-steps/steps-overview/fig1.png
[2]: /img/features/recorder/advanced-recording-tools/element-steps/steps-overview/fig2.png
[3]: /img/features/recorder/advanced-recording-tools/element-steps/steps-overview/fig3.png
[4]: /img/features/recorder/advanced-recording-tools/element-steps/steps-overview/fig4.png

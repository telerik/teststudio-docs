---
title: Overview
page_title: Overview
description: "Add steps against element during recording. Step Builder allows you to add new action and verification steps. Select an element from Elements repository and add a step against that. Wait for an element to exist to be visible. Codeless steps against element from the DOM tree."
position: 0
---
# Add Element Steps #

You can <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">explore the DOM tree</a> during a recording session and build element steps. To do that, you need to select the target element in the DOM Explorer tab first.

![Select Element from DOM][1]

When you select an element from the DOM Explorer, you will see the **Actions** and **Verifications** tabs with available steps for that element. Each of those tabs has different types of steps that you can configure and add to your test. Simply choose the required step and click the **Add Step** button. You can make additional configurations to the newly added step in the <a href="/features/test-maintenance/test-step-properties" target="_blank">Step Properties</a> pane in Test Studio.

![Add Step][2]

You can also build steps from the <a href="/features/custom-steps/overview" target="_blank">Step Builder</a> in Test Studio, after the recording session is closed.

## Actions ##

![Actions][3]

In order to automate your test scenario, you need to record different actions against the application under test. Test Studio will capture your mouse and keyboard actions automatically, but you can also add more actions. Check out the 3 categories below:

- <a href="/features/recorder/advanced-recording-tools/element-steps/actions/mouse-actions" target="_blank">Mouse Actions</a> are invoked as if the real user was directly using the mouse. They range from different Left and Right mouse button actions to hover over and drag & drop actions to cover all scenarios.

- <a href="/features/recorder/advanced-recording-tools/element-steps/actions/scroll-actions" target="_blank">Scroll Actions</a> are used to ensure that the element is visible on the screen. You can scroll the application in three different ways - top, bottom and center.

- <a href="/features/recorder/advanced-recording-tools/element-steps/actions/javascript-events" target="_blank">JavaScript Events</a> can be invoked against the highlighted element.

## Verifications ##

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
- Verify content, attributes, images, image texts, styles, visibility, drop-down list selections, checkboxes, radio buttons, tables and Silverlight property values.

Test Studio implements verification through "sentences" that compare a portion of an element to a value, such as:

- textbox content is equal to 'order 2011'
- image path contains 'http://www.telerik.com'
- wait for element to exist

> Test Studio cannot read and verify against the contents of a PDF file loaded in the browser, as it does not have a DOM structure like a traditional web page. If you can store that information in a file type such as XLS, XML, CSV, or a SQL database, then you can use the <a href="/features/data-driven-testing/Overview" target="blank">Data Driving</a> feature. 

[1]: /img/features/recorder/advanced-recording-tools/element-steps/steps-overview/fig1.png
[2]: /img/features/recorder/advanced-recording-tools/element-steps/steps-overview/fig2.png
[3]: /img/features/recorder/advanced-recording-tools/element-steps/steps-overview/fig3.png
[4]: /img/features/recorder/advanced-recording-tools/element-steps/steps-overview/fig4.png

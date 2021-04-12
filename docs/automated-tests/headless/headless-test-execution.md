---
title: Executing Tests in Headless Mode
page_title: Executing Tests in Headless Mode
description: "Execute tests in headless mode in Chrome browser. How can I execute a test in headless chrome mode. Can I execute a test list in Headless browser."
position: 0
---
# Headless Test Execution in Test Studio

Headless testing improves both the effectiveness and efficiency of your testing process. Test Studio supports execution of all existing web tests in headless mode for Chrome browser.

Find out more about this type of execution for UI tests in the below article.

## What is Headless Testing?

Running web tests in __headless browser mode uses a web browser to run the scripts, but skips loading the browser's UI__. That means that the HTML page under test is not getting rendered during the run, so the __overall execution is much faster__. Another advantage is that tests bypass interacting with the page to manipulate the browser more directly, which __reduces the failures due to UI-related interactions__.

> __Tip__
><br>
><br>
> Find out further advantages of <a href="https://www.telerik.com/blogs/what-is-headless-browser-testing-when-and-why-use-it" target="_blank">headless testing in this Test Studio blog post</a>.

{% if site.has_cta_panels == true %}
{% include cta-panel-teststudio-introduction.html %}
{% endif %}

## How to Execute Test in Headless Browser Mode?

Test Studio currently __supports the headless mode for Chrome browser__ and you can <a href="/automated-tests/test-execution/quick-execution" target="_blank">execute any existing test</a> in your automation project selecting headless Chrome type of browser.

![Execute Test in Headless Mode](/img/automated-tests/headless/fig1.png)

Once you initiate the headless browser run in quick execution, you __can continue interacting freely with your desktop__. Since there is no UI loaded, you don't need to wait for the run to finish. The indication for the test run process is the <a href="/automated-tests/troubleshooting/visual-debugger" target="_blank">Visual Debugger</a> at the lower right corner of your display - right above the system tray. This toolbar will indicate the currently executed step.

![Visual Debugger in Headless chrome Mode](/img/automated-tests/headless/fig2.png)

## Do I Need to Modify the Existing Tests to Execute Them in Headless Chrome Browser?

Since there is no UI loaded during the headless test execution, it is much faster than the usual test run with active browser. Therefore, we __recommend to review the existing web tests and determine if these contain sufficient <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/wait" target="_blank">wait</a> and/or <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/quick-verification" target="_blank">verification steps__ to ensure stable and consistent behavior during headless browser execution.

### What Are the Wait/Verification Steps and When Do I Need Them?

The wait and verify steps are the mechanism in Test Studio to __align the test execution speed with the speed of application responsiveness__. This type of steps are always related to an element on the page and are slowing down the execution, depending on how fast the application handles the actions in test - thus, __these are not actually affecting the overall amount of time required for the test run__.

The basic concept of adding a short delay as a wait or verify step is to __ensure the state of the application under test is what you expect it, before sending the next action__. The straight forward example is to ensure an element is visible, or exists, on the page, after the page is reloaded. However, don't underestimate the dynamic content on a page, without reloading it. Here are some common examples:

* __Selecting a value from dropdown control__ - verify that the option to select is visible, or exists, before you select it from the list.
* __Entering some text, which gets populated anywhere on the page__ - verify that the expected element's text content is updated accordingly.
* __An element on page changes visually, after some data is submitted__ - <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/advanced-verification" target="_blank">verify the style or attributes of an element</a>.

## Execute Tests in Test Lists Using Headless Chrome Browser

Similar to the existing web tests, all <a href="/automated-tests/test-lists/test-lists-standalone#automated-type-of-test-list" target="_blank">existing automated test lists with web tests</a> can be executed in headless browser mode for Chrome. To set this type of browser for the test list, __modify its <a href="/features/test-lists/test-list-settings#web-tab" target="_blank">Web settings</a>__.

![Test Lists in Headless browser Mode](/img/automated-tests/headless/fig3.png)
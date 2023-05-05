---
title: Invoke Blind Mouse Click
page_title: Invoke Blind Mouse Click
description: "Invoke Blind (Element Independent) Mouse Click in Test Studio test"
position: 1
---
# Invoke Blind Mouse Click

## PROBLEM

You need to click on an element. A "normal" Test Studio click is a complex action. The element that needs to be clicked has to be located first. The click itself works directly on the DOM. There are some situations where you will need to invoke a true simulated desktop click (identical to the physical action of using the mouse to click on the element). This type of click disregards the element it is clicking (hence the term "blind"). This is often used as a temporary solution to an automation problem. 

## SOLUTION

Start the Test Studio recorder and navigate to your application. Go to the page in your application that contains the element that needs to be clicked. Now you need to pick a reference element. A reference element will serve as a reference point. This is necessary because "blind" clicks use coordinates within the browser in order to locate the point that needs to be clicked. The reference element you pick should be a "stable" element on the same page. "Stable" means that Test Studio should be able to find it every time. Simple, static (i.e. non-dynamically generated) elements are best. In most cases it's a bad idea to use the element you're trying to click as your reference element. 

1.&nbsp; Highlight the reference element and from the context menu choose **Locate in DOM**.

![Locate in DOM][1]

a. Select the element from the DOM Tree.

b. Select **Left Click** from **Mouse Actions**.

c. Select **Specific Point** value from **Location** dropdown. 

![Specific Point][2]

2.&nbsp; A crosshair will appear in the browser. Aim it at the point that needs to be clicked (i.e. just drag it over the control you would like to click):

![Crosshair][3]

3.&nbsp; Click **Add Step**.

![Add Step][4]

4.&nbsp; Once done a new step with the prefix "Desktop command" should appear in your test.

![Test Steps][5]

> __Note!__ If the requirement is to invoke a blind mouse click outside the page under test you could use the <a href="/testing-framework/write-tests-in-code/intermediate-topics-wtc/mouse-manager" target="_blank">Mouse Manager</a> in a coded step and click on specific coordinates. 


[1]: /img/troubleshooting-guide/test-execution-problems-tg/invoke-blind-mouse-click/fig1.png
[2]: /img/troubleshooting-guide/test-execution-problems-tg/invoke-blind-mouse-click/fig2.png
[3]: /img/troubleshooting-guide/test-execution-problems-tg/invoke-blind-mouse-click/fig3.png
[4]: /img/troubleshooting-guide/test-execution-problems-tg/invoke-blind-mouse-click/fig4.png
[5]: /img/troubleshooting-guide/test-execution-problems-tg/invoke-blind-mouse-click/fig5.png


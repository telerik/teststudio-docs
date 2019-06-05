---
title: Grayed Out Controls
page_title: Grayed Out Controls
description: "Dealing with Grayed Out Controls in Test Studio."
position: 1
---
#Dealing with Grayed Out Controls#

*My application contains "grayed out" (i.e. visible but not functioning) controls, like buttons. These controls cause unpredictable behavior when performing UI automation.*

##Solution##

The crux of the matter is that Test Studio cannot recognize whether a control is, in fact, grayed out and thus unavailable. "Grayed out" it used somewhat figuratively in this context - there are a lot of ways to signify that an element is not currently available to the user. Usually it's a gray transparent screen that covers the background or an AJAX loading animation. This is a typical implementation for modal dialogs, but also for AJAX loading screens and others.

Let's take a simple situation in order to demonstrate this: your application contains a button that gets grayed out at some point when a specific event is triggered.

![Grayed out][1]

While recording a test for this application, you would wait out the loading screen and then click the button. This gets recorded as a Click Step. When Test Studio invokes this step during test execution, here's what happens:

Test Studio immediately recognizes that the intended button exists in the DOM structure of the page. It will ignore that it's grayed out. In fact, the grayed out effect is actually just a transparent element that is placed "higher" than the button. Test Studio immediately invokes a click on the button in the DOM (or a regular, simulated click depending on how SimulateRealClick is set) and it will perceive the click as "passed." However, the button is still grayed out at this point and the event associated with the click is not fired. This will probably cause one of your subsequent steps to fail if they rely on the event being fired.

In order to avoid this problem, you have to wait for the loading screen to go away before you proceed with your test. The crudest way to do this is to introduce a fixed delay, but this is not recommended. Unfortunately it might be a bit tricky to determine the element that's "blocking" the app (and that needs to be waited out).

From the example site above, let's trigger and then wait out the AJAX loading screen.

Determine which DOM element represents the loading screen and then wait for this element to disappear. This is a bit tricky because the loading screen appears only briefly - not enough time to highlight it. However, you can workaround this by simply clicking the element. This will add a new step and the element that is associated with that step (which happens to be the AJAX loading screen - actually a DIV). From here you can use the <a href="/getting-started/test-recording/step-suggestions" target="_blank">Step Suggestions</a> feature in order to create a Wait for ExistsNot step for this element. You can change the role from a Verify to a Wait with the <a href="/features/test-maintenance/test-steps-context-menu" target="_blank">Test Step Context Menu</a>.

<a href="http://screencast.com/t/xoeTif8LoU8c" target="_blank">This</a> video demonstrates this approach.

If you're using the Telerik Testing Framework, this is harder to implement. This is because you will need to manually determine which element represents the AJAX loading screen. In the demo app, this is a DIV element with an ID of RadAjaxLoadingPanel1Panel1. Once you've determined that, you can write the test that waits for it to not exist. Here's the code that triggers the AJAX loading screen and then waits for it to not exist:

```C#
// Launch a browser instance
Manager.LaunchNewBrowser(BrowserType.InternetExplorer);
 
The active browser
ActiveBrowser.NavigateTo("http://demos.telerik.com/aspnet-ajax/ajax/examples/loadingpanel/loadingimages/defaultcs.aspx");
 
// Find button that triggers AJAX request and click it
Find.ById<HtmlInputButton>("Button1").Click();
 
//Wait until the AJAX loading screen goes away
Find.ById("RadAjaxLoadingPanel1Panel1").Wait.ForExistsNot(10000);
 
//Now we're free to click around the page without worrying whether the click will actually occur
```
```VB
' Launch a browser instance
Manager.LaunchNewBrowser(BrowserType.InternetExplorer)
 
' The active browser
ActiveBrowser.NavigateTo("http://demos.telerik.com/aspnet-ajax/ajax/examples/loadingpanel/loadingimages/defaultcs.aspx")
 
' Find button that triggers AJAX request and click it
Find.ById(Of HtmlInputButton)("Button1").Click()
 
'Wait until the AJAX loading screen goes away
Find.ById("RadAjaxLoadingPanel1Panel1").Wait.ForExistsNot(10000)
 
'Now we're free to click around the page without worrying whether the click will actually occur
```

[1]: /img/advanced-topics/coded-samples/general/grayed-out-controls/fig1.png
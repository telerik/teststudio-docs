---
title: Annotator
page_title: Annotator
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Annotator

The annotator displays in the browser window the actions that Telerik Testing Framework is performing along with highlighting the UI element that it is acting upon. If the action does not involve a UI element (such as navigating to a URL or creating a cookie) the action is displayed at the top of the browsers window. Here is what the annotator looks like in action:

![Annotation][1]

## Activating the Annotator via the Application .config File

There are 2 methods to activating Telerik Testing Framework's automatic annotator. The simplest method is to activate it via the application .config file. By setting "annotateExecution" to true, the framework turns on the annotator and begins annotating all actions in the browser

````XML
<WebAii.Settings
  annotateExecution="true"
/>
````

## Activating the Annotator Programmatically

The next method is to turn on the annotator programmatically in your application. This is accomplished by placing this simple line of code in your unit test:

````C#
// Enable Annotated Execution.
Manager.Settings.AnnotateExecution = true;
// Disable Annotated Execution.
Manager.Settings.AnnotateExecution = false;
````
````VB
' Enable Annotated Execution.
Manager.Settings.AnnotateExecution = True
' Disable Annotated Execution.
Manager.Settings.AnnotateExecution = False
````

## Performing Your Own Annotation

You can also perform your own annotation programmatically using the Annotator class. First you must create an Annotator object passing into it which browser window to display annotation in. Once you have an Annotator object you can call one of the annotate functions. For example:

````C#
Annotator myAnnotator = new Annotator(ActiveBrowser);
myAnnotator.Annotate("This annotation message appears at the top of the browser document window");
myAnnotator.Annotate("This annotation message appears at the top left corner of the browser document window",
     350, OffsetReference.TopLeftCorner);
myAnnotator.Annotate(new Point(100, 300), "This annotation message appears under the point at 100,300 in the browser document window");
myAnnotator.Annotate(Find.ById("btn1").GetRectangle(), "This annotation highlights the Color On button");
````
````VB
Dim myAnnotator As Annotator = New Annotator(ActiveBrowser)
myAnnotator.Annotate("This annotation message appears at the top of the browser document window")
myAnnotator.Annotate("This annotation message appears at the top left corner of the browser document window", _
                      350, OffsetReference.TopLeftCorner)
myAnnotator.Annotate(New Point(100, 300), "This annotation message appears under the point at 100,300 in the browser document window")
myAnnotator.Annotate(Find.ById("btn1").GetRectangle(), "This annotation highlights the Color On button")
````

[1]: images/annotator/fig1.png



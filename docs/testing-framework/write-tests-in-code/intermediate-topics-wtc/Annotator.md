---
title: Annotator
page_title: Annotator
description: "Test Studio Testing Framework annotated coded tests runs. Use the Annotator to highlight the target element for each action from the coded test."
position: 1
---
<<<<<<< HEAD
# Annotator
=======
#Annotator
>>>>>>> 3a5a2429 (Fix headers, CTA banners and other)

The annotator displays in the browser window the actions that Telerik Testing Framework is performing along with highlighting the UI element that it is acting upon. If the action does not involve a UI element (such as navigating to a URL or creating a cookie) the action is displayed at the top of the browsers window. Here is what the annotator looks like in action:

![Annotation][1]

<<<<<<< HEAD
## Activating the Annotator via the Application .config File
=======
##Activating the Annotator via the Application .config File
>>>>>>> 3a5a2429 (Fix headers, CTA banners and other)

There are 2 methods to activating Telerik Testing Framework's automatic annotator. The simplest method is to activate it via the application .config file. By setting "annotateExecution" to true, the framework turns on the annotator and begins annotating all actions in the browser

````XML
<WebAii.Settings
  annotateExecution="true"
/>
````

<<<<<<< HEAD
## Activating the Annotator Programmatically
=======
##Activating the Annotator Programmatically
>>>>>>> 3a5a2429 (Fix headers, CTA banners and other)

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

<<<<<<< HEAD
## Performing Your Own Annotation
=======
##Performing Your Own Annotation
>>>>>>> 3a5a2429 (Fix headers, CTA banners and other)

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

[1]: /img/testing-framework/write-tests-in-code/intermediate-topics-wtc/annotator/fig1.png


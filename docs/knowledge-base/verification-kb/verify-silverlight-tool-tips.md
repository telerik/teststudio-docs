---
title: Verify Silverlight Tool-Tips
page_title: Verify Silverlight Tool-Tips
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#How to Verify Tool-Tips in Silverlight#

Verifying Silverlight tool-tips sometimes can be tricky. First we must understand that tool-tips are attached to elements and Test Studio has the ability to verify what the tool-tip is that is attached to a specific element. We don't try to get the tool-tip element itself and verify the tool-tip contents, because a tool-tip is just a property of the Silverlight UI element for which the tool-tip is intended to be displayed.

One other small hurdle is that in order to verify a tool-tip, it must first appear in the Silverlight Visual Tree, which is Microsoft's internal representation of the Silverlight application UI. The first trick is to <a href="/knowledge-base/test-automation-kb/invoke-mouse-hover" target="_blank">Invoke a Mouse Hover event</a>. By hovering the mouse over the element, it causes the tool-tip to appear in the UI, which also adds it to the Visual Tree. Once it appears you can try to add a tool-tip verification of your UI element.

In some cases, just highlighting the UI element in the recorder and adding a tool-tip verification doesn't work as expected.

![Highlight][1]

The problem is that the tool-tip is being applied to the parent RatingItem element and not the child Grid or TextBlock elements. To further complicate things, we can't simply find the RatingItem element in the DOM Explorer and try to use the Sentence Verification Builder to create a tool-tip verification. You can find the RatingItem element in DOM Explorer, but Test Studio won't be able to build a tool-tip verification for it.

Instead we have to resort to code to perform our tool-tip verification. First add the RatingItem element to the Project Elements.

1.&nbsp; Highlight the element. 
2.&nbsp; Click Locate in DOM. 
3.&nbsp; Highlight the parent *RatingItem* element and ensure it matches on the page. 

![Locate in DOM][2]

4.&nbsp; Right click the element in the DOM and select **Add to Project Elements**. 

Now we have an element reference we can use in a coded step. Next add a coded step as follows:

```C#
FrameworkElement elem = Pages.SilverlightToolkitSamples.SilverlightApp.AmusedRatingitem;

string actualTip = elem.ToolTipText;

Log.WriteLine(actualTip);

Assert.AreEqual<string>("Amused", actualTip);
```
 

```VB
Dim elem As FrameworkElement = Pages.SilverlightToolkitSamples.SilverlightApp.AmusedRatingitem

Dim actualTip As String = elem.ToolTipText

Log.WriteLine(actualTip)

Assert.AreEqual(Of String)("Amused", actualTip)
```

[1]: /img/knowledge-base/verification-kb/verify-silverlight-tool-tips/fig1.png
[2]: /img/knowledge-base/verification-kb/verify-silverlight-tool-tips/fig2.png




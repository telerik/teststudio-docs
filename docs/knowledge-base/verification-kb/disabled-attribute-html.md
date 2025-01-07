---
title: Disabled Attribute (HTML)
page_title: Disabled Attribute (HTML)
description: How to verify an HTML element attribute is disabled. Many website developers will setup buttons or other elements within the site to be "disabled" until a certain action occurs. When using Test Studio to test this, it is sometimes necessary to create a special verification that confirms that the button (in this example) is visible but disabled (not clickable/usable)
position: 1
---
#How to Verify the Disabled Attribute (HTML)

Many website developers will setup buttons or other elements within the site to be "disabled" until a certain action occurs. When using Test Studio to test this, it is sometimes necessary to create a special verification that confirms that the button (in this example) is visible but disabled (not clickable/usable). You can similarly verify that the disabled attribute no longer exists, indicating the button is clickable/usable.

 
For example, when you have a disabled or not disabled element on a page that needs to be verified/waited for, or you have another attribute within the markup of an element you wish to search for (you can modify this process for your own needs).

![Element Mapping][1]

##SOLUTION 1 (No Code)

1.&nbsp; Start recording.

2.&nbsp; 2.Navigate to the page/step with the disabled element you'd like to verify.

*	Enable hover over highlighting.
*	Hover the mouse over the applicable element
*	Choose **Build Step**
*	In the Build Step menu click **Attributes**
*	Choose the proper attribute and the its state.

![Add step][2]

3.&nbsp; **Click Add Step**.

4.&nbsp; A new Verify rule will be created within the Test at the location you specified. You can right click this step to **Change Role** and **Set as Wait**, if desired. 

##SOLUTION 2 (Using Code, also apples to Telerik Testing Framework)

There are several ways to indicate a disabled element in HTML. This solution will work for each type of <a href="/troubleshooting-guide/browser-inconsistencies-tg/disabled-attribute" target="_blank">disabled</a>. First, access the element from a <a href="/features/custom-steps/script-step" target="_blank">Coded Step</a>.

There are two ways to do that:

1.&nbsp; 1.Write the Find Logic yourself in code. Use this approach if you are using Telerik Testing Framework only. You can insert this logic in the same coded step that does the disabled verification.

```C#
Element e = Find.ByExpression("id=myInput");
```

2.&nbsp; Add the element to your Project Elements, then reference it from that source. Use this approach if you are using Test Studio Standalone version or the Visual Studio plugin.

```C#
HtmlInputText e = Pages.TryitEditorV14.FrameView.LnameText;
```

3.&nbsp; Once you have your Element e, here is the verification in code:

```C#
Assert.IsTrue(e.ToString().Contains("disabled"));
```

[1]: /img/knowledge-base/verification-kb/disabled-attribute-html/fig1.png
[2]: /img/knowledge-base/verification-kb/disabled-attribute-html/fig2.png

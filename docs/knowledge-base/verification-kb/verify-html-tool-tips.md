---
title: Verify HTML Tooltips
page_title: Verify HTML Tooltips
description: Verify HTML Tooltips in Test Studio web test. Check the tooltip text in a Test Studio test. 
position: 1
---
# Verify HTML Tool-Tips

There's more than one way to implement Tool-tips in HTML. They are usually implemented using the Title attribute that gets applied to elements. Consider this HTML code snippet:

````HTML
<p>Test Studio, made by <span name="myHtmlSpan" title="Telerik is a leading vendor of development, team productivity, and automated testing tools.">Telerik</span>, is a quantum leap forward in Web test automation.</p>
````

When you hover your mouse over the word Telerik, the tooltip will be displayed as shown in this screenshot:

## SOLUTION 1 (No Code)

![Tool tip][1]

1.&nbsp; Start recording and navigate to the testing page.

2.&nbsp; Highlight the "Telerik" span and click **Build Step**.

3.&nbsp; Under the Verifications choose **Attributes**.

4.&nbsp; Choose **title** as an attribute in the first drop down and Same in the second one.

![Verify title][2]  

5.&nbsp; Click **Add Step**. 

## SOLUTION 2 (Using Code, also apples to Telerik Testing Framework)

1.&nbsp; Create a <a href="/features/custom-steps/script-step" target="_blank">coded step</a>.

2.&nbsp; Write the code as follows:

````C#
Find.ByName<HtmlSpan>("myHtmlSpan").AssertAttribute().Value("title", ArtOfTest.Common.StringCompareType.Same, "Telerik is a leading vendor of development, team productivity, and automated testing tools.");
````

Now when you execute your test it will verify that the Title attribute, i.e. the tool-tip, of your HTML element contains the correct text.

Often verifying a tooltip will be much more complex. A lot of the time tooltips are loaded on demand.

**Note:** If you're using Telerik Testing Framework only (no Test Studio available), you'll need to do some research in order to determine how to identify the tooltip (your developers could give you some info). Tools like Firebug can help you inspect the tooltip and determine how to locate it. This can be very tricky especially if the tool-tip is loaded-on-demand or if it's not part of the DOM Tree. 

[1]: /img/knowledge-base/verification-kb/verify-html-tool-tips/fig1.png
[2]: /img/knowledge-base/verification-kb/verify-html-tool-tips/fig2.png


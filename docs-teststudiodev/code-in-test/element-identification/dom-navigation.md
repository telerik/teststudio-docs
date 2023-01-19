---
title: DOM Navigation
page_title: DOM Navigation - Test Studio Dev Documentation
description: DOM Navigation
position: 1
---
#DOM Navigation#

Once you have an element, you can navigate to other elements relative to this element. Navigation methods include:

* Getting the elements parent.

* Getting the elements sibling, either the next or the previous sibling in the DOM.

* Getting the elements child or children nodes. NOTE: There is a subtle difference between the two:
	* Child nodes - nodes directly underneath this node including any text nodes.

	* Children nodes - nodes directly underneath this node excluding any text nodes.
 
Suppose we have some HTML that looks like this:


```HTML
<div id="div1">
  DIV1 TEXT
       <div id="div2">
         DIV2 TEXT
           <span id="span1" class="style-span-1" lang="en-us">SPAN1 TEXT</span>
               <span id="span2" class="style-span-2">SPAN2 TEXT</span>
               <span id="span3" class="style-span-3">SPAN3 TEXT</span>
       </div>
</div>
```
Here is how we can navigate around the DOM once we have a starting element:

#### __[C#]__

        {{region }}

    // Let's start with the span1 element.
    Element span1 = Find.ById("span1");
    Element span2 = span1.GetNextSibling();
    Element span3 = span2.GetNextSibling();

    // Let's verify we got the right elements
    Assert.IsTrue(span1.IdAttributeValue.Equals("span1"), string.Format("Actual ID: {0}", span1.IdAttributeValue));
    Assert.IsTrue(span2.IdAttributeValue.Equals("span2"), string.Format("Actual ID: {0}", span2.IdAttributeValue));
    Assert.IsTrue(span3.IdAttributeValue.Equals("span3"), string.Format("Actual ID: {0}", span3.IdAttributeValue));

    // Now let's navigate backwards
    span2 = span3.GetPreviousSibling();
    span1 = span2.GetPreviousSibling();
    Assert.IsTrue(span1.IdAttributeValue.Equals("span1"), string.Format("Actual ID: {0}", span1.IdAttributeValue));
    Assert.IsTrue(span2.IdAttributeValue.Equals("span2"), string.Format("Actual ID: {0}", span2.IdAttributeValue));
    Assert.IsTrue(span3.IdAttributeValue.Equals("span3"), string.Format("Actual ID: {0}", span3.IdAttributeValue));

    // Now let's look at parent and children
    Element parentDiv = span1.Parent;
    // ChildNodes includes all nodes including text and comments. Children is a subset of ChildNodes.
    Assert.AreEqual(parentDiv.ChildNodes.Count, 4, string.Format("ChildNodes = {0}", parentDiv.ChildNodes));
    // Children are basically only markup children. (Does not include text or comments);
    Assert.AreEqual(parentDiv.Children.Count, 3, string.Format("Children = {0}", parentDiv.ChildNodes));

    span1 = parentDiv.Children[0];
    span2 = parentDiv.Children[1];
    span3 = parentDiv.Children[2];
    Assert.IsTrue(span1.IdAttributeValue.Equals("span1"), string.Format("Actual ID: {0}", span1.IdAttributeValue));
    Assert.IsTrue(span2.IdAttributeValue.Equals("span2"), string.Format("Actual ID: {0}", span2.IdAttributeValue));
    Assert.IsTrue(span3.IdAttributeValue.Equals("span3"), string.Format("Actual ID: {0}", span3.IdAttributeValue));
    {{endregion}}

#### __[VB]__

      {{region }}

    ' Let's start with the span1 element.
    Dim span1 As Element = Find.ById("span1")
    Dim span2 As Element = span1.GetNextSibling()
    Dim span3 As Element = span2.GetNextSibling()

    ' Let's verify we got the right elements
    Assert.IsTrue(span1.IdAttributeValue.Equals("span1"), String.Format("Actual ID: {0}", span1.IdAttributeValue))
    Assert.IsTrue(span2.IdAttributeValue.Equals("span2"), String.Format("Actual ID: {0}", span2.IdAttributeValue))
    Assert.IsTrue(span3.IdAttributeValue.Equals("span3"), String.Format("Actual ID: {0}", span3.IdAttributeValue))

    ' Now let's navigate backwards
    span2 = span3.GetPreviousSibling()
    span1 = span2.GetPreviousSibling()
    Assert.IsTrue(span1.IdAttributeValue.Equals("span1"), String.Format("Actual ID: {0}", span1.IdAttributeValue))
    Assert.IsTrue(span2.IdAttributeValue.Equals("span2"), String.Format("Actual ID: {0}", span2.IdAttributeValue))
    Assert.IsTrue(span3.IdAttributeValue.Equals("span3"), String.Format("Actual ID: {0}", span3.IdAttributeValue))

    ' Now let's look at parent and children
    Dim parentDiv As Element = span1.Parent
    ' ChildNodes includes all nodes including text and comments. Children is a subset of ChildNodes.
    Assert.AreEqual(parentDiv.ChildNodes.Count, 4, String.Format("ChildNodes = {0}", parentDiv.ChildNodes))
    ' Children are basically only markup children. (Does not include text or comments);
    Assert.AreEqual(parentDiv.Children.Count, 3, String.Format("Children = {0}", parentDiv.ChildNodes))

    span1 = parentDiv.Children(0)
    span2 = parentDiv.Children(1)
    span3 = parentDiv.Children(2)
    Assert.IsTrue(span1.IdAttributeValue.Equals("span1"), String.Format("Actual ID: {0}", span1.IdAttributeValue))
    Assert.IsTrue(span2.IdAttributeValue.Equals("span2"), String.Format("Actual ID: {0}", span2.IdAttributeValue))
    Assert.IsTrue(span3.IdAttributeValue.Equals("span3"), String.Format("Actual ID: {0}", span3.IdAttributeValue))
    {{endregion}}
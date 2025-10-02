---
title: Find Expressions
page_title: Find Expressions
description: "Test Studio Testing Framework Find Expressions in coded tests. Use Find Expressions in coded tests to locate elements in the tested application."
previous_url: /user-guide/write-tests-in-code/intermediate-topics/element-identification/find-expressions.aspx, /user-guide/write-tests-in-code/intermediate-topics/element-identification/find-expressions
position: 1
---

#HTML and XAML Find Expressions#

FindExpression's are the replacement/evolution of FindParam's. We will be using FindExpression's as the base for all element searches in the DOM, HWnd, or control trees (including Translator Locators). The key design goal for FindExpressions is to enable a flexible, rich and extensible search definition pattern that can be used across all of our Telerik technologies. This will enable our customers to carry over their product experience as they move across our product stacks making the learning curve for customers moving from one technology to another minimal.ma
 
Some of the key problems we faced with FindParam's that are solved by using 

FindExpression's are the following:

1.&nbsp; FindParam's are very closely coupled with HTML. The object model for FindParam's was built with HTML in mind.

2.&nbsp; Chained identifications [e.g. find element 'foo' then 'bar' starting at 'foo'] cannot currently be represented as one FindParam object.

3.&nbsp; The ability to extend the capability of the current search routines based on FindParam's is expensive. The search logic is disconnected from the search definition.

4.&nbsp; The FindParam object model is very verbose which results in:

	* Constant OM changes when extending search patterns.

	* OM changes will always require serialization changes and any serialization change requires extra consideration for backward compatibility.

	* Constructing a FindParam is a bit tricky. We have 7 constructors and even these 7 don't satisfy all scenarios. We want our search code to be as concise as possible.

	* Complex OMs make Code Gen more complex.

5.&nbsp; No extensible infrastructure where customers can build their own search engines if they wish.

6.&nbsp; Can't easily be leveraged for searches within other technologies.

##Basic Concept##

The key to understanding FindExpression's is to understand its basic component: the FindClause. A FindClause is a name/value pair with an optional comparison operator. A FindExpression consists of 1-n FindClauses. For example:

###FindClauses Without Operators###

```
TagName=div
id=bar
innermarkup=hellothere
```

###FindClauses With Operators###

```
name=~bar [name attribute partially contains bar]
automationid=^hat [the automation id of an element starts with hat]
```


**Note:** The optional operator is ALWAYS the first character after the = in the expression. This special character can be escaped with a preceding ' character if it is meant to be interpreted as a literal character.


###Supported Operators###

<table class="docs">
<tr>
	<th>Leading character</th><th>Example</th><th>Description</th>
</tr>
<tr>
	<td>~</td>
	<td>foo=~bar</td>
	<td>Find the element where attribute foo 'contains' bar</td>
</tr>
<tr>
	<td>!</td>
	<td>foo=!bar</td>
	<td>Find the element where attribute foo 'does not contain' bar</td>
</tr>
<tr>
	<td>^</td>
	<td>foo=^bar</td>
	<td>Find the element where attribute foo 'starts with' bar</td>
</tr>
<tr>
	<td>?</td>
	<td>foo=?bar</td>
	<td>Find the element where attribute foo 'ends with' bar</td>
</tr>
<tr>
	<td>#</td>
	<td>foo=#ba*</td>
	<td>Find the element where attribute foo 'matches the regular expression' ba* - See this link for a description of regular expressions.</td>
</tr>
<tr>
	<td>|</td>
	<td>'id=CenterDiv', '|', 'tagIndex=a:2' </td>
	<td>Chains two expressions together. Chained expressions work by finding the element that matches the first expression, then underneath that find the element that matches the next expression. There is no technical limit to how many expressions can be chained together. The example tells <a href="http://www.telerik.com/teststudio" target="_blank">Test Studio</a> to find the first element whose ID = CenterDiv and then under that element find the third anchor element (tagIndex is 0 based).</td>
</tr>
<tr>
	<td>'</td>
	<td>textContent=''City</td>
	<td>Escape special characters. Find the element whose text = 'City', including the ' characters. </td>
</tr>
<tr>
	<td>+</td>
	<td>foo=+</td>
	<td>Find the element that has the specified attribute. Find the element that has the attribute 'foo'.</td>
</tr>
<tr>
	<td>-</td>
	<td>foo=-</td>
	<td>Find the element that does not have the specified attribute. Find the element that does not have the attribute 'foo'.</td>
</tr>
</table>

The name portion of the clause can be a well known enumeration that a certain technology (i.e. HTML, XAML) recognizes as a certain search pattern. For example, in HTML:

```
xpath=HTML[0]/div[1]
```

is interpreted by the HTML search tree as a specific search that requires XPATH interpretation.

```
automationid=?sam
```

##Constructing FindExpressions##

Each technology (HTML, WPF, or Desktop) will define its own FindExpression that inherits from the base FindExpression object. All FindExpression's need only one constructor to define any type of search.
 
For example:
 
Find the HTML element with an id that ends with 'sam' and also has a class attribute that contains bar and also has a text content that does not contain foo.

```C#
HtmlFindExpression expr = new HtmlFindExpression("id=bar","|","tagindex=td:0","|","tagname=img","src=~png");
```

##Hierarchy Constraint##

You can also describe a certain hierarchal constraint to be applied against that FindExpression so that the decision on whether a specific element matches a specific translator or not is not solely based on the tag but also takes into consideration its hierarchical position. For example a tag that looks like ```HTML <div class='foo' />```might be part of a grid while at the same time other elements on the page could contain that tag. The only way to distinguish whether that tag is part of the grid is to inspect its parent or child hierarchy.
 
FindExpression's natively support hierarchy constraints. A FindExpression can have 0-n HierarchyConstraint objects associated with it.
 
A hierarchy constraint contains two pieces of data:

1. A Hierarchy path => The path from the target element. This is expressed as a list of integers. for example -1,1 means: The first child of the parent. [negative=up/parent index, positive=down/child index]

2. A FindExpression => This is the expression to match at the target of the path reference.
 
For example, suppose we have the following HTML code snippet to deal with:

```HTML
<div class="bar">
  <div id="foo1">
     <section id="foo2">
         <div class="bar">
```

Now we want to match the div tag that has class='bar' and its parent's parent has an id='foo1':

```C#
// This expression will locate both p tags at [0] & [3]
HtmlFindExpression expression = new HtmlFindExpression("class=bar", "tagname=div");
  
// Create a hierarchy constraint
HtmlFindExpression parentExpr = new HtmlFindExpression("id=foo1"); // matches [1]
  
// Add the constraint to the original expression.
// -2 signifies two parents up.
// Note that HierarchyConstraints are [1] based. Zero signifies the target element or reference point.
expression.AddHierarchyConstraint(new HierarchyConstraint(parentExpr, -2));
```
```VB
' This expression will locate both p tags at [0] & [3]
Dim expression As New HtmlFindExpression("class=bar", "tagname=div")
  
' Create a hierarchy constraint
Dim parentExpr As New HtmlFindExpression("id=foo1")
' matches [1]
' Add the constraint to the original expression.
' -2 signifies two parents up.
' Note that HierarchyConstraints are [1] based. Zero signifies the target element or reference point.
expression.AddHierarchyConstraint(New HierarchyConstraint(parentExpr, -2))
```


The resulting expression now will match [3] ONLY.
 
Here is a more involved scenario:

```HTML
<div class="bar">
  <p id="foo1">
    <span id="foo2" />
        <a href="/cat.html" id="cat"/>
            <img src="cat.jpg" alt="cat picture" />
            text 
        </a>
        , and more text
    </span>
  </p>
</div>
```

If we wish the constraint to match the first child of the parent's parent (i.e. [2]) and to be an 'span' instead, that is also doable.
 
The path in that case is -2, 1 => Two parents up, one down at index 1. (Or -1, -1, 1, both are the same) and the second FindExpression will be "TagName=span" instead of "id=foo1".

##HtmlFindExpression Types##

The following is a list of the types that can appear on the left side of the expression in HtmlFindExpressions:

* Any valid attribute name (id, name, etc.)

* TextContent - search for an element in which has text that matches the specified expression.

* InnerText - search for an element in which the InnerText matches the specified expression.

* InnerMarkup - search for an element in which the InnerMarkup matches the specified expression.

* OuterMarkup - search for an element in which the OuterMarkup matches the specified expression.

* StartTagContent - search for an element in which the StartTagContent matches the specified expression.

* NodeIndexPath - search for an element having the specified NodeIndexPath.

* TagName - search for an element in which the TagName matches the specified expression.

* TagIndex - search for an element at the specified zero based TagIndex.

* XPath - search for an element at the specified XPath expression.

##XamlFindExpression Types##

The following is a list of the types that can appear on the left side of the expression in XamlFindExpressions:

* AutomationId - search for an element having an automation ID of a specific value.

* TextContent - search for an containing or not containing some text in the element.

* XamlTag - search for an element of a specific type.

* XamlTagBase - search for an element that extends a specific type

* Name - search for an element having a name of a specific value.

* TagIndex - the zero based index value of a specific tag.

* XamlPath - Uses a XAML path expression like XamlPath=/radtabcontrol[automationid=Tabs]/grid[0]/raddockpanel[0]/layouttransformcontrol[name=HeaderDockedElement]


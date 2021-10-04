---
title: Finding Page Elements
page_title: Finding Page Elements | Test Studio Dev Documentation
description: "Test Studio Find methods. Progress Testing Framework Find.By methods. Locate an element in code. Find an element in code. "
position: 1
---

<style>
table.docs {
font-family: verdana,arial,sans-serif;
font-size:11px;
color:#333333;
border: 1px solid #dbdbdb;
border-collapse: collapse;
table-layout: fixed;
width: 900px;

}
table.docs th {
color:#fff;
background-color:#ed8200;
border: 1px solid #dbdbdb;
padding: 8px;
}
table.docs tr {
background-color:#ffffff;
}
table.docs td {
border: 1px solid #dbdbdb;
padding: 8px;
}
</style>

# Finding Page Elements #

Telerik Testing Framework provides one of the richest markup identification infrastructures currently available on the market. It builds on top of commonly known element identification methods like 'getElementById', 'getElementByName' or 'XPath' and extends them to provide identification routines that cater more to application automation scenarios. In addition to maintaining a simple and easy to use set of APIs, Telerik Testing Framework introduces a consistent and extensible way to build identification and persist it using 'FindParam' objects.

All the Find.Byxxx methods now support LINQ queries.

It is important to understand how Telerik's identification method works because that understanding will allow you to exploit the power of these identification methods to build robust automation quicker.

##Element Identification Overview##

The following identification methods are supported:

<table class="docs">
<tr>
	<th style="width:165px;">Methods</th><th style="width:200px;">Description</th><th>Example</th>
</tr>
<tr>
	<td><a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#collapsible-ArtOfTest_WebAii_Core_Find_ById_System_String_" target="_blank">**Find.ById()**</a></td>
	<td>Searches for an element contained in a markup document using its set 'id' attribute. When the desired 'id' matches an element's id, the element is returned - identical to getElementById</td>
<td>
```	
// Find element with id=input1
Element e = Find.ById("input1");
```
</td>
</tr>
<tr>
	<td><a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#collapsible-ArtOfTest_WebAii_Core_Find_ByName_System_String_" target="_blank">**Find.ByName()**</a></td>
	<td>Searches for an element contained in a markup document using its set 'name' attribute. When the desired 'name' matches an element's name, the element is returned</td>
<td>
```	
// Find element with name=goButton
Element e = Find.ByName("goButton")
```
</td>
</tr>
<tr>
	<td><a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#collapsible-ArtOfTest_WebAii_Core_Find_ByImage_System_Drawing_Image_System_Double_System_Int32_System_Boolean_System_Drawing_Point_System_Int32_" target="_blank">**Find.ByImage()**</a><br>
    <a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#ArtOfTest_WebAii_Core_Find_AllByImage_System_Drawing_Image_System_Double_System_Boolean_System_Drawing_Point_System_Int32_" target="_blank">**Find.AllByImage()**</a></td>
	<td>Searches for an element or 'All' elements that look like a predefined image</td>
<td>
```
// Specify the predefined image on which the search will be based
System.Drawing.Image img1 = System.Drawing.Image.FromFile(@"C:\sampleImg.png");
// Find an element that looks like the predefind image
var elementImg1 = Manager.ActiveBrowser.Find.ByImage(img1, 70); // the second argument is the threshold % to use, while searching for the image
// Cast the found element to be able to use it. The type of located element needs to be specified.
HtmlButton btn1 = elementImg1.As<HtmlButton>();
```
</td>
</tr>
<tr>
	<td><a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#collapsible-ArtOfTest_WebAii_Core_Find_ByTagIndex_System_String_System_Int32_" target="_blank">**Find.ByTagIndex()**</a></td>
	<td>Searches for an element using its tag name occurrence index. Finds the element at the specified occurrence index and returns it. This method uses zero based indexing.</td>
<td>
```	
// Find the 3rd occurrence of table tag
Element table = Find.ByTagIndex("table", 2);
```
</td>
</tr>
<tr>
	<td><a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#ArtOfTest_WebAii_Core_Find_ByAttributes_System_String___" target="_blank">**Find.ByAttributes()**</a><br>
	<a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#ArtOfTest_WebAii_Core_Find_AllByAttributes_System_String___" target="_blank">**Find.AllByAttributes()**</a></td>
	<td>Searches for an element or 'All' elements using an 'exact' or 'partial' list of attribute values (You can specify 1-N attribute/value pairs). When all attribute values match, the element or collection of elements is returned.</td>
<td>
```	
// Find the first element with attribute class=myclass
Element e = Find.ByAttributes("class=myclass");
// Find the first element with attribute class=myclass
// and 'src' has partial value foo.gif. (~ signifies partial)
Element e = Find.ByAttributes("class=myclass", "src=~foo.gif");
// Find all elements with class=myclass and src has a partial foo.gif
IList<Element> allbtns = Find.AllByAttributes("class=myclass", "src=~foo.gif");
```
</td>
</tr>
<tr>
	<td><a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#ArtOfTest_WebAii_Core_Find_ByContent_System_String_" target="_blank">**Find.ByContent()**</a><br>
	<a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#ArtOfTest_WebAii_Core_Find_AllByContent_System_String_" target="_blank">**Find.AllByContent()**</a></td>
	<td>Searches for an element or 'All' elements using 'exact', 'partial' or 'regex' of the element content. The element content can be: InnerText, InnerMarkup, OuterMarkup, TextContent (default), StartTagContent.</td>
<td>
```	
// Find element with TextContent has literal value: Education
// l: signifies literal
Element e = Find.ByContent("l:Education");
// Find element with TextContent has patrial value: Education
// p: signifies partial
Element e = Find.ByContent("p:Education");
// Find element with TextContent matches regex expression:
// ^(<tr>\s*<td\s*scope=.*>\s*Education)
// x: signifies regular expression
Element e = Find.ByContent(@"x:^(<tr>\s*<td\s*scope=.*>\s*Education)");
// Explicitly set the content type.
Element e = Find.ByContent("p:<div id='cat'>", FindContentType.StartTagContent);
// Find all elements with TextContent having partial value: car
IList<Element> alle = Find.AllByContent("p:car")
// NOTE:
//
// There is a difference between FindContentType.InnerText & FindContentType.TextContent that is worth noting:
//
// Example: <div id="div1">Text1<div id="div2">Text2</div></div>
//
// InnerText for div1 : Text1Text2 {recursive}
// TextContent of div1 : Text1 {non-recursive}
//
// Default for ByContent is TextContent which is the most common usage.
```
</td>
</tr>
<tr>
	<td><a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#collapsible-ArtOfTest_WebAii_Core_Find_ByExpression_ArtOfTest_WebAii_Core_HtmlFindExpression_" target="_blank">**Find.ByExpression()**</a><br>
	<a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#ArtOfTest_WebAii_Core_Find_AllByExpression_ArtOfTest_WebAii_Core_HtmlFindExpression_" target="_blank">**Find.AllByExpression()**</a></td>
	<td>Searches for an element or 'All' elements matching an HtmlFindExpression. The HtmlFindExpression cannot use any type of hierarchical expressions including tag index path expressions, HTML path expressions, and XPath expressions.</td>
<td>
```	
// Create an HtmlFindExpression element
HtmlFindExpression expr = new HtmlFindExpression("id=?sam","class=~bar","textcontent=!foo");
// Return all elements matching HtmlFindExpression
IList<Element> allSams = Find.AllByExpression(expr);
```
</td>
</tr>
<tr>
	<td><a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#collapsible-ArtOfTest_WebAii_Core_Find_ByXPath_System_String_" target="_blank">**Find.ByXPath()**</a><br>
	<a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#ArtOfTest_WebAii_Core_Find_AllByXPath_System_String_" target="_blank">**Find.AllByXPath()**</a></td>
	<td>Searches for an element or 'All' elements using an XPath expression. WebAii supports the .NET Framework XPath implementation.</td>
<td>
```	
// Find the banner img element
Element img = Find.ByXPath("//body[1]/table[1]/tbody[1]/tr[1]/td[1]/img[1]");
// Find all times with id=div
IList<Element> allDivs = Find.AllByXPath("/descendant::node()[starts-with(@id,'div')]");
```
</td>
</tr>
<tr>
	<td><a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#ArtOfTest_WebAii_Core_Find_ByCssSelector_System_String_" target="_blank">**Find.ByCssSelector()**</a><br>
	<a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#ArtOfTest_WebAii_Core_Find_AllByCssSelector_System_String_" target="_blank">**Find.AllByCssSelector()**</a></td>
	<td>Searches for an element or 'All' elements using a css selector query.</td>
<td>
```	
// Find the active link
HtmlAnchor activeLink = Find.ByCssSelector<HtmlAnchor>("a:active");
// Find all links
IList<HtmlAnchor> allLinks = Find.AllByCssSelector<HtmlAnchor>("a"); 
```
</td>
</tr>
<tr>
	<td><a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#ArtOfTest_WebAii_Core_Find_AllByTagName_System_String_" target="_blank">**Find.AllByTagName()**</a></td>
	<td>Searches for 'All' elements with the specified tag name and returns it as a list of elements.</td>
<td>
```	
// Return all img elements
IList<Element> allimg = Find.AllByTagName("img");
```
</td>
</tr>
<tr>
	<td><a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#collapsible-ArtOfTest_WebAii_Core_Find_ByNodeIndexPath_System_String_" target="_blank">**Find.ByNodeIndexPath()**</a></td>
	<td>Searches for an element using dom tree node index paths. This identification is done using an xpath like approach that simply describes the hierarchy path to a specific element using the node index within the hierarchy without having to specify the tag name at each level. This identification method can be chosen in cases where a segment of the DomTree hierarchy at a specific location is consistent but element type changes. For example, if an element you are trying to target is the direct child of another element that fluctuates between a span and div, you can choose this identification method to provide a consistent way to identify that element.</td>
<td>

```	
Given this DOM:

 <referenceElement>
  (0)<foo>
        <bar>
        </bar>
        <car>
        </car>
      (2)<bus>
          (0)<driver>
                <cap>
                </cap>
              (1)<target>
                </target>
            </driver>
        </bus>
    </foo>
 </referenceElement>

// We can find the <target></target> element by:
Element target = Find.ByNodeIndexPath("0/2/0/1");
```
</td>
</tr>
<tr>
	<td><a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#collapsible-ArtOfTest_WebAii_Core_Find_FromCollection_ArtOfTest_WebAii_ObjectModel_FindExpressionCollection_ArtOfTest_WebAii_Core_HtmlFindExpression__" target="_blank">**Find.FromCollection()**</a></td>
	<td>Finds all elements with the FindParams in the passed in collection.</td>
<td>
```	
FindParamCollection col = FindParamCollection.LoadFromXml(xml);
return this.FromCollection(col);
```
</td>
</tr>
<tr>
	<td><a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#collapsible-ArtOfTest_WebAii_Core_Find_ByCustom_System_Predicate_ArtOfTest_WebAii_ObjectModel_Element__" target="_blank">**Find.ByCustom()**</a><br>
	<a href="https://docs.telerik.com/teststudio/api/artoftest.webaii.core.find.html#ArtOfTest_WebAii_Core_Find_AllByCustom_System_Predicate_ArtOfTest_WebAii_ObjectModel_Element__" target="_blank">**Find.AllByCustom()**</a></td>
	<td>Searches for an element or 'All' elements using a custom predicate.</td>
<td>
```	
// Find the first input button having an ID of 'input1'
HtmlInputButton btn = Find.ByCustom<HtmlInputButton>(
    delegate(HtmlInputButton e)
    {
        if (e.BaseElement.IdAttributeValue == "input1")
            return true;
        else
            return false;
    }
);
Assert.IsNotNull(btn);
```
</td>
</tr>
<table>

##Identification Methods Usage##

Telerik Testing Framework identification methods are accessible using the **Find** object that is exposed as a property off of the 'Browser' object : *Manager.ActiveBrowser.Find.Byxx(...)* and also as a property off of each TestRegion object : *TestRegion.Find.Byxx(...)*.

The difference between the Find object off of the Browser class (Root Base Identification - Identification Sample) and the Find object off of the TestRegion class (ReGion Base Identification - **RGBI**), is that the one off of the Browser performs all searches starting from the root document element whereas the Find object off of the TestRegion's searches only the elements contained in that specific test region and uses the TestRegion's open tag (i.e. <!--testregion...->) as the root element for reference based identification like tag name occurrence index and XPath identification.

With TestRegions, depending on the areas of the application that each automated test is targeting, you can use different Find objects to give each test a greater level of independence and shield it from product changes outside its target area. This topic is discussed in greater details in <a href="/code-in-test/advanced-topics-wtc/test-regions-wtc/Introduction" target="_blank">Introduction to TestRegions</a>.

##Matching Syntax Used in Parameters##

The Byxxx functions that take a nameValuePairs parameter recognizes the following matching syntax:

* class=myclass - Matches when the 'class' attribute is equal to 'myclass'

* class=~myclass - Matches when the 'class' attribute contains the string 'myclass'. This is called the 'partial match' syntax.

* class=!myclass - Matches when the 'class' attribute does not contain the string 'myclass'.
 
You can mix the above syntax into a single Byxxx function. (e.g. Find.ByAttributes("class=~my", "class=~class", "class=!other") will match the string "class=myclass" but will not match "class=myotherclass".)
 
The Byxxx functions that take a content string parameter recognizes the following matching syntax:

* Prefix the string parameter with 'l:' for exact match strings. e.g. 'l:Vacation homes' will match 'Vacation homes' exactly. This is also the default used if no prefix is used.

* Prefix the string parameter with 'p:' for partial strings matching. e.g. 'p:Arizona' will match any content containing the string 'Arizona'.

* Prefix the string parameter with 'x:' for regular expression matching. e.g. 'x:[*foo*]' will match any content containing the string 'foo' in the middle of it. For more information about  regular expressions see: http://msdn.microsoft.com/en-us/library/2k3te2cs.aspx.

##Identification Sample##

To help illustrate the above identification methods, let's use the following sample application. Note that this application uses TestRegions excessively to allow it to demonstrate the different identification methods that can be performed using both **RBI** and **RGBI**:

```HTML
<!DOCTYPE html>
<html>
<head>
<title></title>
</head>
<body>
<!--testregion id="Region1"-->
    <div>
        <input type="text" id="input0"/>
            <!--testregion id="Region11"-->
                <div id="div0" style="background-color:Red">Data Display</div>
                <input id="input1" type="button" value="Click Me" onclick="clicked();"/>
                   <!--testregion id="Region111"-->
                       <a id="a0" href="http://www.google.com">Go Google</a>
                           <!--testregion id="Region1111"-->
                               <a id="a1" href="http://www.kayak.com">Go Kayak</a>
                           <!--/testregion-->
                   <!--/testregion-->
                   <!--testregion id="Region112"-->
                       <div id="div1">Some Data</div>
                   <!--/testregion-->
                <div id="div2">Some Data
                   <a id="a2" href="http://www.kayak.com">Go Kayak</a>
                   <a id="a3" href="http://www.kayak.com">Go Kayak</a>
                   <a name="a4" href="http://www.kayak.com">Go Kayak</a>
                   <a name="a5" href="http://www.kayak.com">Go Kayak</a>
                </div>
                <div id="div3">Some Data</div>
                <div id="div4">Some Data
                   <input attr1="Button1" type="button" value="Click Me" onclick="clicked();"/>
                   <div id="div5">Some Data</div>
                </div>
                <div id="div6">Some Data
                       <input id="Button2" type="button" value="Click Me" onclick="clicked();"/>
                       <input id="Button3" type="button" value="Click Me" onclick="clicked();"/>
                </div>
                <div id="div7" bla="foo:$$__fdd">Some Data</div>
                <div id="div8">Some Data</div>
            <!--/testregion-->
    </div>
<!--/testregion-->
</body>
</html>
```

The code below shows the different methods you can use in your test code to identify elements. Note in the sample below, we are using Visual Studio's Assert class to demonstrate how different objects can be identified differently and to illustrate how to scope the identification with TestRegions using RGBI and across the entire document DomTree using RBI.

```C#
// Set the short-cuts to the main automation objects.
Browser brwser = mgr.ActiveBrowser;
Find rootFind = brwser.Find;
  
// All the testregion are initialized here.
TestRegion r1 = brwser.Regions["Region1"];
TestRegion r11 = brwser.Regions["Region11"];
TestRegion r111 = brwser.Regions["Region111"];
TestRegion r1111 = brwser.Regions["Region1111"];
TestRegion r112 = brwser.Regions["Region112"];
  
//*** Using identification by id.
Element div0 = r1.Find.ById("div0");
  
//*** Using tag name occurrence index.
Element div = r1.Find.ByTagIndex("div", 0);
Element div1 = r112.Find.ByTagIndex("div", 0);
  
// Some verification to illustrate how the same element that was found
// using TestRegion Find objects above, can be also found
// using the main Browser Find object.
Assert.IsTrue(div.Equals(rootFind.ByTagIndex("div", 0)));
Assert.IsTrue(div0.Equals(rootFind.ByTagIndex("div", 1)));
  
//*** Using attribute identification.
Assert.IsTrue(div1.Equals(rootFind.ByAttributes("id=div1")));
Assert.IsTrue(rootFind.ByAttributes("id=bla") == null);
Assert.IsNotNull(rootFind.ByAttributes("href=http://www.kayak.com"));
  
//*** Using partial attribute identification.
Assert.IsTrue(rootFind.ByAttributes("bla=~__").Equals(rootFind.ById("div7")));
Assert.IsNull(rootFind.ByAttributes("id=~div7", "bla=~wow"));
Assert.IsNotNull(rootFind.ByAttributes("onclick=~clicked();", "id=~button2"));
  
//*** Using 'All' elements identification.
  
// note here that the first 'div' does not have any id that contains 'div' hence the '- 1'
Assert.IsTrue(rootFind.AllByTagName("div").Count - 1
    == rootFind.AllByXPath("/descendant::node()[starts-with(@id,'div')]").Count);
  
Assert.IsTrue(rootFind.AllByAttributes("href=http://www.kayak.com").Count == 5);
Assert.IsTrue(rootFind.AllByAttributes("id=~button").Count == 2);
Assert.IsTrue(r1.Find.AllByTagName("div").Count == 10);
Assert.IsTrue(r1111.Find.AllByTagName("div").Count == 0);
Assert.IsTrue(r111.Find.AllByTagName("a").Count == 2);
Assert.IsTrue(r11.Find.AllByAttributes("id=~div").Count == 9);
  
//*** Using NodeIndexPath identification.
Assert.IsTrue(r1.Find.ByNodeIndexPath("0/1/1").IdAttributeValue.Equals("input1"));
Assert.IsTrue(rootFind.ByNodeIndexPath("1/0/0").TagName.Equals("div", StringComparison.OrdinalIgnoreCase));
  
//*** Using name
Assert.IsNull(r1.Find.ByName("bla"));
```
```VB
' Set the short-cuts to the main automation objects.
Dim brwser As ArtOfTest.WebAii.Core.Browser = Manager.ActiveBrowser
Dim rootFind As Find = brwser.Find
  
' All the testregion are initialized here.
Dim r1 As TestRegion = brwser.Regions("Region1")
Dim r11 As TestRegion = brwser.Regions("Region11")
Dim r111 As TestRegion = brwser.Regions("Region111")
Dim r1111 As TestRegion = brwser.Regions("Region1111")
Dim r112 As TestRegion = brwser.Regions("Region112")
  
'*** Using identification by id.
Dim div0 As Element = r1.Find.ById("div0")
  
'*** Using tag name occurrence index.
Dim div As Element = r1.Find.ByTagIndex("div", 0)
Dim div1 As Element = r112.Find.ByTagIndex("div", 0)
  
' Some verification to illustrate how the same element that was found
' Imports TestRegion Find objects above, can be also found
' Imports the main Browser Find object.
Assert.IsTrue(div.Equals(rootFind.ByTagIndex("div", 0)))
Assert.IsTrue(div0.Equals(rootFind.ByTagIndex("div", 1)))
  
'*** Using attribute identification.
Assert.IsTrue(div1.Equals(rootFind.ByAttributes("id=div1")))
Assert.IsNull(rootFind.ByAttributes("id=bla"))
Assert.IsNotNull(rootFind.ByAttributes("href=http://www.kayak.com"))
  
'*** Using partial attribute identification.
Assert.IsTrue(rootFind.ByAttributes("bla=~__").Equals(rootFind.ById("div7")))
Assert.IsNull(rootFind.ByAttributes("id=~div7", "bla=~wow"))
Assert.IsNotNull(rootFind.ByAttributes("onclick=~clicked();", "id=~button2"))
  
'*** Using 'All' elements identification.
  
' Note here that the first 'div' does not have any id that contains 'div' hence the '- 1'.
Assert.AreEqual(rootFind.AllByTagName("div").Count - 1, _
    rootFind.AllByXPath("/descendant::node()[starts-with(@id,'div')]").Count)
  
Assert.AreEqual(5, rootFind.AllByAttributes("href=http://www.kayak.com").Count)
Assert.AreEqual(2, rootFind.AllByAttributes("id=~button").Count)
Assert.AreEqual(10, r1.Find.AllByTagName("div").Count)
Assert.AreEqual(0, r1111.Find.AllByTagName("div").Count)
Assert.AreEqual(2, r111.Find.AllByTagName("a").Count)
Assert.AreEqual(9, r11.Find.AllByAttributes("id=~div").Count)
  
'*** Using NodeIndexPath identification.
Assert.IsTrue(r1.Find.ByNodeIndexPath("0/1/1").IdAttributeValue.Equals("input1"))
Assert.IsTrue(rootFind.ByNodeIndexPath("1/0/0").TagName.Equals("div", StringComparison.OrdinalIgnoreCase))
  
'*** Using name
Assert.IsNull(r1.Find.ByName("bla"))
```
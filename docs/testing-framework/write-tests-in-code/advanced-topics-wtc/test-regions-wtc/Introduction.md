---
title: Introduction
page_title: Introduction to TestRegions
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
#Introduction to TestRegions#

Building testability and agility into your markup applications.

##What Are TestRegions? (*)##

TestRegions are simple innovations that bring a new perspective to automated software testing by breaking the traditional silos between application authoring and testing. They pave the way to a better and more robust test automation while enhancing the agility of the overall development lifecycle. TestRegions are hopefully a first step that others can use and build upon to usher a new generation of tools and methodologies that bring new advancements in the art of software testing and quality assurance.
 
In a nutshell, TestRegions are markup tags that can be used as part of a "markup application under test" to define and segment the application into logical structured and hierarchal list of test regions that are being targeted for automated testing. A markup application can be any application written using markup languages like XML, HTML, XHTML ...etc.
 
TestRegions are usually ignored by the host (or processor) of the markup application, but are recognized by automation systems that implement them like Telerik Testing Framework's Automation Infrastructure.
 
Some of the key benefits of TestRegions are:

* Reduce the cost and complexity of the test automation authoring process by providing automated tests a generic approach to identify targeted test regions within an application under test while adding structure and consistency in how these tests navigate and access these targeted regions.

* TestRegions can be used as reference points for element identification which has the effect of shielding automated tests that use them from product changes that fall outside the scope of these tests. This in turn reduces the maintenance costs for tests when the product undergoes design changes and functionality updates. In other words, they reduce unwanted noise and test failures caused by product updates.

* TestRegions can also be used to build complete strongly-typed abstract automation layers of a tested application to provide loose coupling of test code from the product being tested. These layers can also be used to encapsulate certain product functionality to be automated.

* TestRegions can also be leveraged to provide an early warning system to notify teams of product changes that will potentially break their test automation without the need to run tests and do analysis. That in turn can save development teams time and shorten the feedback loop between development and quality assurance teams.
 
To help demonstrate these benefits, we will be using the following simple markup page as our sample application through out this tutorial.

```HTML
<html>
<head>
   <title>Basic TestRegion's Usage</title>
</head>
<body>
   <input type="hidden" value"someinfo />
   <table><tr><td>MyCompany, Inc. HomePage.</td></tr></table>
   <div>
     <input type="text" id="yourname" />
     <input type="text" id="zipcode" />
     <!-- Italian restaurants in your zipcode -->
     <table>
       <tr>
         <td>Name</td>
         <td>Address</td>
         <td>Tel.#</td>
       </tr>
       <tr>
         <td>Rest1</td>
         <td>Add1</td>
         <td>Tel1</td>
       </tr>
       <tr>
         <td>Rest2</td>
         <td>Add2</td>
         <td>Tel2</td>
       </tr>
       <tr>
         <td>Rest3</td>
         <td>Add3</td>
         <td>Tel3</td>
       </tr>
     </table>
   </div>
</body>
</html>
```

##Current Automation Practices##

Before digging into TestRegions, let's first take a look at some of the current common automation approaches for markup applications and understand their characteristics, challenges and drawbacks.
 
The common approach when attempting to automate a markup application (like the sample above) without using TestRegions is to directly target each element on the page using its id or name (if defined). When ids/names are not defined automators usually revert to other methods like searching for a target element using its tag name occurrence or XPath within the document from the root of the document.
 
**Note:** There are few things to note about these approaches:

* Using ids/names can sometimes become cumbersome given the number of elements being targeted by test automation and the unstructured approach of picking ids/names from a flat list of available ids/names on the entire page. When using a large application, that typically leads to less legible and harder to maintain test code; especially when test ownership shifts or the automation is being off shored overseas. That usually results in higher costs of ownership for the overall product cycle.

* Using ids/names are not always possible or easily done. This can be due to many reasons, some of which are:
	* When using a dynamic web development framework that doesn't provide control over all ids/names of the generated markup. A classical example is the ASP.NET Calendar control that generates nested HTML tables but users can only control the id of the outer most table.

	* When using a third party control or markup content that you have no control over. You are basically stuck using tag name indexes and XPath identifications across the entire page. For example, if your application does web scraping or uses data returned from a webservice as a markup.

	* When using dynamic or auto-generated unique ids/names that you can't control. Some complex applications are designed to perform such naming schemes but also dynamic web development frameworks do performs such naming schemes. (Like ASP.NET when using naming containers). Given that you don't control these naming schemes, any changes to them (due to upgrades or service packs) can drastically impact your test automation and render it broken in many cases, forcing you to spend hours/days fixing your test code.

* The lack of ids/names on elements as mentioned above will typically lead to element identification using tag name occurrence or XPath identification. When this type of identification is used in test automation, it is usually one of the key factors for producing fragile test automation that increases costs for test run analysis, cause invalid test failures and eventually lead to higher costs for maintenance. The reason for these drawbacks is that these approaches have an intrinsic dependency on the full structure of the entire application or the page being tested. Tests that use these approaches tend to break frequently when parts of the application that are unrelated to the part being targeted by these tests change. Which usually forces developers to have to go back and update these tests every time such changes occur.
 
To clarify this point more, let's take a simple example:

* In the sample page above, let's assume we have an automated test that verifies the content of the Italian restaurants table. The test uses tag name occurrence to identify the second table that lists the restaurants in a certain zip code. In the sample above, the test code will ask for 'table', occurrence='2' and that should be correct. Now if later on, the page content gets updated to include another table right before our Italian restaurants table, our automation will break. To be more specific, if the above page changes to include another table right below the table that contains the company name (for example to list the company address too), our test will break since 'table' occurrence '2' is no longer the Italian restaurants table. Although the change in the page occurred in portion of the application that the current test does not care about and does not care to verify, the test still broke. The same scenario applies when using XPath identification. That is usually one of the main causes of test case fragility and high costs of test case maintenance in markup applications.
 
With that being said, it is important to note that TestRegions DO NOT completely eradicate the need for ids/names but instead they augment the current use of ids/names and common automation practices to help address some of the issues mentioned above and add more structure and consistency to test automation.

##Using TestRegions##

Let's start by using TestRegions in the above sample to provide a structured approach to accessing this application from test automation. To do so, we need to inject TestRegions within our application markup. The TestRegions supported by Telerik Testing Framework Automation Infrastructure are:

```HTML
<testregion id="regionid">...region content...</testregion>
```

Given that these are custom tags and are currently not handled as expected in latest browsers (for example, in Firefox, custom tags - even if they are Xhtml defined with extended dtd - are always included with the closing tag right after the open tag regardless of the tag content), the comment version of these tags is supported:

```HTML
<!--testregion id="regionid"-->...region content...<!--/testregion-->
```

Using these tags as comments is a very unintrusive approach to the overall application and is completely compliant with markup standards like XHTML and XML.

Let's start by defining two logical regions within our sample application above that we want to target in our automated testing. The page below shows the sample above with the following two logical regions defined: userinput, restaurantdata.

```HTML
<html>
<head>
   <title>Basic TestRegion's Usage</title>
</head>
<body>
   <table><tr><td>MyCompany, Inc. HomePage.</td></tr></table>
   <div>
     <!--testregion id="userinput"-->
       <input type="text" id="Text1" />
       <input type="text" id="Text2" />
     <!--/testregion-->
 
     <!--testregion id="restaurantdata"-->
       <!-- Italian restaurants in your zipcode -->
       <table>
         <tr>
           <td>Name</td>
           <td>Address</td>
           <td>Tel.#</td>
         </tr>
         <tr>
           <td>Rest1</td>
           <td>Add1</td>
           <td>Tel1</td>
         </tr>
         <tr>
           <td>Rest2</td>
           <td>Add2</td>
           <td>Tel2</td>
         </tr>
         <tr>
           <td>Rest3</td>
           <td>Add3</td>
           <td>Tel3</td>
         </tr>
       </table>
     <!--/testregion-->
   </div>
</body>
</html>
```

With test regions defined, our test code can directly access these regions regardless of their nesting or positioning as follows:

```C#
TestRegion userInput = Manager.ActiveBrowser.Regions["userinput"];
TestRegion restaurantData = Manager.ActiveBrowser.Regions["restaurantdata"];
```
 

```VB
Dim userInput As TestRegion = Manager.ActiveBrowser.Regions("userinput")
Dim restaurantData As TestRegion = Manager.ActiveBrowser.Regions("restaurantdata")
```
Each TestRegion above represents the part of the application as defined by the TestRegio's that are part of the application. It is worth noting here that the TestRegions collection accessor is case-insensitive to avoid test failures due to id casing mistakes.

##Identifying Elements Using TestRegions##

Now that we know how to define test regions as part of an application under test and how to access them from our automated test code, our next step is to be able to access elements contained in these TestRegions to perform actions on or extract data from.
 
Each TestRegion object has two properties that provide access to the elements contained in it:

1. Each TestRegion has an 'Element' property which returns the actual DOM Element object of that testregion tag as it exists in the DOM tree of the loaded document. You can use that Element object to navigate the DOM tree up or down to a specific element as needed. That approach is though highly discouraged because your test will become reliant on a specific DOM structure for your application and will result in test code that can easily break.

2. The second way for accessing elements is the more robust and recommended way to use in test code. Each TestRegion has a 'Find' object associated with it. The Find object provides the same rich APIs and search routines as described in the Finding Page Elements topic. The difference is that this Find object uses the TestRegion element as the root element to start the search from. This difference is the key difference that enables test code to have higher resilience to changes outside the targeted testregion. In fact, test code that targets a specific testregion and exclusively uses the Find object exposed to locate elements, will not be impacted at all by any changes in the application outside that region. Of course, changes inside that region will impact the tests that target it which is probably a desired behavior.
 
For example, to locate the restaurants table in the above sample, you can write:

```C#
TestRegion restaurantData = Manager.ActiveBrowser.Regions["restaurantdata"];
 
// Given that the table is the first table within the 'restaurantdata' test region, it has an occurrence index of '0'
Element restaurantTable = restaurantData.Find.ByTagIndex("table", 0);
```
 

```VB
Dim restaurantData As TestRegion = Manager.ActiveBrowser.Regions("restaurantdata")
 
' Given that the table is the first table within the 'restaurantdata' test region, it has an occurrence index of '0'
Dim restaurantTable As Element = restaurantData.Find.ByTagIndex("table", 0)
```

Once you have access to the Element object, you can now use it to extract information from or execute actions on. For example:

```C#
// access the userinput test region.
TestRegion userInput = Manager.ActiveBrowser.Regions["userinput"];
 
// locate the zipcode using XPath. [The second input element starting at the root of userinput testregion
Element zipCodeTextBox = userInput.Find.ByXPath("//input[2]");
 
// Perform an action on the element.
Manager.ActiveBrowser.Actions.SetText(zipCodeTextBox, "90210");
```
 

```VB
' access the userinput test region.
Dim userInput As TestRegion = Manager.ActiveBrowser.Regions("userinput")
 
' locate the zipcode using XPath. [The second input element starting at the root of userinput testregion
Dim zipCodeTextBox As Element = userInput.Find.ByXPath("/input[2]")
 
' Perform an action on the element.
Manager.ActiveBrowser.Actions.SetText(zipCodeTextBox, "90210")
```

In the first sample above, the test will not be impacted by any changes to the application regardless of how many 'table' tags get added before or after that testregion. You can even extract that testregion and embed it in a different portion of a different application and all tests that target that region will still work as expected. Same with the second sample.

##Summary##

The samples above introduce you to basic usage of TestRegions as part of the Telerik Testing Framework Automation Infrastructure. They also demonstrate how you can utilize this approach to build robust test automation code that exhibit low maintenance cost and is highly resilient to undesired test breaks. Moreover, they demonstrate how to use a consistent and structured approach to identify application segments to target for automation while making test code more legible and faster to learn and understand. TestRegions can enhance the agility of development teams and fits nicely within an agile development environment.

**TestRegion's methodology and identification system to building testability into markup applications is currently "Patent Pending" at the US Patent and Trade Office.*
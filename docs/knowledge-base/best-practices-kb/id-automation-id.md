---
title: ID & Automation ID
page_title: ID & Automation ID
description: Static and unique id attribute for the elements in a dynamic application. It is recommended to assign such during the application development process to ease the automation process. 
position: 1
---
# Element Identification with ID and Automation ID #

As a QA professional, it's **important** to get **involved** with the **development team** early on in the process. This article will discuss just one of the many benefits in doing so – coding standards and the use of IDs for enhanced team productivity. Require this up front and you can significantly cut back test case maintenance.
 
No matter what software you use for your test automation, the method in which elements are identified plays a critical role. Small changes to your application can often break the test's find logic causing your test runs to fail. Let's say a couple elements are moved to another location on the page - if IDs are not present, then alternative find logic is used to locate the element. Such find logic includes identification techniques such as Tag Indexes, NodeIndexPath, XPath, and HTMLPath.
 
I'll use Tag Indexes as my example – if my find logic says locate the tenth \<div> tag (DIV:9), and the application changes making the target element now the ninth <div> tag, your script has just been broken – time to drop into maintenance mode.
 
Stop the madness.
 
Ask your development team to implement IDs for your dynamic HTML applications or Automation IDs for your WPF applications. As long as the IDs are unique, your element repository will not require maintenance when changes are made to your application.
 
Our Automated Testing Tools do an amazing job at automatically identifying elements for you – this saves countless hours and allows you to continue the expansion of your regression suite while keeping your project on schedule. Why not take this to the next level by implementing IDs as a coding standard and substantially reducing your test case maintenance time.

* Dynamic HTML Testers – <a href="http://msdn.microsoft.com/en-us/library/ms533880(v=vs.85).aspx" target="_blank">read more on the Element ID Attribute</a>.
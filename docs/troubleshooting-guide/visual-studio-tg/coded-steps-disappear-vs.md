---
title: Coded Steps Disappear in Visual Studio
page_title: Coded Steps Disappear in Visual Studio
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Coded steps disappear in Visual Studio plugin when user double click on Coded Step for specific project

## PROBLEM

In Visual Studio when you double click on a Coded Step - code-behind file is opened successfully. Switch back to .tstest tab - steps are disappeared.

## SOLUTION

This is happening because you have changed the Test Studio project code base class **'BaseWebAiiTest'** to **'CustomWebAiiTest'**, which does not inherit the original and thus the coded steps cannot be resolved. 

In order to fix this problem so you are able to see your coded steps again, you should do the following steps:


1. In Test Studio project settings Recording options, use the full path to your custom base class, including the namespace, i.e. 'SampleTest.CustomWebAiiTest' ;

2. Generate in the project an independant class that defines the inheritance of your custom base class from Test Studio 'BaseWebAiiTest', i.e.:

```C#
using ArtOfTest.WebAii.Design;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

namespace SampleTest
{
public class CustomWebAiiTest : BaseWebAiiTest
{
}
}
```


---
title: Coded Steps Disappear in Visual Studio
page_title: Coded Steps Disappear in Visual Studio
description: "Find out why coded steps may disappear in Visual Studio when using the Test Studio plugin. This article explains the cause, related to custom base classes, and provides steps to restore coded step visibility in your projects."
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


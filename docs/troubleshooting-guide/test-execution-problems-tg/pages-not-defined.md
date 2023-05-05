---
title: Pages Not Defined
page_title: Pages Not Defined
description: "Executing a Test Studio coded test is not possible due to errors 'Type Pages is not defined' or 'The type or namespace name Pages could not be found'. How to resolve this type of errors"
position: 1
---
# Pages Not Defined

## PROBLEM

When I execute my test in the Standalone version, or build my test project in the VS plugin, I receive one of the following errors:

- Type 'Pages' is not defined
- The type or namespace name 'Pages' could not be found

## SOLUTION

```C#
namespace TestProject2
{
    using ArtOfTest.WebAii.Core;
    using ArtOfTest.WebAii.ObjectModel;
    using ArtOfTest.WebAii.TestAttributes;
    using ArtOfTest.WebAii.TestTemplates;
    using ArtOfTest.WebAii.Controls.HtmlControls;
    public class Pages
}
```
```VB
	Imports ArtOfTest.WebAii.Core
	Imports ArtOfTest.WebAii.ObjectModel
	Imports ArtOfTest.WebAii.TestAttributes
	Imports ArtOfTest.WebAii.TestTemplates
	Imports ArtOfTest.WebAii.Controls.HtmlControls
 
	Namespace TestProject2
 
	Public Class Pages
```

If the code behind files are not using the same namespace, you receive one of the errors. This is how the code behind file should look for *TestProject2*:


```C#
using Telerik.WebAii.Controls.Html;
using Telerik.WebAii.Controls.Xaml;
using System;
using System.Collections.Generic;
using System.Text;
using System.Linq;
 
using ArtOfTest.Common.UnitTesting;
using ArtOfTest.WebAii.Core;
using ArtOfTest.WebAii.Controls.HtmlControls;
using ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts;
using ArtOfTest.WebAii.Design;
using ArtOfTest.WebAii.Design.Execution;
using ArtOfTest.WebAii.ObjectModel;
using ArtOfTest.WebAii.Silverlight;
using ArtOfTest.WebAii.Silverlight.UI;
 
namespace TestProject2
{
```
```VB
Imports Telerik.WebAii.Controls.Html
Imports Telerik.WebAii.Controls.Xaml
Imports System
Imports System.Collections.Generic
Imports System.Text
Imports System.Linq
 
Imports ArtOfTest.Common.UnitTesting
Imports ArtOfTest.WebAii.Core
Imports ArtOfTest.WebAii.Controls.HtmlControls
Imports ArtOfTest.WebAii.Controls.HtmlControls.HtmlAsserts
Imports ArtOfTest.WebAii.Design
Imports ArtOfTest.WebAii.Design.Execution
Imports ArtOfTest.WebAii.ObjectModel
Imports ArtOfTest.WebAii.Silverlight
Imports ArtOfTest.WebAii.Silverlight.UI
 
Namespace TestProject2
```


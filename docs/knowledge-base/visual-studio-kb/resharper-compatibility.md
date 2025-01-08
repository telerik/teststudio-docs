---
title: ReSharper Compatibility
page_title: ReSharper Compatibility
description: ReSharper Compatibility in Test Studio. Cannot resolve symbol error messages in Test Studio.
position: 1
---
# ReSharper Compatibility

*With ReSharper installed, you receive Cannot resolve symbol error messages in Test Studio code-behind files.*

## Solution

ReSharper is warning you that it cannot locate the definition of the element in the project. The problem is that element definitions are kept in our Pages.g.cs(vb) file. This file is not included in the Visual Studio test project, but is included during project builds using an internal custom build task that is defined by Progress Test Studio. 
 
The error message is benign and can be safely ignored.

*With ReSharper installed, there is no autocompletion for elements under a page element under Pages. For example, this object will not autocomplete after 'MainPage':

Pages.MainPage.FrameContentIFrame*

## Solution

Disable ReSharper's IntelliSense and enable Visual Studio's.

1. Click **RESHARPER > Options > Environment > IntelliSense > General**.

2. Select **Visual Studio**.

![VS IntelliSense][1]

[1]: /img/knowledge-base/visual-studio-kb/resharper-compatibility/fig1.png
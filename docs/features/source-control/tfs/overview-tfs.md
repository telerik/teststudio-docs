---
title: Overview
page_title: Integration with Source Control Systems
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /features/source-control/overview
position: 0
---
# Integration with Source Control Systems

Test Studio seamlessly integrates with Microsoft Team Foundation Server to simplify the collaboration between QAs and Developers.

The TFS integration also facilitates the work of a QA team on the same test project, allowing them to check-in their results at the same time and independently. In addition to TFS support, Test Studio can also interact with any other file-based source control system.


- <a href="/features/source-control/tfs/connect-to-tfs" target="_blank">Connect a local project to TFS</a> 
- <a href="/features/source-control/tfs/open-tfs-project" target="_blank">Open a TFS-controlled project</a> 
- <a href="/features/source-control/tfs/project-item-options" target="_blank">Project Item Options</a> 
- <a href="/features/source-control/tfs/sc-alternatives" target="_blank">Alternative, file-based source control systems</a> 

# Integration Methods

If you attempt to integrate with TFS in Test Studio Standalone version and do not have Visual Studio installed, you will receive the following error: *Unable to load source control plugin*.

![Unable to Load][1]

You will need to install Team Explorer. This is the client SKU that allows you to access the TFS functionality.


- <a href="https://www.microsoft.com/en-us/download/details.aspx?id=16338" target="_blank">Visual Studio Team System 2008 Team Explorer</a>
- <a href="https://www.microsoft.com/en-us/download/details.aspx?id=4240" target="_blank">Microsoft Visual Studio Team Explorer 2010</a>


If you are using the Test Studio VS plugin, be aware that Visual Studio has built-in TFS integration.

- <a href="http://msdn.microsoft.com/en-us/library/ms181237%28v=VS.90%29.aspx" target="_blank">Version Control - Visual Studio 2008</a>
- <a href="http://msdn.microsoft.com/library/ms181368.aspx" target="_blank">Version Control - Visual Studio 2010</a> 


[1]: /img/features/source-control/overview/fig1.png
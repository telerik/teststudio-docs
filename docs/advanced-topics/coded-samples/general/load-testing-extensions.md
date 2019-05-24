---
title: Load Testing Extensions
page_title: Load Testing Extensions
description: "Load Testing Extensions in Test Studio."
position: 1
publish: false
---
#Load Testing Extensions#

A load testing plugin is similar to other <a href="/advanced-topics/coded-samples/general/execution-extensions" target="_blank">execution extensions</a>, but implements a different set of interfaces. Instead of a class that implements the IExecutionExtension interface, implement one or more of the following interfaces:

* **ILoadAgentPlugin**

* **ILoadAgentPluginHttpRequest**

* **ILoadAgentPluginVirtualUser**

Each of these has its own set of functions that extend load testing functionality. For example: 

The below code creates a new, randomly-named file every time Test Studio creates a new Virtual User during load testing The code overrides all the extensible load functions, but only gives **VirtualUserAllocated** an implementation. The rest of the functions do nothing, and the exceptions they throw are benign. This class requires an assembly reference to *Telerik.TestStudio.Load.Common.dll*.

```C#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
 
 
using System.IO;
using System.Data;
using System.Data.OleDb;
using System.Windows.Forms;
using ArtOfTest.WebAii.Design.Execution;
using Telerik.TestStudio.Load.Interfaces.Load.API;
 
namespace ClassLibrary1
{
    public class Class1 : ILoadAgentPlugin, ILoadAgentPluginHttpRequest, ILoadAgentPluginVirtualUser
    {
 
        public void VirtualUserAllocated(Guid userProfileId, Guid virtualUserId)
        {
            Random random = new Random();
            int randomNumber = random.Next(0, 5000);
 
            File.Create("c:\\test\\" + randomNumber.ToString());
        }
 
        public void VirtualUserDeallocated(Guid userProfileId, Guid virtualUserId)
        {
            // Your custom implementation here
        }
 
        public void AfterResponseReceived(Guid virtualUserId, int currentStepIndex, System.Net.HttpWebResponse response)
        {
            // Your custom implementation here
        }
 
        public void BeforeRequestSent(Guid virtualUserId, int currentStepIndex, System.Net.HttpWebRequest request)
        {
            // Your custom implementation here
        }
 
        public string OverrideOutgoingUrl(Guid virtualUserId, int currentStepIndex, string url)
        {
            // Your custom implementation here
        }
 
        public void UserProfileAllocated(Guid profileRunID, string profileFriendlyName)
        {
            // Your custom implementation here
        }
    }
}
```

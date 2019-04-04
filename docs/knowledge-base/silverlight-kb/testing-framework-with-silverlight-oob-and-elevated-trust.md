---
title: Testing Framework with Silverlight OOB and Elevated Trust
page_title: Testing Framework with Silverlight OOB and Elevated Trust
description: Using Telerik Testing Framework with Silverlight Out-of-Browser and Elevated Trust. Your Silverlight runs correctly out-of-browser with elevated trust when running without Telerik Testing Framework. When running with Telerik Testing Framework, as part of automatic test execution, an error occurs similar to this - An error has occurred in the script on this page. 
position: 1
---
# Using Telerik Testing Framework with Silverlight Out-of-Browser and Elevated Trust

## Basic functionalities

*Your Silverlight runs correctly out-of-browser with elevated trust when running without Telerik Testing Framework. When running with Telerik Testing Framework, as part of automatic test execution, an error occurs similar to this:*

![Error][1]

## Solution

This is a communication problem. Telerik Testing Framework supports elevated trust, but after a bit of configuring. Here are the changes that need to be made:
 
All web service calls need to be absolute hard-coded paths. They cannot use relative paths to locate their service. This is because during Out of Browser automation, Telerik software alters the path which is no longer understood by the web server.
 
The code below will fail because it uses a relative path:

```
TestMath context = new TestMath()
 ->
public TestMath() : 
this(new WebDomainClient<ITestMathContract>(new Uri("TestAutomationByRia-Web-Services-TestMath.svc", UriKind.Relative)))
{
}
```

This is fixed by modifying the initial call to hardwire in a service path:

```
TestMath context = new TestMath(new Uri("http://localhost:49569/ClientBin/TestAutomationByRia-Web-Services-TestMath.svc", UriKind.Absolute));
```


We have effectively forced the app to make cross-site calls, so this needs to be enabled on the server. You'll need to modify the app manifest, as well as generate some policy documents which tell the server this sort of operation is acceptable.
 
The AppManifest.xml file needs to set ExternalCallersFromCrossDomain in its root node:

```
<Deployment ... ExternalCallersFromCrossDomain="ScriptableOnly" ... >
```

And in the root of the server, these files need to be created:

**clientaccesspolicy.xml**

```XML
<?xml version="1.0" encoding="utf-8"?>
<access-policy>
    <cross-domain-access>
        <policy>
            <allow-from http-request-headers="*">
                <domain uri="*"/>
            </allow-from>
            <grant-to>
                <resource path="/" include-subpaths="true"/>
            </grant-to>
        </policy>
    </cross-domain-access>
</access-policy>
```

**crossdomain.xml**

```XML
<?xml version="1.0"?>
<!DOCTYPE cross-domain-policy SYSTEM "http://www.macromedia.com/xml/dtds/cross-domain-policy.dtd">
<cross-domain-policy>
  <allow-http-request-headers-from domain="*" headers="SOAPAction,Content-Type"/>
</cross-domain-policy>
```

t is possible that some lesser combination of these actions would be sufficient to get the app running, however these are the steps we had to take in our testing.

[1]: /img/knowledge-base/silverlight-kb/testing-framework-with-silverlight-oob-and-elevated-trust/fig1.png



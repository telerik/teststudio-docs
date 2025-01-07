---
title: Invoke Web Service Call
page_title: Invoke a Web Service Call
description: "Invoke a Web Service Call from a coded step in Test Studio."
previous_url: /user-guide/code-samples/general/invoke-web-service-call.aspx
position: 1
---
# Invoke a Web Service Call

*I would like to invoke a web service call from a coded step in Test Studio and verify its response.*

## Solution

Below you will find a code sample which demonstrates one possible solution for this automation challenge. This sample requires that you add references to the following assemblies:

* System.Net

* System.IO

* System.Xml

See this <a href="/advanced-topics/coded-steps/add-assembly-reference" target="_blank">article</a>. which explains how to add an assembly reference in Test Studio (Standalone version).

```C#
// Create the WebRequest object we'll use for sending the request
WebRequest request = WebRequest.Create("http://money.service.msn.com/StockQuotes.aspx?v=1&symbols=$INDU,AAPL,NFLX");
request.Method = "GET";
  
// Send the request and read the response
using (WebResponse response = request.GetResponse())
{
    // Verify the status code is OK
    Assert.AreEqual<string>("OK", ((HttpWebResponse)response).StatusDescription);
    // Get the stream containing content returned by the server.
    using (Stream responseStream = response.GetResponseStream())
    {
        // Parse the response into an XML document and validate we got the data expected
        // It should look like this:
  
        // <?xml version="1.0" ?>
        // <quotesdata>
        // <ticker symbol="$INDU" ... </quotesdata>
  
        XmlDocument doc = new XmlDocument();
        doc.Load(responseStream);
        Assert.AreEqual<int>(2, doc.ChildNodes.Count);
        Assert.AreEqual<int>(3, doc.ChildNodes[1].ChildNodes.Count);
        XmlNode aapl = doc.SelectSingleNode("/quotesdata/ticker[@symbol=\"AAPL\"]");
        XmlNode nflx = doc.SelectSingleNode("/quotesdata/ticker[@symbol=\"NFLX\"]");
        XmlNode indu = doc.SelectSingleNode("/quotesdata/ticker[@symbol=\"$INDU\"]");
        Assert.IsNotNull(aapl);
        Assert.IsNotNull(nflx);
        Assert.IsNotNull(indu);
    }
}
```
```VB
' Create the WebRequest object we'll use for sending the request
Dim request As WebRequest = WebRequest.Create("http://money.service.msn.com/StockQuotes.aspx?v=1&symbols=$INDU,AAPL,NFLX")
request.Method = "GET"
 
' Send the request and read the response
Using response As WebResponse = request.GetResponse()
    ' Verify the status code is OK
    Assert.AreEqual(Of String)("OK", DirectCast(response, HttpWebResponse).StatusDescription)
    ' Get the stream containing content returned by the server.
    Using responseStream As Stream = response.GetResponseStream()
        ' Parse the response into an XML document and validate we got the data expected
        ' It should look like this:
 
        ' <?xml version="1.0" ?>
        ' <quotesdata>
        ' <ticker symbol="$INDU" ... </quotesdata>
 
        Dim doc As New XmlDocument()
        doc.Load(responseStream)
        Assert.AreEqual(Of Integer)(2, doc.ChildNodes.Count)
        Assert.AreEqual(Of Integer)(3, doc.ChildNodes(1).ChildNodes.Count)
        Dim aapl As XmlNode = doc.SelectSingleNode("/quotesdata/ticker[@symbol=""AAPL""]")
        Dim nflx As XmlNode = doc.SelectSingleNode("/quotesdata/ticker[@symbol=""NFLX""]")
        Dim indu As XmlNode = doc.SelectSingleNode("/quotesdata/ticker[@symbol=""$INDU""]")
        Assert.IsNotNull(aapl)
        Assert.IsNotNull(nflx)
        Assert.IsNotNull(indu)
    End Using
End Using
```

---
title: JSON Objects
page_title: JSON Objects
description: "Using JSON objects in a coded step in Test Studio. Coded test to handle JSON objects in Test Studio. Test Studio Testing Framework handle JSON objects in tests."
position: 5
---
#Handling JSON Objects

Your tests can understand JSON (<a href="http://www.json.org/" target="_blank" rel="nofollow">JavaScript Object Notation</a>) and can handle strongly typed objects returned from JavaScript. This might be a bit advanced for regular testers implementing test automation. However, if you are building mini-frameworks on top of Telerik Testing Framework, it is a great tool to help you get rid of having to parse complex strings returned by the InvokeScript function.
 
This is a basic example of how to use JSON:

```C#
[TestMethod]
public void KeyValuePairs()
{
    Manager.LaunchNewBrowser();
 
    // We are using a dummy call here. The call can be to any JS method on your page
    JsonObject o = ActiveBrowser.Actions.InvokeScript<JsonObject>(
        "({key1:'value1', key2:'value2'})");
 
    Assert.AreEqual<string>("value1", o["root"]["key1"]);
    Assert.AreEqual<string>("value2", o["root"]["key2"]);
}
```
```VB
<TestMethod()> _
Public Sub KeyValuePairs()
    Manager.LaunchNewBrowser()
 
    ' We are using a dummy call here. The call can be to any JS method on your page
    Dim o As JsonObject = ActiveBrowser.Actions.InvokeScript(Of JsonObject)("({key1:'value1', key2:'value2'})")
 
    Assert.AreEqual(Of String)("value1", o("root")("key1"))
    Assert.AreEqual(Of String)("value2", o("root")("key2"))
End Sub
```

In this example we define our own object in a Data Contract:

```C#
[DataContract]
public class MyObject
{
    [DataMember(Name = "one")]
    public int One { get; set; }
    [DataMember(Name = "fifteen")]
    public int Fifteen { get; set; }
}
 
[TestMethod]
public void ReturnObject()
{
    Manager.LaunchNewBrowser();
    MyObject o = Actions.InvokeScript<MyObject>("({one:1, fifteen:15})");
    Assert.AreEqual<int>(1, o.One);
    Assert.AreEqual<int>(15, o.Fifteen);
}
```
```VB
<DataContract()> _
Public Class MyObject
    Private _One As Integer
    <DataMember(Name:="one")> _
    Public Property One() As Integer
        Get
            Return _One
        End Get
        Set(ByVal value As Integer)
            _One = value
        End Set
    End Property
    Private _Fifteen As Integer
    <DataMember(Name:="fifteen")> _
    Public Property Fifteen() As Integer
        Get
            Return _Fifteen
        End Get
        Set(ByVal value As Integer)
            _Fifteen = value
        End Set
    End Property
End Class
 
<TestMethod()> _
Public Sub ReturnObject()
    Manager.LaunchNewBrowser()
    Dim o As MyObject = Actions.InvokeScript(Of MyObject)("({one:1, fifteen:15})")
    Assert.AreEqual(Of Integer)(1, o.One)
    Assert.AreEqual(Of Integer)(15, o.Fifteen)
End Sub
```

In this example we'll access an array returned by InvokeScript, treat it as JSON, and parse it manually for its values.

```C#
var actions = Manager.Current.ActiveBrowser.Actions;
JsonObject result = actions.InvokeScript <JsonObject>("window.my_list=[1,2,3]");
JsonArray arr = (JsonArray)result["root"];
for (int i = 0; i < 3; i++)
{
double val = arr[i];
Log.WriteLine(val.ToString());
}
```
```VB
Dim actions = Manager.Current.ActiveBrowser.Actions
Dim result As JsonObject = actions.InvokeScript(Of JsonObject)("window.my_list=[1,2,3]")
Dim arr As JsonArray = DirectCast(result("root"), JsonArray)
For i As Integer = 0 To 2
    Dim val As Double = arr(i)
    Log.WriteLine(val.ToString())
Next
```
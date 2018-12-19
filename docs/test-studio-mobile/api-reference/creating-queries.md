---
title: Creating Queries
page_title: Creating Queries
description: "Telerik Mobile Testing - Creating Queries"
position: -1
publish: true
slug: ms-create-query
---

# Creating queries

<select id="methodsSelect" onchange="window.location.hash='#'+event.currentTarget.selectedOptions[0].value;">
 <option value="android">Android</option>  <option value="ios">iOS</option> <option value="web">Web</option> <option value="hybrid">Hybrid</option>
</select>

Queries are used to select a view (Native or Web).

When a query is executed, all elements matching the query are stored in an internal array. By default the element at index 0 is used for any operations to be performed. This index can be manually specified in the query by setting index.

*Note: The properties are case sensitive, you should use them in the queries as they are defined in your application.*

> A *Dictionary* data structure is used in the sample code lines bellow. It is necessary to add a reference to the project of the *System.Collections.Generic* namespace.

```C#
{ Class = "TYPE", Index=2 }
```

```VB
{.Class = "TYPE", .Index=2 }
```



<a id="android"></a>
## Android

Android queries are objects that define one or more properties to match in a **android.view.View**. If a view is found where all properties match, the requested operation is performed on that view. If multiple views with matching properties are found, the operation is performed on the first view found to be a match.

```C#
AndroidQuery query = new AndroidQuery(){Properties = new Dictionary<string, string>(){ {  "propertyName1" , "expectedValue"}, {"propertyName2" , "expectedValue2"} } };
```

```VB
Dim query As New AndroidQuery()
query.Properties.Add("propertyName1", "expectedValue")
query.Properties.Add("propertyName2", "expectedValu2")
```

Sometimes it is necessary to locate a view using supplemental information, such as a class type (android.view.View, android.widget.Button, etc). This can be done as follows:

```C#
// TYPE can be android.view.View, android.widget.Button, etc.
AndroidQuery query = new AndroidQuery(){Class="TYPE"};
```
```VB

Dim query As New AndroidQuery()
query.Class="TYPE"
```
Queries for a class type will find views of that type, and views that derive from that type in their inheritance chain. It is possible to define a query that only locates views with an exact class type, excluding parent class types.

```C#
// TYPE can be android.view.View, android.widget.Button, etc.
AndroidQuery query = new AndroidQuery(){Class="TYPE", ExactClass = true};
```
```VB
Dim query As New AndroidQuery() With {.Class = "TYPE", .ExactClass  = True}
```

Queries for class type can be combined with queries for property values.

```C#
{% raw %}
AndroidQuery query = new AndroidQuery(){Class="android.widget.Button", Properties = new Dictionary<string, string>(){{"text", "Button1"}}};
{% endraw %}
```
```VB
Dim query As New AndroidQuery() With {.Class = "android.widget.Button"}
query.Properties.Add("text", "Button 1")
```
You can query for a control using the id specified in a layout XML file. As an example, to query for the control specified as:

```XML
<View android:id="@+id/myControl"/>
```

format your query like:

```C#
{% raw %}
AndroidQuery query = new AndroidQuery(){Class="TYPE", Properties = new Dictionary<string, string>(){{"ID", "myControl"}}};
{% endraw %}
```
```VB
Dim query As New AndroidQuery()
query.Properties.Add("ID", "myControl")
```

**Chained queries** can be used to perform complex queries that require many query types. A chained query is an array of single queries. Each query of the array represents a child of the previous query in the array. The first query represents a child of the top-most view.

```C#
//Finds the first android.widget.ExpandableListView, then search inside of it for android.widget.Button with index 10 
AndroidQuery[] chainedQuery = new AndroidQuery[] { new AndroidQuery(){Class = "TYPE"}, new AndroidQuery() {Class = "TYPE", Index = 10} } ;
```

```VB
Dim chainedQuery As AndroidQuery() = New AndroidQuery() {New AndroidQuery() With {.Class = "TYPE"}, New AndroidQuery() With {.Class = "TYPE", .Index=10}}
```

<a href="#methodsSelect">Back to Top</a>
<br>

<a id="ios"></a>
## iOS

iOS queries are objects that define one or more properties to match in a UIView. If a view is found where all properties match, the requested operation is performed on that view. If multiple views with matching properties are found, the operation is performed on the first view found to be a match.

```C#
IOSQuery query = new IOSQuery(){Properties = new Dictionary<string, string>(){ {  "propertyName1" , "expectedValue"}, {"propertyName2" , "expectedValue2"} } };
```

```VB
Dim query As New IOSQuery()
query.Properties.Add("propertyName1", "expectedValue")
query.Properties.Add("propertyName2", "expectedValu2")
```
Sometimes it is necessary to locate a view using supplemental information, such as a class type (UIView, UIButton, etc). This can be done as follows:

```C#
// TYPE can be UIView, UIButton, etc.
IOSQuery query = new IOSQuery(){Class="TYPE"};
```
```VB
Dim query As New IOSQuery() With {.Class="Type"}
```

Queries for a class type will find views of that type, and views that derive from that type in their inheritance chain. It is possible to define a query that only locates views with an exact class type, excluding parent class types.

```C#
//TYPE can be UIView, UIButton, etc
IOSQuery query = new IOSQuery(){Class="TYPE", ExactClass = true};
```
```VB
Dim query As New IOSQuery() With { .Class="Type", .ExactClass = True}
```
Queries for class type can be combined with queries for property values.

```C#
{% raw %}
IOSQuery query = new IOSQuery(){Class="UIButton", Properties = new Dictionary<string, string>(){{"currentTitle", "Button 1"}}};
{% endraw %}
```
```VB
Dim query As New AndroidQuery()
query.Class="android.widget.Button"
query.Properties.Add("text", "Button 1")
```

**Chained queries** can be used to perform complex queries that require many query types. A chained query is an array of single queries. Each query of the array represents a child of the previous query in the array. The first query represents a child of the window.

```C#
//Finds the first UITableView, then search inside of it for UITableViewCell with index 10 
IOSQuery[] chainedQuery = new IOSQuery[] { new IOSQuery(){Class = "UITableView"}, new IOSQuery() {Class = "UITableViewCell", Index = 10} } ;
```

```VB
Dim chainedQuery As IOSQuery() = New IOSQuery() {New IOSQuery() With {.Class = "UITableView"}, New IOSQuery() With {.Class = "UITableViewCell", .Index=10}}
```

<a href="#methodsSelect">Back to Top</a>
<br>

<a id="web"></a>
## Web

Web queries are objects that define one or more properties to match in a **Html element**. If an element is found where all properties match, the requested operation is performed on that element. If multiple elements with matching properties are found, the operation is performed on the first element found to be a match.

Sometimes it is necessary to locate an element using supplemental information, such as a ClassName (ui-autocomplete). This can be done as follows:

```C#
//Search for html element with ClassName ui-autocomplete
WebQuery query = new WebQuery() {ClassName = "ui-autocomplete"};
```
```VB
Dim query As New WebQuery() With { .ClassName = "ui-autocomplete" }
```

or by ID

```C#
//Search for html element with ID ui-autocomplete
WebQuery queryById = new WebQuery() {Id = "ui-autocomplete"};
```
```VB
Dim queryById As New WebQuery() With { .Id = "ui-autocomplete" }
```

or by XPath

```C#
//Search for html element with XPath @"//*[@id=""c1""]/div[1]/div[1]/a"
WebQuery queryByXpath = new WebQuery() { XPath = @"//*[@id=""c1""]/div[1]/div[1]/a" };
```
```VB
Dim queryByXpath As New WebQuery() With { .XPath = "//*[@id=""c1""]/div[1]/div[1]/a"  }
```

or by TagName and Index

```C#
//Search for html element with TagName a
WebQuery queryByTagNameAndIndex = new WebQuery() { TagName = "a", Index = 1 };
```
```VB
Dim queryByTagNameAndIndex As New WebQuery() With { .TagName = "a", .Index = 1 }
```

You can also combine them into one query

```C#
//Search for html element with ClassName ui-autocomplete, ID ui-autocomplete, TagName a and Index 1
WebQuery query = new WebQuery() {ClassName = "CLASSNAME", Id = "ID", TagName = "TAGNAME", Index = 1 };
```
```VB
Dim query As New WebQuery() With { .ClassName = "CLASSNAME", .Id = "ID", .TagName = "a", .Index = 1 }
```

**Chained queries** can be used to perform complex queries that require many query types. A chained query is an array of single queries. Each query of the array represents a child of the previous query in the array. The first query represents a child of the window.


```C#
//Finds the first element with ClassName col1, then search inside of it for an element with TagName a and index 1
WebQuery[] chainedQuery = new WebQuery[] {new WebQuery(){ClassName = "col1"}, new WebQuery() { TagName = "a", Index = 1 } };
```
```VB
Dim chainedQuery As WebQuery() = New WebQuery() {New WebQuery() With { .ClassName = "col1" }, New WebQuery() With { .TagName = "a", .Index=1 }}
```

<a href="#methodsSelect">Back to Top</a>
<br>

<a id="hybrid"></a>
## Hybrid

Hybrid queries are a combination of native and web queries. A native query (iOS, Android) is needed to identify the native web view that hosts the app and a web query to identify a specific web element. If the hybrid app is hosted inside only one web view, then the native view query can be skipped:

```C#
// This will perform a web tap action on the provided element located inside the first found WebView object in the app.
this.ActiveDevice.Web.Tap(this.Elements.MyScreen.webview.BUTTON);

// This will perform a web tap action on the provided element located inside a specific WebView object in the app.
this.ActiveDevice.Web.Tap(this.Elements.MyScreen.webview.View, this.Elements.MyScreen.webview.BUTTON);
```

```VB
' Me.ActiveDevice.Web.Tap(Elements.MyScreen.webview.BUTTON)

' Me.ActiveDevice.Web.Tap(Elements.MyScreen.webview.View, Elements.MyScreen.webview.BUTTON)
```

<a href="#methodsSelect">Back to Top</a>
<br>
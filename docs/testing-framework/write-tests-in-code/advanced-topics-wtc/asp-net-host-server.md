---
title: Asp.NET Host Server
page_title: Asp.NET Host Server
description: "Test Studio Testing Framework support for Asp.NET Host Server"
position: 1
---
#Using Asp.Net In-Process Host Server

Many of our customers have asked for a way to execute tests without the need for a browser. They wanted a light-weight, fast and agile execution that fits within their Continuous Integration Builds and works easily with 'CruiseControl.Net' or 'Visual Studio Team Foundation Server.' We enabled these scenarios with two areas of support:

1.&nbsp; We enabled Non-Interactive execution using Internet Explorer and Firefox. Continuous Integration Servers usually use a user account that logs on non-interactively to the server machines to perform the build and run the smoke or BVT (Build Verification Tests) tests. We made fixes to enable these scenarios and provided developers a way to detected when they are running in non-interactive mode so they can automatically disable scenarios that require interactive UI like tests that move the mouse to click on items or handle custom dialogs. Tests can check the **Settings.IsUserInteractiveMode** property to figure out if they are running in non-interactive mode or not and perform the appropriate actions. If you attempt to perform an action that is not allowed in NonInteractive mode, an **'UnsupportedNonInteractiveOperationException'** is thrown to help inform you of this situation.

2.&nbsp; Telerik Testing Framework can host the Asp.Net runtime in-process. This allows you to execute and process Asp.Net pages without the need for a web server, a browser or any external processes. All requests are performed internally within the test .exe or .dll process. Instead of re-inventing the wheel, we opted to integrate the Asp.Net Host implemented by the 'Plasma' project at here. We extended the post backs support to allow for all common actions of Asp.Net web pages including clicking on Asp.Net Calendar links, TreeView, and Menu controls. All actions are implemented using the same **Actions** interface used for Internet Explorer and Firefox so your tests are consistent regardless of which browser/host they choose to run under. You can actually switch back and forth between browsers including the Asp.Net Host by simply setting the 'Settings.DefaultBrowser' property. This allows for ultimate flexibility to choose the environment you want your tests to run under depending on your need. (i.e. running on integration server, use AspNetHost, running on your desktop, use IE or Firefox. All with the flip of a flag.)

* With the Asp.Net In-Process server being a browser-less host, tests that require heavy client javascript execution might not be suited for this browser since there is no javascript engine running. Heavy Ajax scenarios should be tested using IE or Firefox. Asp.Net In-Proc Server is ideal in BVT type of scenarios or in unit tests that are focused on testing the business logic behind UI elements actions. It is not ideal for End-To-End Scenario automated testing.

* Just like Non-Interactive mode, running under the Asp.Net In-Process server will disable certain features that do not apply in that mode. For example, if you attempt to access the 'Browser.Window' object or perform 'Actions.InvokeScript', the Framework will throw an **'UnsupportedBrowserOperationException'** given that these scenarios do not apply when running under this mode.

* If you are using NUnit 2.4 or higher you might experience AppDomainUnloadException similar to the issue described here. To work around this issue, please set the configuration setting legacyUnhandledExceptionPolicy to '0' in nunit.exe.config file.
 
\<legacyUnhandledExceptionPolicy enabled="0" />

With all these in mind, let's look at an example that illustrates how we can enable our tests to run against the Asp.Net inproc host. Here is a simply Asp.Net page that utilizes several Asp.Net controls:

```ASP
<%@ Page Language="C#" %>
 
<!DOCTYPE htmlPUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
 
<script runat="server">
 
    protected void treeView1_SelectedNodeChanged(object sender, EventArgs e)
    {
        label1.Text = "TreeView1 SelectedNodeChanged To: " + treeView1.SelectedNode.Text;
    }
 
    protected void Calendar1_SelectionChanged(object sender, EventArgs e)
    {
        label1.Text = "Calendar1 SelectionChanged To: " + Calendar1.SelectedDate.ToString();
    }
 
    protected void LinkButton1_Click(object sender, EventArgs e)
    {
        label1.Text = "LinkButton1 Clicked";
    }
 
    protected void Button1_Click(object sender, EventArgs e)
    {
        label1.Text = "Button1 Clicked";
    }
 
    protected void DropDownList1_SelectedIndexChanged(object sender, EventArgs e)
    {
        label1.Text = "DropDownList1 Changed To: " + DropDownList1.SelectedItem.Text;
    }
 
    protected void TextBox1_TextChanged(object sender, EventArgs e)
    {
        label1.Text = "TextBox1 TextChanged To: " + TextBox1.Text;
    }
</script>
 
<html xmlns="http://www.w3.org/1999/xhtml" >
<head runat="server">
    <title>Untitled Page</title>
</head>
<body>
    <form id="form1" runat="server">
    <div>
 
        <asp:Label Font-Bold="true"Font-Size="X-Large" ID="label1" runat="server" Text="NoAction"></asp:Label>
        <br/>
        <br/>
        <asp:Button ID="Button1"runat="server" Text="Button" OnClick="Button1_Click" />
        <asp:LinkButton ID="LinkButton1"runat="server" OnClick="LinkButton1_Click">LinkButton</asp:LinkButton>
        <asp:TextBox AutoPostBack="true" ID="TextBox1" runat="server" OnTextChanged="TextBox1_TextChanged"></asp:TextBox>
        <asp:DropDownList ID="DropDownList1" AutoPostBack="true" runat="server" OnSelectedIndexChanged="DropDownList1_SelectedIndexChanged">
            <asp:ListItem>Item1</asp:ListItem>
            <asp:ListItem>Item2</asp:ListItem>
        </asp:DropDownList>
        <asp:Calendar ID="Calendar1"runat="server" OnSelectionChanged="Calendar1_SelectionChanged"></asp:Calendar>
 
    </div>
        <asp:TreeView ID="treeView1" runat="server" OnSelectedNodeChanged="treeView1_SelectedNodeChanged">
            <Nodes>
                <asp:TreeNode Text="Node1" Value="Node1"></asp:TreeNode>
                <asp:TreeNode Text="Node2" Value="Node2"></asp:TreeNode>
            </Nodes>
        </asp:TreeView>
    </form>
</body>
</html>
```


You can run this page using the Asp.Net InProc server by first setting the default browser to 'AspNetHost' and setting the physical location of the web application. For example, you can override these settings in your test initialization or set them in your .config file:

```C#
// Set the default browser to be AspNetHost
settings.DefaultBrowser = BrowserType.AspNetHost;
 
// Set the location of the Asp.Net App
settings.WebAppPhysicalPath = @"C:\MyAspNetApp\";
```
```VB
' Set the default browser to be AspNetHost
mysettings.DefaultBrowser = BrowserType.AspNetHost
 
' Set the location of the Asp.Net App
mysettings.WebAppPhysicalPath = System.IO.Path.Combine(Globals.PATH_TO_PAGES, "AspNetApp")
```

Next you can perform your automation in the same manner as you would for any other browser. For example:


```C#
// Will initialize a new AspNetApplication object.
Manager.LaunchNewBrowser();
 
// Request the page we want.
ActiveBrowser.NavigateTo(PAGE_NAME);
 
// We can access raw http request properties when the
// browser is AspNetHost.
if (ActiveBrowser.BrowserType == BrowserType.AspNetHost)
{
    // we wrap this part with an if..else statement so that
    // this test can still run on other browsers without
    // having to perform any recompilation.
    AspNetHostBrowser hostBrowser = (AspNetHostBrowser)ActiveBrowser;
 
    // get the last status code for the last response.
    // You can also access the full Request/Response objects using
    // hostBrowser.AspNetAppInstance.LastResponse
    // or
    // hostBrowser.AspNetAppInstance.LastRequest
    Assert.IsTrue(hostBrowser.Status == 200);
}
else
{
    // Do some other type of verification...
}
 
Element label = ActiveBrowser.Find.ById("label1");
 
// Click a button
Actions.Click(Find.ById("button1"));
label.Refresh();
Assert.IsTrue(label.InnerText.Contains("Button1 Clicked"));
 
// Click a linkbutton
Actions.Click(Find.ById("linkbutton1"));
label.Refresh();
Assert.IsTrue(label.InnerText.Contains("LinkButton1 Clicked"));
 
// Set Text
Actions.SetText(Find.ById("textbox1"),"Hello!");
label.Refresh();
Assert.IsTrue(label.InnerText.Contains("Hello!"));
 
//Select From DropDown
Actions.SelectDropDown(Find.ById("dropdownlist1"), "Item2");
label.Refresh();
Assert.IsTrue(label.InnerText.Contains("Item2"));
 
// Select a link on the calendar.
string dateToSelect = DateTimeFormatInfo.CurrentInfo.GetMonthName(DateTime.Today.Month) + " " +
    string.Format("{0:00}", DateTime.Today.Day);
 
Actions.Click(Find.ByAttributes("title=~" + dateToSelect));
label.Refresh();
Assert.IsTrue(label.InnerText.Contains(DateTime.Today.ToShortDateString()));
 
// Select a node in a treeview
Actions.Click(Find.ById("treeView1t1"));
label.Refresh();
Assert.IsTrue(label.InnerText.Contains("Node2"));
```
```VB

' Will initialize a new AspNetApplication object.
Manager.LaunchNewBrowser()
 
' Request the page we want.
ActiveBrowser.NavigateTo(PAGE_NAME)
 
' We can access raw http request properties when the
' browser is AspNetHost.
If (ActiveBrowser.BrowserType = BrowserType.AspNetHost) Then
    ' we wrap this part with an if..else statement so that
    ' this test can still run on other browsers without
    ' having to perform any recompilation.
    Dim hostBrowser As AspNetHostBrowser = CType(ActiveBrowser, AspNetHostBrowser)
 
    ' get the last status code for the last response.
    ' You can also access the full Request/Response objects using
    ' hostBrowser.AspNetAppInstance.LastResponse
    ' or
    ' hostBrowser.AspNetAppInstance.LastRequest
    Assert.IsTrue((hostBrowser.Status = 200))
Else
    ' Do some other type of verification...
End If
 
Dim label As Element = ActiveBrowser.Find.ById("label1")
 
' Click a button
Actions.Click(Find.ById("button1"))
label.Refresh()
Assert.IsTrue(label.InnerText.Contains("Button1 Clicked"))
 
' Click a linkbutton
Actions.Click(Find.ById("linkbutton1"))
label.Refresh()
Assert.IsTrue(label.InnerText.Contains("LinkButton1 Clicked"))
 
' Set Text
Actions.SetText(Find.ById("textbox1"), "Hello!")
label.Refresh()
Assert.IsTrue(label.InnerText.Contains("Hello!"))
 
'Select From DropDown
Actions.SelectDropDown(Find.ById("dropdownlist1"), "Item2")
label.Refresh()
Assert.IsTrue(label.InnerText.Contains("Item2"))
 
' Select a link on the calendar.
Dim dateToSelect As String = (DateTimeFormatInfo.CurrentInfo.GetMonthName(DateTime.Today.Month) + (" " + String.Format("{0:00}", DateTime.Today.Day)))
Actions.Click(Find.ByAttributes(("title=~" + dateToSelect)))
label.Refresh()
Assert.IsTrue(label.InnerText.Contains(DateTime.Today.ToShortDateString))
 
' Select a node in a treeview
Actions.Click(Find.ById("treeView1t1"))
label.Refresh()
Assert.IsTrue(label.InnerText.Contains("Node2"))
```


##Debugging Page Requests

Given that these page requests are running in-process without any UI showing, it is sometimes difficult to see what exactly is being rendered. To make debugging scenarios easier, Telerik Testing Framework enables the option of rendering the responses from the Asp.Net In-Process server into an IE browser instance. To enable this debug mode, simply set the **Settings.EnableUILessRequestViewing** to True and an IE instance will launch and redirect a copy of all responses from the Asp.Net host to that instance so you can visually inspect the UI of the pages.

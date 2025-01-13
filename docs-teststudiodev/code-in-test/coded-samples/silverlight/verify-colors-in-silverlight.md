---
title: Verify Colors in Silverlight
page_title: Verify Colors in Silverlight - Test Studio Dev Documentation
description: Verify Colors in Silverlight
position: 1
---
# Verify Colors in Silverlight

_I would like to add a color verification for an element in a Silverlight application._

## Solution

The code below demonstrates this approach against this <a href="http://demos.telerik.com/silverlight/#TreeView/Performance" target="_blank">Telerik demo site</a>. It gets the first item in the menu and verifies that its foreground color matches pre-defined values:

````C#
    Manager.Settings.Web.EnableSilverlight = true; 
    Manager.LaunchNewBrowser(); 
    ActiveBrowser.NavigateTo("http://demos.telerik.com/silverlight/#TreeView/Performance"); 
    SilverlightApp app = ActiveBrowser.SilverlightApps()[0]; 
    app.Find.Strategy = FindStrategy.WhenNotVisibleReturnElementProxy; 
    Button b = app.Find.ByAutomationId<Button>("button"); 
    b.Wait.ForExists(60000); 
    b.User.Click();
    
    FrameworkElement installerElem = app.Find.ByTextContent("^Installer Branc"); 
    installerElem.Wait.ForExists(30000); 
    TextBlock installer= installerElem.CastAs<TextBlock>();
    Log.WriteLine(installer.Text);
    Dictionary<string, string> props = installerElem.GetProperties();
    Assert.IsTrue(props.ContainsKey("Text"));
    Log.WriteLine("Text = " + installerElem.TextContent);
    ArtOfTest.WebAii.Silverlight.UI.Brush textblockBrush = (Brush)installerElem.GetProperty(new AutomationProperty("Foreground", typeof(Brush)));
    
    if (textblockBrush is SolidColorBrush)
    {
        Color actualColor = ((SolidColorBrush)textblockBrush).Color;
        Assert.AreEqual<Byte>(255, actualColor.A, "Error: alpha color does not match expected.");
        Assert.AreEqual<Byte>(105, actualColor.B, "Error: red color does not match expected.");
        Assert.AreEqual<Byte>(72, actualColor.G, "Error: green color does not match expected.");
        Assert.AreEqual<Byte>(40, actualColor.R, "Error: blue color does not match expected.");
    }
    else
    {
        // If it's not a SolidColorBrush what is it? How do we handle it?
        throw new ApplicationException("Expecting a SolidColorBrush, but got a " + textblockBrush.GetType().ToString());
    }
````
````VB

    Manager.Settings.Web.EnableSilverlight = True
    Manager.LaunchNewBrowser()
    ActiveBrowser.NavigateTo("http://demos.telerik.com/silverlight/#TreeView/Performance")
    Dim app As SilverlightApp = ActiveBrowser.SilverlightApps()(0)
    
    app.Find.Strategy = FindStrategy.WhenNotVisibleReturnElementProxy
    Dim b As Button = app.Find.ByAutomationId(Of Button)("button")
    b.Wait.ForExists(60000)  
    b.User.Click()    
    
    Dim installerElem As FrameworkElement = app.Find.ByTextContent("^Installer Branc")
    installerElem.Wait.ForExists(30000)
    Dim installer As TextBlock = installerElem.CastAs(Of TextBlock)()
    Log.WriteLine(installer.Text)      
    
    Dim props As Dictionary(Of String, String) = installerElem.GetProperties()
    Assert.IsTrue(props.ContainsKey("Text"))
    
    Log.WriteLine("Text = " + installerElem.TextContent)
    
    Dim textblockBrush As ArtOfTest.WebAii.Silverlight.UI.Brush = DirectCast(installerElem.GetProperty(New AutomationProperty("Foreground", GetType(Brush))), Brush)
    
    If TypeOf textblockBrush Is SolidColorBrush Then
        Dim actualColor As Color = DirectCast(textblockBrush, SolidColorBrush).Color
        Assert.AreEqual(Of [Byte])(255, actualColor.A, "Error: alpha color does not match expected.")
        Assert.AreEqual(Of [Byte])(105, actualColor.B, "Error: red color does not match expected.")
        Assert.AreEqual(Of [Byte])(72, actualColor.G, "Error: green color does not match expected.")
        Assert.AreEqual(Of [Byte])(40, actualColor.R, "Error: blue color does not match expected.")
    Else
        Throw New ApplicationException("Expecting a SolidColorBrush, but got a " + textblockBrush.[GetType]().ToString())
    End If
````





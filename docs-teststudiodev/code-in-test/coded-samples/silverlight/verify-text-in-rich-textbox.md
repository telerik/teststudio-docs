---
title: Verify Text in Rich TextBox
page_title: Verify Text in Rich TextBox - Test Studio Dev Documentation
description: Verify Text in Rich TextBox
position: 2
---
# Verify Text in a Silverlight RichTextBox

_I cannot verify all the text or its properties in my Silverlight RichTextBox. The contents are either not visible or each word is contained in an individual TextBlock in the Visual Tree._

## Solution

The <a href="http://msdn.microsoft.com/en-us/library/system.windows.controls.richtextbox%28v=vs.95%29.aspx" target="_blank">Silverlight RichTextBox</a> is tricky to work with. It is a "container" type of control, meaning it contains other <a href="http://msdn.microsoft.com/en-us/library/system.windows.documents.block%28v=vs.95%29.aspx" target="_blank">"block" elements</a>, usually the <a href="http://msdn.microsoft.com/en-us/library/system.windows.documents.paragraph%28v=vs.95%29.aspx" target="_blank">Paragraph</a> or <a href="http://msdn.microsoft.com/en-us/library/system.windows.documents.section%28v=vs.95%29.aspx" target="_blank">Section</a>. It is these block elements that hold the actual text displayed in the RichTextBox. Thus, to fetch the displayed text, you must enumerate through the individual blocks and fetch the text from each block element.

To make matters worse, the contents of the RichTextBox may not be contained in the Silverlight Visual Tree. You have to get the Xaml property and parse the contents yourself. Here is an example. Let's assume that you have this in the XAML file for your Silverlight application:

````XAML
<RichTextBox AutomationProperties.AutomationId="richTextBox1" Name="richTextBox1" Margin="310,6,6,235">
    <Paragraph FontSize="11" FontFamily="Portable User Interface" Foreground="#FF000000" FontWeight="Normal" FontStyle="Normal" FontStretch="Normal" TextAlignment="Left">
        <Run FontWeight="Bold" Text="Now is the time for all good men to come to the aid of their country." />
    </Paragraph>
</RichTextBox>
````

The application will show text as shown below.

![SL app][1]

However in DOM Explorer all you see is this:

````XAML
<?xml version="1.0"?>
<richtextbox Name="richTextBox1" AutomationId="richTextBox1" Uid="16157963">
  <grid Name="RootElement" Uid="37840511">
    <border Name="Border" Uid="34030663">
      <border Name="MouseOverBorder" Uid="33607346">
        <scrollviewer Name="ContentElement" AutomationId="ContentElement" Uid="63386473">
          <border Uid="54749715">
            <grid Uid="35909463">
              <scrollcontentpresenter Name="ScrollContentPresenter" Uid="5020285">
                <richtextboxview BaseType="RichTextBoxView" Uid="22985394" />
              </scrollcontentpresenter>
              <rectangle Uid="26673201" />
              <scrollbar Name="VerticalScrollBar" AutomationId="VerticalScrollBar" Uid="45182569" />
              <scrollbar Name="HorizontalScrollBar" AutomationId="HorizontalScrollBar" Uid="3989940" />
            </grid>
          </border>
        </scrollviewer>
      </border>
    </border>
    <border Name="DisabledVisualElement" Uid="38732217" />
    <border Name="FocusVisualElement" Uid="13045638" />
  </grid>
</richtextbox>
````

Notice that there's no text in the DOM view, even though it is specified in the XAML and displayed in the application. We have to use code to fetch the XAML that the RichTextBox holds as data, then parse out the text buried in it. Here's an example:

````C#

  
  // Fetch the XAML property of the RichTextBox
  string rtbContents = (string)Pages.SilverlightAppTesting.SilverlightApp.RichTextBox1Richtextbox.GetProperty(new AutomationProperty("Xaml", typeof(string)));
  
  // Load it into an XmlDocument for easier parsing
  XmlDocument doc = new System.Xml.XmlDocument();
  doc.LoadXml(rtbContents);
  
  // Find all "Run" nodes as this is where the text is buried
  XmlNodeList runNodes = doc.GetElementsByTagName("Run");
  
  // Display the Text attribute of each run node
  foreach(XmlNode runNode in runNodes)
  {
      Log.WriteLine(runNode.Attributes["Text"].Value);
  }
````
````VB

  
  Dim rtbContents As String = DirectCast(Pages.SilverlightAppTesting.SilverlightApp.RichTextBox1Richtextbox.GetProperty(New AutomationProperty("Xaml", GetType(String))), String)
    
  Dim doc As XmlDocument = New System.Xml.XmlDocument()
  doc.LoadXml(rtbContents)
    
  Dim runNodes As XmlNodeList = doc.GetElementsByTagName("Run")
    
  For Each runNode As XmlNode In runNodes
      Log.WriteLine(runNode.Attributes("Text").Value)
  Next
````

Here's how to verify the text is bold:

````C#

  
  string rtbContents = (string)Pages.SilverlightAppTesting.SilverlightApp.RichTextBox1Richtextbox.GetProperty(new AutomationProperty("Xaml", typeof(string)));
  Log.WriteLine(rtbContents);
    
  // Load the RTB contents into an XElement for parsing
  XElement xElem = XElement.Parse(rtbContents);
  
  // Find the <Run node.
  XElement runElem = xElem.Descendants().First((e) => "Run".Equals(e.Name.LocalName));
  
  // Fetch the FontWeight attribute
  XAttribute attr = runElem.Attribute("FontWeight");
  Log.WriteLine(attr.Value);
  
  // Verify it is Bold
  Assert.AreEqual<string>("Bold", attr.Value);
````
````VB

  
  Dim rtbContents As String = DirectCast(Pages.SilverlightAppTesting.SilverlightApp.RichTextBox1Richtextbox.GetProperty(New AutomationProperty("Xaml", GetType(String))), String)
  Log.WriteLine(rtbContents)
    

  Dim xElem As XElement = XElement.Parse(rtbContents)
    

  Dim runElem As XElement = xElem.Descendants().First(Function(e) "Run".Equals(e.Name.LocalName))
    

  Dim attr As XAttribute = runElem.Attribute("FontWeight")
  Log.WriteLine(attr.Value)
    

  Assert.AreEqual(Of String)("Bold", attr.Value)
````

[1]: images/verify-text-in-rich-textbox/fig1.png
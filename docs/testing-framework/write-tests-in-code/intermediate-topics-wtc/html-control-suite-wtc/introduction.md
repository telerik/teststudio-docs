---
title: Introduction
page_title: Introduction to Testing Framework's HTML Control Suite
description: "Test Studio Testing Framework introducing the HTML Control Suite - what actions and verifications can be performed on the elements in coded tests. "
previous_url: /user-guide/write-tests-in-code/intermediate-topics/html-control-suite/introduction.aspx, /user-guide/write-tests-in-code/intermediate-topics/html-control-suite/introduction
position: 1
---
# Intro to Telerik Testing Framework's HTML Control Element Wrappers Suite

Telerik Framework includes an extensive suite of strongly typed HTML element wrappers that abstracts out actions and verifications of the controls contained on the webpage. With the classes contained in the control suite you can do things like:

**nextPageButton.Click()** instead of **Actions.Click(nextPageButton)**

or

**Assert.IsTrue(textBox.Text.Equals("foo"))** instead of **Assert.IsTrue(element.GetAttribute("value").Equals("foo"))**


In addition there are many other features that make the abstraction even more powerful. Here is a list off all the wrapper classes currently available along with the properties and methods they expose:

<table class="docs">
<tr>
	<th>HTML Control</th><th>Description</th><th>Properties</th><th>Methods</th><th>Base Class</th>
</tr>
<tr>
	<td>**HtmlAnchor**</td>
	<td>Wraps access to a HTML \<a> anchor element.</td>
	<td>HRef<br>
	Name<br>
	Target<br>
	Title</td>
	<td></td>
	<td><a href="#base">HtmlContainerControl</a></td>
</tr>
<tr>
	<td>**HtmlButton**</td>
	<td>Wraps access to a HTML \<button> element.</td>
	<td>Disabled
	Name<br>
	TabIndex<br>
	Valuee</td>
	<td></td>
	<td><a href="#base">HtmlContainerControl</a></td>
</tr>
<tr>
	<td>**HtmlDefinitionDescription**</td>
	<td>Wraps access to a HTML \<dd /> element . This control is used by the HtmlDefinitionList control.</td>
	<td>Description</td>
	<td></td>
	<td><a href="#base">HtmlContainerControl</a></td>
</tr>
<tr>
	<td>**HtmlDefinitionList**</td>
	<td>Wraps access to a HTML \<dl> element.</td>
	<td>Descriptions<br>
	Terms</td>
	<td></td>
	<td><a href="#base">HtmlContainerControl</a></td>
</tr>
<tr>
	<td>**HtmlDefinitionTerm**</td>
	<td>Wraps access to a HTML \<dt> element. This control is used by the HtmlDefinitionList control.</td>
	<td>Terms</td>
	<td></td>
	<td><a href="#base">HtmlContainerControl</a></td>
</tr>
<tr>
	<td>**HtmlDiv**</td>
	<td>Wraps access to a HTML \<div> container element.</td>
	<td></td>
	<td></td>
	<td><a href="#base">HtmlContainerControl</a></td>
</tr>
<tr>
	<td>**HtmlForm**</td>
	<td>Wraps access to a HTML \<form> element.</td>
	<td>EncType<br>
	Length<br>
	Name<br>
	Target</td>
	<td></td>
	<td><a href="#base">HtmlContainerControl</a></td>
</tr>
<tr>
	<td>**HtmlImage**</td>
	<td>Wraps access to a HTML \<image> element.</td>
	<td>Align<br>
	Alt<br>
	Border<br>
	Height<br>
	Src<br>
	Width</td>
	<td></td>
	<td><a href="#base">HtmlControl</a></td>
</tr>
<tr>
	<td>**HtmlInputButton**</td>
	<td>Wraps access to a HTML \<input type=button> element.</td>
	<td>Align<br>
	Alt<br>
	Border<br>
	Height<br>
	Src<br>
	Width</td>
	<td></td>
	<td><a href="#base">HtmlInputControl</a></td>
</tr>
<tr>
	<td>**HtmlInputCheckBox**</td>
	<td>Wraps access to a HTML \<input type=checkbox> element.</td>
	<td>Checked</td>
	<td>Check</td>
	<td><a href="#base">HtmlInputControl</a></td>
</tr>
<tr>
	<td>**HtmlInputFile**</td>
	<td>Wraps access to a HTML \<input type=file> element.</td>
	<td>FilePath</td>
	<td>Upload</td>
	<td><a href="#base">HtmlInputControl</a></td>
</tr>
<tr>
	<td>**HtmlInputHidden**</td>
	<td>Wraps access to a HTML \<input type=hidden> element.</td>
	<td></td>
	<td></td>
	<td><a href="#base">HtmlInputControl</a></td>
</tr>
<tr>
	<td>**HtmlInputImage**</td>
	<td>Wraps access to a HTML \<input type=image> element.</td>
	<td>Align<br>
	Alt<br>
	Border<br>
	Height<br>
	Src<br>
	Width</td>
	<td></td>
	<td><a href="#base">HtmlInputControl</a></td>
</tr>
<tr>
	<td>**HtmlInputPassword**</td>
	<td>Wraps access to a HTML \<input type=password> element.</td>
	<td>Disabled
	Size<br>
	TabIndex<br>
	Text</td>
	<td></td>
	<td><a href="#base">HtmlInputControl</a></td>
</tr>
<tr>
	<td>**HtmlInputRadioButton**</td>
	<td>Wraps access to a HTML \<input type=radio> element.</td>
	<td>Cheched</td>
	<td>Check</td>
	<td><a href="#base">HtmlInputControl</a></td>
</tr>
<tr>
	<td>**HtmlInputReset**</td>
	<td>Wraps access to a HTML \<input type=reset> element.</td>
	<td>Align<br>
	Alt<br>
	Border<br>
	Height<br>
	Src<br>
	Width</td>
	<td></td>
	<td><a href="#base">HtmlInputControl</a></td>
</tr>
<tr>
	<td>**HtmlInputSubmit**</td>
	<td>Wraps access to a HTML \<input type=submit> element.</td>
	<td>Align<br>
	Alt<br>
	Border<br>
	Height<br>
	Src<br>
	Width</td>
	<td></td>
	<td><a href="#base">HtmlInputControl</a></td>
</tr>
<tr>
	<td>**HtmlInputText**</td>
	<td>Wraps access to a HTML \<input type=text> element.</td>
	<td>Disabled<br>
	Size<br>
	TabIndex<br>
	Text</td>
	<td></td>
	<td><a href="#base">HtmlInputControl</a></td>
</tr>
<tr>
	<td>**HtmlListItem**</td>
	<td>Wraps access to a HTML \<li> element. This control is used by the HtmlOrdererList control and the HtmlUnorderedList control.</td>
	<td>GetItemOrder</td>
	<td></td>
	<td><a href="#base">HtmlContainerControl</a></td>
</tr>
<tr>
	<td>**HtmlOption**</td>
	<td>Wraps access to a HTML \<option> element which is a member of a select element.</td>
	<td>Selected<br>
	Text<br>
	Value</td>
	<td></td>
	<td><a href="#base">HtmlControl</a></td>
</tr>
<tr>
	<td>**HtmlOrderedList**</td>
	<td>Wraps access to a HTML \<ol>.</td>
	<td>AllItems<br>
	Itemst</td>
	<td></td>
	<td><a href="#base">HtmlContainerControl</a></td>
</tr>
<tr>
	<td>**HtmlSelect**</td>
	<td>Wraps access to a HTML \<select> list box or drop-down list element.</td>
	<td>Options<br>
	SelectedIndex<br>
	SelectedOption<br>
	this[]</td>
	<td>SelectByIndex<br>
	SelectByText<br>
	SelectByValue<br>
	SelectByPartialText<br>
	SelectByPartialValue<br>
	MultiSelect<br>
	MultiSelectByValue<br>
	MultiSelectByText</td>
	<td><a href="#base">HtmlContainerControl</a></td>
</tr>
<tr>
	<td>**HtmlSpan**</td>
	<td>Wraps access to a HTML \<span> inline text container element.</td>
	<td></td>
	<td></td>
	<td><a href="#base">HtmlContainerControl</a></td>
</tr>
<tr>
	<td>**HtmlTable**</td>
	<td>Wraps access to a HTML \<table> table element containing rows and columns.</td>
	<td>AllRows<br>
	BodyRows<br>
	Border<br>
	Caption<br>
	CellPadding<br>
	CellSpacing<br>
	ColumnCount<br>
	FootRows<br>
	HeadRows<br>
	Rows<br>
	this[]<br>
	Width</td>
	<td></td>
	<td><a href="#base">HtmlContainerControl</a></td>
</tr>
<tr>
	<td>**HtmlTableCell**</td>
	<td>Wraps access to a HTML \<td> table cell element.</td>
	<td>Align<br>
	BgColor<br>
	BorderColor<br>
	CellIndex<br>
	ColSpan<br>
	Height<br>
	RowSpan<br>
	Text<br>
	VAlign<br>
	Width/td>
	<td></td>
	<td><a href="#base">HtmlContainerControl</a></td>
</tr>
<tr>
	<td>**HtmlTableRow**</td>
	<td>Wraps access to a HTML \<tr> element.</td>
	<td>Align<br>
	BgColor<br>
	BorderColor<br>
	Cells<br>
	RowIndex<br>
	Text<br>
	this[]</td>
	<td></td>
	<td><a href="#base">HtmlContainerControl</a></td>
</tr>
<tr>
	<td>**HtmlTextArea**</td>
	<td>Wraps access to a HTML \<textArea> text input element.</td>
	<td>Cols<br>
	Rows<br>
	Text</td>
	<td></td>
	<td><a href="#base">HtmlContainerControl</a></td>
</tr>
<tr>
	<td>**HtmlUnorderedList**</td>
	<td>Wraps access to a HTML \<ul> element.</td>
	<td>AllItems<br>
	Items</td>
	<td></td>
	<td><a href="#base">HtmlContainerControl</a></td>
</tr>
<table>
*Table 1. List of HTML element control wrappers contained in Telerik Testing Framework's HTML control suite.*

Here is a list of the base classes along with the properties and methods they expose:

<table class="docs" id="base">
<tr>
	<th>Base Class</th><th>Description</th><th>Properties</th><th>Methods</th><th>Base Class</th>
</tr>
<tr>
	<td>**HtmlContainerControl**</td>
	<td>Base class for all wrapper controls that can contain other controls.</td>
	<td>Find<br>
	InnerText<br>	
	TextContent</td>
	<td></td>
	<td>HtmlControl</td>
</tr>
<tr>
	<td>**HtmlInputControl**</td>
	<td>Base class for all input wrapper controls.</td>
	<td>Name<br>
	Type<br>
	Value</td>
	<td></td>
	<td>HtmlControl</td>
</tr>
<tr>
	<td>**HtmlControl**</td>
	<td>Base class for the entire HTML wrapper control suite.</td>
	<td>Attributes<br>
	ChildNodes<br>
	ClientSideLocator<br>
	CssClass<br>
	Events<br>
	ID<br>
	ScrollLeft<br>
	ScrollTop<br>
	Styles<br>
	TagName<br>
	Wait</td>
	<td>AddEventListener<br>
	CallMethod<br>
	Capture<br>
	Click<br>
	Download<br>
	DragTo<br>
	DragToWindowLocation<br>
	GetComputedStyle<br>
	GetComputedStyleValue<br>
	GetRectangle<br>
	GetStyle<br>
	GetStyleValue<br>
	GetValue<br>
	InvokeEvent<br>
	IsVisible<br>
	MouseClick<br>
	MouseHover<br>
	Parent(T)<br>
	RemoveEventListener<br>
	ScrollToVisible<br>
	SetValue</td>
	<td>Control</td>
</tr>
<tr>
	<td>**Control**</td>
	<td>Root base class for all WebAii controls.</td>
	<td>BaseElement<br>
	IsRefresh<br>
	Locator<br>
	LocatorExpression<br>
	OwnerBrowser<br>
	Terms</td>
	<td>AssignElement<br>
	GetFamilyElement<br>
	MatchControl<br>
	Refresh</td>
	<td><a href="#" target="_blank">HtmlContainerControl</a></td>
</tr>
<table>
*Table 2. List of base classes used by Telerik Testing Framework's HTML control suite.*

Here is a list of the support classes that make it easier to use the rest of the HTML control suite:

<table class="docs">
<tr>
	<th>Base Class</th><th>Description</th><th>Properties</th><th>Methods</th><th>Base Class</th>
</tr>
<tr>
	<td>**HtmlFind**</td>
	<td>An extended Find class that includes HTML specific find methods.</td>
	<td>Table<br>
	TableCell<br>
	TableRowt</td>
	<td></td>
	<td>Find</td>
</tr>
<tr>
	<td>**HtmlStyle**</td>
	<td>Represents a single HtmlStyle. This object can be used to help probe and do validation against Html styles. Has functionality to convert unit styles to int values and color styles to System.Drawing.Color.</td>
	<td>Name<br>
	Value</td>
	<td>IsColor<br>
	IsInt<br>
	(static) IsSameColor<br>
	ToColor<br>
	(static) ToHtmlColor<br>
	ToInt</td>
	<td>Name<br>Value</td>
</tr>
<tr>
	<td>**HtmlWait**</td>
	<td>An extended Wait class that includes HTML specific wait methods.</td>
	<td></td>
	<td>ForCondition<br>
	ForExists<br>
	ForStyles<br>
	ForStylesNot<br>
	ForVisible<br>
	ForVisibleNot</td>
	<td>Wait</td>
</tr>
<table>
*Table 3. List of HtmlControl support classes contained in Telerik Testing Framework's HTML control suite.*

## Example of How to Fill Out a Web Form Using the HTML Element Wrapper Control Suite

Suppose we're automating a form to submit an auto classified ad. Here's how to write the code and take advantage of the HTML element wrapper suite:

```C#
[TestClass]
public class SubmitAdTestClass : BaseTest
{
    private const string TEST_PAGE_NAME = @"..\..\Pages\HTMLControls.htm";
  
    // Since we know the order of the input fields
    // we can use an enum to more easily reference them.
    enum TextInputFields
    {
        Model,
        Price,
        Phone,
        Email,
        FirstName,
        LastName,
        Company,
        Address,
        City,
        Zip,
        UserName,
    }
    // Same thing for the select drop downs
    enum Selects
    {
        Year,
        Make,
        AllowEmail,
        State
    }
  
    [TestMethod]
    [Description("Submits a used car classified ad")]
    public void SubmitAdTest()
    {
        Manager.LaunchNewBrowser();
        ActiveBrowser.NavigateTo("file:\\\\" + Path.Combine(TestContext.TestDir, TEST_PAGE_NAME));
   
        // Find all the required elements on the page
        HtmlForm form = Find.ById<HtmlForm>("Form2");
        IList<HtmlSelect> selectsList = form.Find.AllByTagName<HtmlSelect>("select");
        IList<HtmlInputText> textInputsList = form.Find.AllByTagName<HtmlInputText>("input");
        HtmlInputPassword passwordField = form.Find.ById<HtmlInputPassword>("txtPassword");
        HtmlTextArea description = form.Find.ById<HtmlTextArea>("txtDescription");
        HtmlInputSubmit submit = form.Find.ById<HtmlInputSubmit>("submit");
  
        // Enter data into the input fields
        Actions.ScrollToVisible(submit.BaseElement, ScrollToVisibleType.ElementBottomAtWindowBottom);
        selectsList[(int)Selects.Year].SelectByText("1956");
        selectsList[(int)Selects.Make].SelectByText("Ford");
        textInputsList[(int)TextInputFields.Model].Text = "T-Bird";
        textInputsList[(int)TextInputFields.Price].Text = "175000";
        textInputsList[(int)TextInputFields.Phone].Text = "555-122-5544";
        textInputsList[(int)TextInputFields.Email].Text = "test@myemail.com";
        selectsList[(int)Selects.AllowEmail].SelectByText("Yes");
        description.Text = "Beautifully restored two tone red & white classic T-Bird. Just like factory mint condition. Actual mileage is 175,600.";
        textInputsList[(int)TextInputFields.FirstName].Text = "Willard";
        textInputsList[(int)TextInputFields.LastName].Text = "Laird";
        textInputsList[(int)TextInputFields.Company].Text = "Laird Auto Restoration";
        textInputsList[(int)TextInputFields.Address].Text = "147 Industrial Dr.";
        textInputsList[(int)TextInputFields.City].Text = "Sacramento";
        selectsList[(int)Selects.State].SelectByText("California");
        textInputsList[(int)TextInputFields.Zip].Text = "22746";
        textInputsList[(int)TextInputFields.UserName].Text = "wlaird335";
        passwordField.Text = "lairdinc";
   
        // Submit the ad
        submit.Click();
    }
}
```
```VB
<TestClass()> _
 Public Class SubmitAdTestClass
    Inherits BaseTest
  
    Private Const TEST_PAGE_NAME As String = "..\..\Pages\HTMLControls.htm"
  
 
    Enum TextInputFields
        Model
        Price
        Phone
        Email
        FirstName
        LastName
        Company
        Address
        City
        Zip
        UserName
    End Enum
   
    
    Enum Selects
        Year
        Make
        AllowEmail
        State
    End Enum
  
    <TestMethod(), _
    Description("Submits a used car classified ad"), _
    DeploymentItem("Pages\\HTMLControls.htm"), _
    DeploymentItem("Pages\\Submitted.htm")> _
    Public Sub SubmitAdTest()
   
        Manager.LaunchNewBrowser()
        ActiveBrowser.NavigateTo("file:\\\\" + Path.Combine(TestContext.TestDir, TEST_PAGE_NAME))
  
        ' Find all the required elements on the page
        Dim form As HtmlForm = Find.ById(Of HtmlForm)("Form2")
        Dim selectsList As IList(Of HtmlSelect) = form.Find.AllByTagName(Of HtmlSelect)("select")
        Dim textInputsList As IList(Of HtmlInputText) = form.Find.AllByTagName(Of HtmlInputText)("input")
        Dim passwordField As HtmlInputPassword = form.Find.ById(Of HtmlInputPassword)("txtPassword")
        Dim description As HtmlTextArea = form.Find.ById(Of HtmlTextArea)("txtDescription")
        Dim submit As HtmlInputSubmit = form.Find.ById(Of HtmlInputSubmit)("submit")
  
        
        Actions.ScrollToVisible(submit.BaseElement, ScrollToVisibleType.ElementBottomAtWindowBottom)
        selectsList(Selects.Year).SelectByText("1956")
        selectsList(Selects.Make).SelectByText("Ford")
        textInputsList(TextInputFields.Model).Text = "T-Bird"
        textInputsList(TextInputFields.Price).Text = "175000"
        textInputsList(TextInputFields.Phone).Text = "555-122-5544"
        textInputsList(TextInputFields.Email).Text = "test@myemail.com"
        selectsList(Selects.AllowEmail).SelectByText("Yes")
        description.Text = "Beautifully restored two tone red & white classic T-Bird. Just like factory mint condition. Actual mileage is 175,600."
        textInputsList(TextInputFields.FirstName).Text = "Willard"
        textInputsList(TextInputFields.LastName).Text = "Laird"
        textInputsList(TextInputFields.Company).Text = "Laird Auto Restoration"
        textInputsList(TextInputFields.Address).Text = "147 Industrial Dr."
        textInputsList(TextInputFields.City).Text = "Sacramento"
        selectsList(Selects.State).SelectByText("California")
        textInputsList(TextInputFields.Zip).Text = "22746"
        textInputsList(TextInputFields.UserName).Text = "wlaird335"
        passwordField.Text = "lairdinc"
  
        
        submit.Click()
  
    End Sub
   
End Class
```


By taking advantage of the object oriented nature of the HTML element wrapper classes, our test code that fills in the fields and clicks the submit button is much simpler, more descriptive and more intuitive in nature. Note how simple it was to enter text into all the input fields, as well as make all the drop down selections using intuitive methods included with Telerik's HTML element wrapper classes!
Also notice how we're doing a nested find. The line **form.Find.AllByTagName<HtmlSelect>("select");** is returning all of the **\<select>** elements that are contained within the form "Form2" contained on the page, not the entire page itself which may contain other \<select> elements on the page, perhaps even on other forms contained on the same page.
 
One special feature to note about the **Find.AllByXXX<TControl>()** functions is that they filter on the type of the **TControl** such that the returned list only includes elements of type **TControl**. In the example above we're calling **Find.AllByTagName<HtmlInputText>("input")**. Due to the filtering being performed by the framework we only get back \<input type="text"> elements and not other input elements such as the \<input type="password"> element that is also on the form.
 
By the same token all of the Fi**nd.ByXXX<TControl>()** functions also verify that the found element is of type **TControl**. If, for example, you call **Find.ByTagIndex<HtmlInputPassword>("input", 4)** and the 5th \<input> element is not type="password" then the framework will throw a System.ArgumentException.

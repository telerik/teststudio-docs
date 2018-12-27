---
title: HtmlWait Class
page_title: HtmlWait Class | Test Studio Dev Documentation
description: HtmlWait Class
position: 2
---
#How to Use the HtmlWait Class#

The HtmlWait class extends and enhances the Element.Wait class with some powerful methods that are very useful with the HTML control suite. It adds:

* Wait for an HTML control to be visible or not visible.

* Wait for a style to be set to a specific value or to no longer be set to the value.

* Wait for a custom condition to be true or not true.
 
The HtmlWait.ForVisible and HtmlWait.ForVisibleNot use the HtmlControl.IsVisible function to test whether or not the element is currently visible in the browser. Since IsVisible follows the CSS chain, we get a true reading of whether or not the element actually is visible. For example:


#### __[C#]__

            {{region }}

    HtmlDiv div = Find.ByTagIndex<HtmlDiv>("div", 0);
    HtmlWait waitObj = div.Wait;
    
    // Wait 50 seconds (50000 milliseconds) for the div element to be visible.
    div.Wait.ForVisible(50000);
    // Wait 50 seconds (50000 milliseconds) for the div element to be invisible
    div.Wait.ForVisibleNot(50000);
    
    // The default timeout value is copied from Settings.Current.ExecuteCommandTimeout
    waitObj.Timeout = 1200000;        // Override the default value
    // Wait 120 seconds for the div to be visible
    waitObj.ForVisible();
    // Wait 120 seconds for the div to become invisible
    waitObj.ForVisibleNot();
    {{endregion}}

#### __[VB]__

          {{region }}

    HtmlDiv div = Find.ByTagIndex<HtmlDiv>("div", 0);
    HtmlWait waitObj = div.Wait;
    
    // Wait 50 seconds (50000 milliseconds) for the div element to be visible.
    div.Wait.ForVisible(50000);
    // Wait 50 seconds (50000 milliseconds) for the div element to be invisible
    div.Wait.ForVisibleNot(50000);
    
    // The default timeout value is copied from Settings.Current.ExecuteCommandTimeout
    waitObj.Timeout = 1200000;        // Override the default value
    // Wait 120 seconds for the div to be visible
    waitObj.ForVisible();
    // Wait 120 seconds for the div to become invisible
    waitObj.ForVisibleNot();
    {{endregion}}

Using the HtmlWait.ForStyles and HtmlWait.ForStylesNot methods you can wait for a particular style to be set or removed from the element. For example:

#### __[C#]__

          {{region }}
            
    HtmlSpan span = Find.ByTagIndex<HtmlSpan>("span", 0);
    HtmlWait spanWaitObj = div.Wait;
    
    // Wait for the background color and margin to be set.
    // Uses the default timeout value from Settings.Current.ExecuteCommandTimeout
    // This form uses GetComputedStyle, which means it follows the CSS chain.
    span.Wait.ForStyles("backgroundColor=red", "margin=30px");
    // Wait 30 seconds for the background color and margin to be set.
    span.Wait.ForStyles(30000, "backgroundColor=red", "margin=30px");
    // Wait for the computed style background color and margin to be set
    // instead of only examining the styles explicitly set on the element.
    // This method will follow the CSS chain up the element list to get
    // the currently active style of those specified in the parameters.
    span.Wait.ForStyles(true, "backgroundColor=red", "margin=30px");
    // Wait 30 seconds for the computed style background color and margin to be set
    // instead of only examining the styles explicitly set on the element.
    // This method will follow the CSS chain up the element list to get
    // the currently active style of those specified in the parameters.
    span.Wait.ForStyles(30000, true, "backgroundColor=red", "margin=30px");
    
    // The default timeout value is copied from Settings.Current.ExecuteCommandTimeout
    spanWaitObj.Timeout = 1200000;        // Override the default value
    // Wait 120 seconds for the background color and margin to be set.
    spanWaitObj.ForStyles("backgroundColor=red", "margin=30px");
    // Wait 120 seconds for for the background color and margin to not be set.
    spanWaitObj.ForStylesNot("backgroundColor=red", "margin=30px");
    
    // Wait for both the background color and margin to be not have the specified values.
    // Will continue to wait if either style is still set to the specified value.
    // Uses the default timeout value from Settings.Current.ExecuteCommandTimeout
    span.Wait.ForStylesNot("backgroundColor=red", "margin=30px");
    {{endregion}}
 

#### __[VB]__

          {{region }}

    Dim span As HtmlSpan = Find.ByTagIndex(Of HtmlSpan)("span", 0)
    Dim spanWaitObj As HtmlWait = div.Wait
    
    ' Wait for the background color and margin to be set.
    ' Uses the default timeout value from Settings.Current.ExecuteCommandTimeout
    ' This form uses GetComputedStyle, which means it follows the CSS chain.
    span.Wait.ForStyles("backgroundColor=red", "margin=30px")
    ' Wait 30 seconds for the background color and margin to be set.
    span.Wait.ForStyles(30000, "backgroundColor=red", "margin=30px")
    ' Wait for the computed style background color and margin to be set
    ' instead of only examining the styles explicitly set on the element.
    ' This method will follow the CSS chain up the element list to get
    ' the currently active style of those specified in the parameters.
    span.Wait.ForStyles(True, "backgroundColor=red", "margin=30px")
    ' Wait 30 seconds for the computed style background color and margin to be set
    ' instead of only examining the styles explicitly set on the element.
    ' This method will follow the CSS chain up the element list to get
    ' the currently active style of those specified in the parameters.
    span.Wait.ForStyles(30000, True, "backgroundColor=red", "margin=30px")
    
    ' The default timeout value is copied from Settings.Current.ExecuteCommandTimeout
    spanWaitObj.Timeout = 1200000        ' Override the default value
    ' Wait 120 seconds for the background color and margin to be set.
    spanWaitObj.ForStyles("backgroundColor=red", "margin=30px")
    ' Wait 120 seconds for for the background color and margin to not be set.
    spanWaitObj.ForStylesNot("backgroundColor=red", "margin=30px")
    
    ' Wait for both the background color and margin to be not have the specified values.
    ' Will continue to wait if either style is still set to the specified value.
    ' Uses the default timeout value from Settings.Current.ExecuteCommandTimeout
    span.Wait.ForStylesNot("backgroundColor=red", "margin=30px")
    {{endregion}}

The HtmlWait.ForCondition is an advanced method that calls a user defined function to determine whether or not the wait condition has been satisfied. You, the test automation programmer, may code up any sort of wait condition you can imagine. The only requirement is that your function must return true to indicate that the condition has been satisfied or return false to indicate the condition has not been satisfied.
 
The overloads of the HtmlWait.ForCondition are split into two virtually identical sets of three overloads. The first set operates on basic Element objects. The second set operates on Control objects, which all of the classes contained in the HTML control suite derive from. Except for this difference, they operate identically. The sample below shows only the Control version:

#### __[C#]__

          {{region }}

    HtmlTextArea textArea = Find.ByTagIndex<HtmlTextArea>("textarea", 0);
    HtmlWait textAreaWaitObj = textArea.Wait;
    // Wait 30 seconds for the HtmlTextArea element to contain the text "Now is the time"
    textArea.Wait.ForCondition(textAreaContainsStr, false, "Now is the time", 30000);
    {{endregion}}

#### __[VB]__

          {{region }}

    Dim textArea As HtmlTextArea = Find.ByTagIndex(Of HtmlTextArea)("textarea", 0)
    Dim textAreaWaitObj As HtmlWait = textArea.Wait
    ' Wait 30 seconds for the HtmlTextArea element to contain the text "Now is the time"
    textArea.Wait.ForCondition(AddressOf textAreaContainsStr, False, "Now is the time", 30000)
    {{endregion}}
    
Now we need the definition of the condition function 'textAreaContainsStr':

#### __[C#]__

          {{region }}

    /// <summary>
    /// Tests whether or not the HtmlTextArea element contains the specified string.
    /// </summary>
    /// <param name="ctl">The HtmlTextArea element to test. WebAii passes in the element currently being tested.</param>
    /// <param name="obj">The string to look for. This comes from the Object parameter of the ForCondition call and could contain anything.</param>
    /// <returns>True if the condition is satisfied, else False.</returns>
    public bool textAreaContainsStr(ArtOfTest.WebAii.Controls.Control ctl, Object obj)
    {
        // Do some basic parameter checking
        if (false == ctl is HtmlTextArea)
        {
            throw new ArgumentException("Passed in control is not a HtmlTextArea");
        }
        if (false == obj is string)
        {
            throw new ArgumentException("Pass in object is not a string");
        }
    
        HtmlTextArea textArea = (HtmlTextArea)ctl;
        return textArea.Text.Contains((string)obj);
    }
    {{endregion}}
 

#### __[VB]__

          {{region }}

    ''' <summary>
    ''' Tests whether or not the HtmlTextArea element contains the specified string.
    ''' </summary>
    ''' <param name="ctl">The HtmlTextArea element to test. WebAii passes in the element currently being tested.</param>
    ''' <param name="obj">The string to look for. This comes from the Object parameter of the ForCondition call and could contain anything.</param>
    ''' <returns>True if the condition is satisfied, else False.</returns>
    Public Function textAreaContainsStr(ByVal ctl As ArtOfTest.WebAii.Controls.Control, ByVal obj As Object) As Boolean
    
        ' Do some basic parameter checking
        If TypeOf ctl Is HtmlTextArea Then
            Throw New ArgumentException("Passed in control is not a HtmlTextArea")
        End If
        If TypeOf obj Is String Then
            Throw New ArgumentException("Pass in object is not a string")
        End If
    
        Dim textArea As HtmlTextArea = CType(ctl, HtmlTextArea)
        Return textArea.Text.Contains(CType(obj, String))
    
    End Function
    {{endregion}}

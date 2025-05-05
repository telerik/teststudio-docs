---
title: Data Driven Find Expressions in Code
page_title: Data Driven Find Expressions in Coded Step
description: "Data Driven Find Expressions in Test Studio test. Select different value from a drop down for each test run. Parameterize or data drive how an element in Test Studio test is found."
position: 1
---
# Data Driven Find Expressions in Coded Step 

*I need to data drive an element's find expression and use it to perform an action against or verify an element.*

> __Tip!__ <a href="/features/elements-explorer/find-element#data-driven" target="_blank">Data driven find expressions</a> is also available directly in elements Edit mode.

## The Scenario

The example below a page from the <a href="https://demos.telerik.com/aspnet-mvc/listbox" target="_blank">Telerik UI for ASP.NET MVC demo site</a>. 
 
1. Create a test and navigate to the demo page.
2. The ListBox on the left side holds a list of names under the _Employees_ list. 
3. Select a name and choose the button to move it on the right. 
4. The selected name is now moved to the right under the _Developers_ list. 
5. Do consecutive iterations for each of the names in the list on the left.

## The Solution

1. Create a test and <a href="/getting-started/first-test#start-a-recording-session" target="_blank">record the __Navigate__ step</a>.
   
2. Prepare the data table - for this example I use the internal data source and it looks like this.

    ![Data source](/img/advanced-topics/coded-samples/general/data-driven-find-expressions/data-source.png)

3. Explore the list of items and its structure using the <a href="/features/recorder/highlighting-menu/element-options#locate-in-dom" target="_blank">Advanced Recording Tools</a>.
   
    ![Highlight Items from list to explore](/img/advanced-topics/coded-samples/general/data-driven-find-expressions/explore-item-in-dom.png)

4. Based on the DOM tree the items from the list are identified as `ListItems` with specific `InnerText` property and `class=k-list-item`. These element's attributes are used when <a href="/testing-framework/write-tests-in-code/intermediate-topics-wtc/element-identification-wtc/finding-page-elements" target="_blank">defining the find expression for the element in code</a>. 
   
5. <a href="/automated-tests/coded-tests/coded-step" target="_blank">Create a coded step</a> in the test. 
   
6. Start the coded solution with <a href="/advanced-topics/coded-samples/general/attach-data-columns" target="_blank">getting the value from the data source</a> and store into a variable. 

7. Next use the value of that variable to define the string, which needs to be used in the find expression definition. 

8. Form the find expression definition and assert a matching element exists on the page. 
   
9.  Click the matching element. Complete coded step looks like this: 

    ```C#
    var dataIterVal = Data["EmplNames"];
            
    // Define a string which adds the value taken from data source as inner text for the find expression
    string defForFE = "InnerText="+dataIterVal.ToString();
    
    // Search for the list item element using find expression with the help of the defined string value           
    HtmlListItem nameToSelect = Find.ByExpression<HtmlListItem>("class=k-list-item", defForFE );
    Assert.IsNotNull(nameToSelect);
    
    // Click the corresponding item from list
    nameToSelect.MouseClick(ArtOfTest.WebAii.Core.MouseClickType.LeftClick, 0, 0, ArtOfTest.Common.OffsetReference.AbsoluteCenter);
    ```


10. Switch back to the test steps and record the click on the button to move the selected item on the right. With this the scenario is complete. 

    ![Recorded step to move the item on the right](/img/advanced-topics/coded-samples/general/data-driven-find-expressions/recorded-step-to-move-right.png)



---
title: Select Listbox Item by Text
page_title: Select Listbox Item by Text - Test Studio Dev Documentation
description: Select Listbox Item by Text
position: 2
---
# Select Listbox Item by Text in Silverlight

*I have a listbox contained in my Silverlight application. I want to be able to find and select an item contained in the listbox by its text, not by its index. I can't use select by index because the position of the item that needs to be selected may change at any time.*

## Solution

This is a tricky one to solve. There are two subtle problems that need to be dealt with before accomplishing the end goal:

1.Silverlight loves to virtualize data contained in data containers such as a listbox. This means the Silverlight visual tree only contains the data necessary to render the UI. Let's assume your list box shows 5 items at a time. Even though your list box may contain 100 items, the visual tree will only contain 6 or 7 items at a time in it. To further complicate this, after scrolling down so you can see items 50 to 55, the visual tree will only contain something like items 50 to 56, not 1 to 56.

2.The ScrollToVisible function doesn't scroll data containers, only the browser window. We'll have to come up with a different method of scrolling the list box.

The solution is to use this approach in a **loop**:

1. Scan what is currently in the Silverlight visual tree looking for the right item.

2.If not found, scroll the contents of the listbox down by one page of data and repeat the scan.

3.When the item is found, scroll it to the top of list box so we can reliably click on it to select it.

My sample Silverlight application to test contains this XAML code to render my listbox:

````XAML
<ListBox AutomationProperties.AutomationId="lb001" Height="117" HorizontalAlignment="Left" Margin="23,102,0,0" Name="listBox1" VerticalAlignment="Top" Width="281">
    <ListBoxItem Content="Item 1" />
    <ListBoxItem Content="Item 2" />
    <ListBoxItem Content="Item 3" />
    <ListBoxItem Content="Item 4" />
    <ListBoxItem Content="Item 5" />
    <ListBoxItem Content="Item 6" />
    <ListBoxItem Content="Item 7" />
    <ListBoxItem Content="Item 8" />
    <ListBoxItem Content="Item 9" />
    <ListBoxItem Content="Item 10" />
    <ListBoxItem Content="Item 11" />
    <ListBoxItem Content="Item 12" />
    <ListBoxItem Content="Item 13" />
    <ListBoxItem Content="Item 14" />
    <ListBoxItem Content="Item 15" />
    <ListBoxItem Content="Item 16" />
    <ListBoxItem Content="Item 17" />
    <ListBoxItem Content="Item 18" />
    <ListBoxItem Content="Item 19" />
    <ListBoxItem Content="Item 20" />
    <ListBoxItem Content="Item 21" />
    <ListBoxItem Content="Item 22" />
    <ListBoxItem Content="Item 23" />
    <ListBoxItem Content="Item 24" />
    <ListBoxItem Content="Item 25" />
    <ListBoxItem Content="Item 26" />
    <ListBoxItem Content="Item 27" />
    <ListBoxItem Content="Item 28" />
    <ListBoxItem Content="Item 29" />
    <ListBoxItem Content="Item 30" />
    <ListBoxItem Content="Item 31" />
    <ListBoxItem Content="Item 32" />
    <ListBoxItem Content="Item 33" />
    <ListBoxItem Content="Item 34" />
    <ListBoxItem Content="Item 35" />
    <ListBoxItem Content="Item 36" />
    <ListBoxItem Content="Item 37" />
    <ListBoxItem Content="Item 38" />
    <ListBoxItem Content="Item 39" />
    <ListBoxItem Content="Item 40" />
    <ListBoxItem Content="Item 41" />
    <ListBoxItem Content="Item 42" />
    <ListBoxItem Content="Item 43" />
    <ListBoxItem Content="Item 44" />
    <ListBoxItem Content="Item 45" />
    <ListBoxItem Content="Item 46" />
    <ListBoxItem Content="Item 47" />
    <ListBoxItem Content="Item 48" />
    <ListBoxItem Content="Item 49" />
    <ListBoxItem Content="Item 50" />
    <ListBoxItem Content="Item 51" />
    <ListBoxItem Content="Item 52" />
    <ListBoxItem Content="Item 53" />
    <ListBoxItem Content="Item 54" />
    <ListBoxItem Content="Item 55" />
    <ListBoxItem Content="Item 56" />
    <ListBoxItem Content="Item 57" />
    <ListBoxItem Content="Item 58" />
    <ListBoxItem Content="Item 59" />
</ListBox>
````

To help make the code necessary to accomplish our search task more modular, let's define a function that takes a listbox, a string to search for and finds and returns the listbox item want. Here is that function:

````C#
    private static ListBoxItem FindListboxItemByText
        (string itemToFind, ListBox myLB)
    {
        // We may have to scroll the list box to find the item we want, so get the scroll viewer attached to the listbox
        ScrollViewer scroller = myLB.Find.ByType<ScrollViewer>();
        IList<ListBoxItem> items;
        double scrollPos = 0;
    
        do
        {
            // Get all list box items currently contained in the visual tree
            items = myLB.Find.AllByType<ListBoxItem>();
    
            // Iterate through each list box item looking for the one we want
            for (int i = 0; i < items.Count; i++)
            {
                if (items[i].Text.Equals(itemToFind))
                {
                // We found the one we want. Scroll it to the top (in case it's outside the listbox's viewport) then return it to the caller.
                    scroller.InvokeMethod("ScrollToVerticalOffset", i);
                    return items[i];
                }
            }
    
            // We didn't find it, scroll down by a page worth of data to populate the VisualTree with the next page of data and try again.
            scrollPos += scroller.ViewportHeight;
            scroller.InvokeMethod("ScrollToVerticalOffset", scrollPos);
            myLB.Refresh(); // Refresh our cached copy of the listbox.
        }
        while (scrollPos <= scroller.ExtentHeight);
    
        // We scanned the entire list and didn't find the right item to select.
        return null;
    }
````

We call this resusable function from a coded step like this:


````C#
    [CodedStep("Select a listbox item by text")]
    public void SelectListItemByTextCodedStep()
    {
        string itemToFind = "Item 42";
    
        SilverlightApp app = ActiveBrowser.SilverlightApps()[0];
        ListBox myLB = app.Find.ByAutomationId<ListBox>("lb001");
    
        ListBoxItem item = FindListboxItemByText(itemToFind, myLB);
        Assert.IsNotNull(item, "\"" + itemToFind + "\" not found in the listbox.");
        item.User.Click();
    }
````
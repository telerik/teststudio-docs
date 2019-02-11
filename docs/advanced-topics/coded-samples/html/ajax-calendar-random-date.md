---
title: AJAX Calendar Random Date
page_title: AJAX Calendar Random Date
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
previous_url: /user-guide/code-samples/html/ajax-calendar-random-date-selection.aspx, /user-guide/code-samples/html/ajax-calendar-random-date-selection
position: 1
---
#AJAX Calendar - Random Date Selection#

*I would like to select a random date from an Ajax Calendar.*

##Solution##

The code below will show you how to select a random date from the Calendar on <a href="http://www.weekendesk.fr/week-end/4398/week-end-a-Courseulles-sur-Mer-Normandie-Week-ends_gourmands" target="_blank">this site</a>.

```C#
//We scroll to the date picker so that we can see the click occuring. //Pages.WeekEndCourseullesSurMer.WeekendFormFormTag is a definiton which Test Studio automatically generated.
Pages.WeekEndCourseullesSurMer.WeekendFormFormTag.ScrollToVisible(ScrollToVisibleType.ElementBottomAtWindowBottom);
              
//The Date Picker is actually an HTML List. We use the class name days to locate it.
HtmlUnorderedList calendar = Find.ByExpression<HtmlUnorderedList>(new HtmlFindExpression("class=days"));
              
//We initalize a collection to store all "available" dates from the calendar.
LinkedList<HtmlListItem> availableDates = new LinkedList<HtmlListItem>();
              
//Go through all the dates in the calendar. The dates are actually HTML List items.
foreach (HtmlListItem i in calendar.Items)
{
    //Green dates belong to class "promotion" while the purple one belongs to class "active".
    if (i.CssClass.Equals("promotion") || i.CssClass.Equals("active"))
    {
        //If the date checks out as "available" we add it to the list.
        availableDates.AddLast(i);
    }          
}
Random r = new Random();
              
//We generate a random number which will corespond to an item in our list.
int randomNum = r.Next(availableDates.Count);
              
//l will be the date we're going to select in the Calendar.
LinkedListNode<HtmlListItem> l = availableDates.First;
             
//This loop moves up the linked list until we reach the node that coresponds to our randomly generated number.
while (randomNum != 0)
{
    l = l.Next;
    randomNum--;
}
 
//Click on the node after we reach it in the list.
l.Value.MouseClick();
```
```VB
'We scroll to the date picker so that we can see the click occuring. //Pages.WeekEndCourseullesSurMer.WeekendFormFormTag is a definiton which Test Studio automatically generated.
Pages.WeekEndCourseullesSurMer.WeekendFormFormTag.ScrollToVisible(ScrollToVisibleType.ElementBottomAtWindowBottom)
 
'The Date Picker is actually an HTML List. We use the class name days to locate it.
Dim calendar As HtmlUnorderedList = Find.ByExpression(Of HtmlUnorderedList)(New HtmlFindExpression("class=days"))
 
'We initalize a collection to store all "available" dates from the calendar.
Dim availableDates As New LinkedList(Of HtmlListItem)()
 
'Go through all the dates in the calendar. The dates are actually HTML List items.
For Each i As HtmlListItem In calendar.Items
    'Green dates belong to class "promotion" while the purple one belongs to class "active".
    If i.CssClass.Equals("promotion") OrElse i.CssClass.Equals("active") Then
        'If the date checks out as "available" we add it to the list.
        availableDates.AddLast(i)
    End If
Next
Dim r As New Random()
 
'We generate a random number which will corespond to an item in our list.
Dim randomNum As Integer = r.[Next](availableDates.Count)
 
'l will be the date we're going to select in the Calendar.
Dim l As LinkedListNode(Of HtmlListItem) = availableDates.First
 
'This loop moves up the linked list until we reach the node that coresponds to our randomly generated number.
While randomNum <> 0
    l = l.[Next]
    randomNum -= 1
End While
 
'Click on the node after we reach it in the list.
l.Value.MouseClick()
```

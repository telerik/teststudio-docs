---
title: Custom HtmlControl
page_title: Custom HtmlControl
description: "Test Studio Testing Framework Custom HtmlControl - design CustomControl class in coded test to interact with custom components on the tested application."
position: 2
---
# Creating Your Own Custom HtmlControls

Let's suppose you're testing a web site that uses a third party or custom control. You can easily create your own custom HtmlControl class and then design tests that interact with the custom control via your custom HtmlControl class.
 
As an example, let's create a custom HtmlControl that wraps the ASP.NET calendar control. We'll give it some methods for reading and controlling the date selection along with a custom ClientSideLocator just for an example. First here's our ASPX web page containing a calendar control that we want to test

```
<% @ Page Language="C#" MasterPageFile="~/AppMaster.master" Title="Untitled Page" %>
<% @ Import Namespace="System.Data" %>
<% @ Register Assembly="ArtOfTest.WebAii.AspNet" Namespace="ArtOfTest.WebAii.AspNet.WebControls" TagPrefix="test" %>
<script runat="server">
     /// <summary>
     /// Page Load
     /// </summary>
     /// <param name="sender"></param>
     /// <param name="e"></param>
     protected void Page_Load(object sender, EventArgs e)
     {
           if (!Page.IsPostBack)
           {
                // Bind the grid and cache the data in the session.
                grid1.DataSource = GetData();
                DataBind();
           }
     }
     /// <summary>
     /// Return a DataSet of some random data.
     /// </summary>
     /// <returns>DataSet</returns>
     private DataSet GetData()
     {
          DataSet data = new DataSet();
          DataTable dt = new DataTable();
          Random r = new Random(3);
          data.Tables.Add(dt);
          dt.Columns.Add("ID", typeof(int));
          dt.Columns.Add("Date", typeof(DateTime));
          dt.Columns.Add("FirstName", typeof(string));
          dt.Columns.Add("LastName", typeof(string));
          dt.Columns.Add("Balance", typeof(int));
          for (int i = 0; i < 15; i++)
          {
               DataRow row = dt.NewRow();
               row.ItemArray = new object[] {i,DateTime.Today.AddDays(i),"Name" + i.ToString(),
                    "Last" + i.ToString(), r.Next(3000)};
               dt.Rows.Add(row);
          }
          return data;
     }
     /// <summary>
     /// OnCalendarSelectionChange()
     /// </summary>
     /// <param name="sender"></param>
     /// <param name="e"></param>
     protected void cal1_SelectionChanged(object sender, EventArgs e)
     {
          // Get DataSet from Session
          TimeSpan diffDate = cal1.SelectedDate.Subtract(DateTime.Today);
          if (cal1.SelectedDate >= DateTime.Today && diffDate.Days < 15)
          {
               grid1.SelectedIndex = diffDate.Days;
               grid1.EditIndex = diffDate.Days;
           }
           grid1.DataSource = GetData();
           grid1.DataBind();
     }
</script>
  
<asp:Content ID="Content1" ContentPlaceHolderID="PageContent" runat="Server">
     <!-- This Data Page Content -->
     <test:TestRegion ID="DataPageContent" runat='server'>
          You are logged in.
         <table style="border: dotted 1px black; background-color: beige; width:80%;" cellpadding="15">
              <tr>
              <td>
                   Select A Date:
                   <!-- The Calendar Control Region -->
                   <test:TestRegion ID="CalendarControl" runat="server">
                        <asp:Calendar ID="cal1" runat="server" OnSelectionChanged="cal1_SelectionChanged"
                             BackColor="#FFFFCC" BorderColor="#FFCC66" BorderWidth="1px" Font-Names="Verdana"
                             Font-Size="8pt" ForeColor="#663399" Height="200px" Width="220px" DayNameFormat="Shortest"
                             ShowGridLines="True">
                             <SelectedDayStyle BackColor="#CCCCFF" Font-Bold="True" />
                             <TodayDayStyle BackColor="#FFCC66" ForeColor="White" />
                             <OtherMonthDayStyle ForeColor="#CC9966" />
                             <NextPrevStyle Font-Size="9pt" ForeColor="#FFFFCC" />
                             <DayHeaderStyle Font-Bold="True" BackColor="#FFCC66" Height="1px" />
                             <TitleStyle BackColor="#990000" Font-Bold="True" Font-Size="9pt" ForeColor="#FFFFCC" />
                             <SelectorStyle BackColor="#FFCC66" />
                        </asp:Calendar>
                   </test:TestRegion>
                   <!-- The Calendar Control Region -->
              </td>
              <td valign="top" style="border: solid 1px black;">
                   Customer Balances:
                   <!-- The GridView Region -->
                   <test:TestRegion ID="GridControl" runat="server">
                        <asp:GridView ID="grid1" runat="server" AutoGenerateColumns="False" BackColor="White" 
                             BorderColor="#CC9966" BorderStyle="None" BorderWidth="1px" CellPadding="4" Font-Size="XX-Small">
                             <Columns>
                                  <asp:TemplateField HeaderText="ID">
                                       <ItemTemplate>
                                            <%# Eval("ID") %>
                                       </ItemTemplate>
                                       <EditItemTemplate>
                                            <!-- ID Column Region [Will persist only in Edit Mode] -->
                                            <test:TestRegion ID="GridEditId" runat="server">
                                                 <%# Eval("ID") %>
                                            </test:TestRegion>
                                            <!-- ID Column Region -->
                                       </EditTemplate>
                                  </asp:TemplateField>
                                  <asp:BoundField HeaderText="FirstName" DataField="FirstName" ReadOnly="true" />
                                  <asp:BoundField HeaderText="LastName" DataField="LastName" ReadOnly="true" />
                                  <asp:BoundField HeaderText="Date" DataField="Date" ReadOnly="true" />
                                  <asp:TemplateField HeaderText="Balance">
                                       <ItemTemplate>
                                            <%# Eval("Balance") %>
                                       </ItemTemplate>
                                       <EditItemTemplate>
                                            <!-- Balance Column Region [Will persist only in Edit Mode] -->
                                            <test:TestRegion ID="GridEditBalance" runat="server">
                                                 <asp:TextBox ID="newBalance" Text='<%# Eval("Balance") %>' runat="server"></asp:TextBox>
                                            </test:TestRegion>
                                            <!-- Balance Column Region -->
                                       </EditItemTemplate>
                                  </asp:TemplateField>
                             </Columns>
                             <FooterStyle BackColor="#FFFFCC" ForeColor="#330099" />
                             <RowStyle BackColor="White" ForeColor="#330099" />
                             <SelectedRowStyle BackColor="#FFCC66" Font-Bold="True" ForeColor="#663399" />
                             <PagerStyle BackColor="#FFFFCC" ForeColor="#330099" HorizontalAlign="Center" />
                             <HeaderStyle BackColor="#990000" Font-Bold="True" ForeColor="#FFFFCC" />
                        </asp:GridView>
                   </test:TestRegion>
                   <!-- The GridView Region -->
              </td>
              </tr>
         </table>
     </test:TestRegion>
     <!-- This Data Page Content -->
</asp:Content>
```

Let's put together our custom HtmlControl that we can use interact with an ASP.NET calendar control:


```C#
 public class AspNetCalendar : HtmlTable
       {
           /// <summary>
           /// Custom ClientSideLocator for demonstration purposes only.
           /// The framework calls this function as part of the JavaScript call when getting/setting
           /// values. Put any logic in here you want to select the element/object the framework
           /// should act upon. The framework prepends this string to the getvalue function.
           /// In this example asking to get the value of the color will equate to executing this JavaScript:
           /// document.getElementsByTagName('{table}')[0].color
           /// </summary>
           public override string ClientSideLocator
           {
               get
               {
                   return String.Formt("document.getElementsByTagName('{0}')[{1}]", this.TagName,  this.BaseElement.TagNameIndex);
               }
           }
   
           /// <summary>
           /// Gets the current year/month as a DateTime object.
           /// </summary>
           /// <returns>DateTime object with the calendars current year/month. Day will always be 1.</returns>
           public DateTime GetDate()
           {
                   HtmlTableCell cell = this.Rows[0].Cells[0];
                   HtmlTable headTable = cell.ChildNodes[0].As<HtmlTable>();
   
                   string MonthYear = headTable.Rows[0].Cells[1].InnerText;
   
                   DateTime date = DateTime.Parse(MonthYear);
                   return date;
           }
   
           /// <summary>
           /// Moves calendar to the specified year/month.
           /// </summary>
           /// <param name="TargetDate">The target year/month to move to.</param>
           public void GotoDate(DateTime TargetDate)
           {
               // Must strip out the day of month and time so we compare on the year/month only.
               DateTime CompareDate = new DateTime(TargetDate.Year, TargetDate.Month, 1);
               while (GetDate() < CompareDate)
               {
                   NextMonth();
               }
               while (GetDate() > CompareDate)
               {
                   PrevMonth();
               }
           }
   
           /// <summary>
           /// Moves calendar to the current year/month.
           /// </summary>
           public void GotoNow()
           {
               GotoDate(DateTime.Now);
           }
   
           /// <summary>
           /// Moves the calendar to the specified year/month and then clicks on the specified day.
           /// </summary>
           /// <param name="date">The target date to be clicked on.</param>
           public void ClickOnDate(DateTime date)
           {
               GotoDate(date);
               HtmlAnchor dayElem = this.Find.ByAttributes<HtmlAnchor>("title=" + date.ToString("MMMM dd"));
               dayElem.Click();
           }
   
           /// <summary>
           /// Gets the calendar's month value.
           /// </summary>
           /// <returns>Month as a string.</returns>
           public string GetMonth()
           {
               HtmlTableCell cell = this.Rows[0].Cells[0];
               HtmlTable headTable = cell.ChildNodes[0].As<HtmlTable>();
   
               string MonthYear = headTable.Rows[0].Cells[1].InnerText;
   
               string[] parts = MonthYear.Split(' ');
               // Always displayed as 'Mmm YYYY'
               return parts[0];
           }
   
           /// <summary>
           /// Gets the calendar's year value.
           /// </summary>
           /// <returns>Year as a string.</returns>
           public string GetYear()
           {
               HtmlTableCell cell = this.Rows[0].Cells[0];
               HtmlTable headTable = cell.ChildNodes[0].As<HtmlTable>();
   
               string MonthYear = headTable.Rows[0].Cells[1].InnerText;
               string[] parts = MonthYear.Split(' ');
               return parts[1];
           }
   
           /// <summary>
           /// Moves the calendar to the next month.
           /// </summary>
           /// <returns>The new month as a string.</returns>
           public string NextMonth()
           {
               HtmlAnchor nextMonthElem = this.Find.ByAttributes<HtmlAnchor>("title=Go to the next month");
   
               nextMonthElem.Click();
               this.OwnerBrowser.WaitUntilReady();
               this.Refresh();
   
               return GetMonth();
           }
   
           /// <summary>
           /// Moves the calendar to the previous month.
           /// </summary>
           /// <returns>The new month as a string.</returns>
           public string PrevMonth()
           {
               HtmlAnchor nextMonthElem = this.Find.ByAttributes<HtmlAnchor>("title=Go to the previous month");
   
               nextMonthElem.Click();
               this.OwnerBrowser.WaitUntilReady();
               this.Refresh();
   
               return GetMonth();
           }
       }
```
```VB
   Public Class AspNetCalendar
        Inherits HtmlTable
        ''' <summary>
        ''' Custom ClientSideLocator for demonstration purposes only.
        ''' The framework calls this function as part of the JavaScript call when getting/setting
        ''' values. Put any logic in here you want to select the element/object the framework
        ''' should act upon. The framework prepends this string to the getvalue function.
        ''' In this example asking to get the value of the color will equate to executing this JavaScript:
        ''' document.getElementsByTagName('{table}')[0].color
        ''' </summary>
        Public Overloads Overrides ReadOnly Property ClientSideLocator() As String
            Get
                Return [String].Format("document.getElementsByTagName('{0}')[{1}]", Me.TagName,  Me.BaseElement.TagNameIndex)
            End Get
        End Property

        ''' <summary>
        ''' Gets the current year/month as a DateTime object.
        ''' </summary>
        ''' <returns>DateTime object with the calendars current year/month. Day will always be 1.</returns>
        Public Function GetDate() As DateTime
            Dim cell As HtmlTableCell = Me.Rows(0).Cells(0)
            Dim headTable As HtmlTable = cell.ChildNodes(0).[As](Of HtmlTable)()

            Dim MonthYear As String = headTable.Rows(0).Cells(1).InnerText

            Dim [date] As DateTime = DateTime.Parse(MonthYear)
            Return [date]
        End Function

        ''' <summary>
        ''' Moves calendar to the specified year/month.
        ''' </summary>
        ''' <param name="TargetDate">The target year/month to move to.</param>
        Public Sub GotoDate(ByVal TargetDate As DateTime)
            ' Must strip out the day of month and time so we compare on the year/month only.
            Dim CompareDate As New DateTime(TargetDate.Year, TargetDate.Month, 1)
            While GetDate() < CompareDate
                NextMonth()
            End While
            While GetDate() > CompareDate
                PrevMonth()
            End While
        End Sub

        ''' <summary>
        ''' Moves calendar to the current year/month.
        ''' </summary>
        Public Sub GotoNow()
            GotoDate(DateTime.Now)
        End Sub

        ''' <summary>
        ''' Moves the calendar to the specified year/month and then clicks on the specified day.
        ''' </summary>
        ''' <param name="date">The target date to be clicked on.</param>
        Public Sub ClickOnDate(ByVal [date] As DateTime)
            GotoDate([date])
            Dim dayElem As HtmlAnchor = Me.Find.ByAttributes(Of HtmlAnchor)("title=" & [date].ToString("MMMM dd"))
            dayElem.Click()
        End Sub

        ''' <summary>
        ''' Gets the calendar's month value.
        ''' </summary>
        ''' <returns>Month as a string.</returns>
        Public Function GetMonth() As String
            Dim cell As HtmlTableCell = Me.Rows(0).Cells(0)
            Dim headTable As HtmlTable = cell.ChildNodes(0).[As](Of HtmlTable)()

            Dim MonthYear As String = headTable.Rows(0).Cells(1).InnerText

            Dim parts As String() = MonthYear.Split(" "c)
            ' Always displayed as 'Mmm YYYY'
            Return parts(0)
        End Function

        ''' <summary>
        ''' Gets the calendar's year value.
        ''' </summary>
        ''' <returns>Year as a string.</returns>
        Public Function GetYear() As String
            Dim cell As HtmlTableCell = Me.Rows(0).Cells(0)
            Dim headTable As HtmlTable = cell.ChildNodes(0).[As](Of HtmlTable)()

            Dim MonthYear As String = headTable.Rows(0).Cells(1).InnerText
            Dim parts As String() = MonthYear.Split(" "c)
            Return parts(1)
        End Function

        ''' <summary>
        ''' Moves the calendar to the next month.
        ''' </summary>
        ''' <returns>The new month as a string.</returns>
        Public Function NextMonth() As String
            Dim nextMonthElem As HtmlAnchor = Me.Find.ByAttributes(Of HtmlAnchor)("title=Go to the next month")

            nextMonthElem.Click()
            Me.OwnerBrowser.WaitUntilReady()
            Me.Refresh()

            Return GetMonth()
        End Function

        ''' <summary>
        ''' Moves the calendar to the previous month.
        ''' </summary>
        ''' <returns>The new month as a string.</returns>
        Public Function PrevMonth() As String
            Dim nextMonthElem As HtmlAnchor = Me.Find.ByAttributes(Of HtmlAnchor)("title=Go to the previous month")

            nextMonthElem.Click()
            Me.OwnerBrowser.WaitUntilReady()
            Me.Refresh()

            Return GetMonth()
        End Function
    End Class
```


Notice how we derive from an HtmlTable. That way we can take advantage of all the functionality already built into a standard table. We'll just add all the functions useful for our calendar control which include:

* NextMonth

* PrevMonth

* GetYear

* GetMonth

* GetDate

* GotoDate

* GotoNow

* ClickOnDate
 
All these functions are fairly straightforward Telerik Testing Framework code that don't really need explanation.
 
For the purposes of demonstration there's also a ClientSideLocator override in lines 201-207 so you can see how it works and how to implement it when you want to create a more complex custom control. For our HtmlControl extenders, you can make your HtmlControl map to any object on the client side. Previously an HtmlControl object had to map to element with an HTML tag. This restriction has been removed. You can override the HtmlControl "ClientSideLocator" property and give it any JavaScript find logic to execute on the client (e.g. in ASP.NET $find("foo") ) and the HtmlControl will map itself to that object on the client. Any future calls on this object using GetValue, SetValue or CallMethod, will use this JavaScript to select the right object on the client side before getting or setting it's value, or calling your custom method on it.


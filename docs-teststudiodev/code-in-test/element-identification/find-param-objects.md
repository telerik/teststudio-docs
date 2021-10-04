---
title: FindParam Objects
page_title: FindParam Objects | Test Studio Dev Documentation
description: FindParam Objects
position: 1
---
#FindParam Objects#

All the identification methods exposed by the 'Find' object described above use FindParam objects under the covers to describe the desired element within the DOM tree to Telerik's identification engine. The engine itself can only understand searches using FindParam's. You can directly invoke element searches against the identification engine using the Find.ByParam() or Find.AllByParam() methods. When FindParam's are used directly to define a search, they enable a richer, consistent and more flexible way to describe a certain element than just the Find.Byxx() which were designed to cater for the most common scenarios. For example, if you want to describe the second 'div' on a page with class=myclass. You can't directly do that using the Find.Byxx() methods unless you first find the second 'div' element then inspect its attributes to figure out if the class attribute is set 'myclass'. With FindParam objects, you can simply describe that search by:

#### __[C#]__

    {{region }}

    // The find object will only return an element if all conditions
    // exist. Else NULL.
    Element e = Find.ByParam(new FindParam("div", 1,"class=myclass"));
    Assert.IsNotNull(e);
    {{endregion}}

Here are some other examples:


#### __[C#]__

    {{region }}

    Element e;
      
    // Find.ById() is implemented as
    e = Find.ByParam(new FindParam("id=Button2"));
    Assert.IsNotNull(e);
      
    // Find an element with partial TextContent="Some Data" and has the 'src' attribute
    // containing a partial value = "foo.gif" and class attribute = "myClass"
    // Note: Don't have to set the ContentType here since by default it is TextContent
    e = Find.ByParam(new FindParam(FindType.Content, "p:Some Data", "title=~Div", "class=myClass"));
    Assert.IsNotNull(e);
      
    // Same as above but use InnerMarkup instead
    FindParam p = new FindParam(FindType.Content, "p:Some Data", "title=~Div", "class=myClass");
    p.ContentType = FindContentType.InnerMarkup;
    e = Find.ByParam(p);
    Assert.IsNotNull(e);
    {{endregion}}

##Chained Identification##

Chained identification is simply using multiple FindParam objects (as in a chain) to identify an element. Chained identification is used to help simplify locating nested and complex markup elements and promote a more robust approach for element identification in these scenarios.
 
Chained identification is executed by starting the identification process at the first element in the FindParam chain/array. When an element is identified using that parameter, that element is used as the reference element for the next parameter in the chain. The process continues until all parameters are used and the last element found will be returned as the result of this identification chain.
 
To help understand chained identification better, let's take a concrete example.
 
Many times developers find themselves struggling with a markup nesting similar to the one below; particularly on rich content websites when heavy styling is applied or when using dynamic web development technologies like ASP.NET. In the sample below, the outer table contains an id attribute but the rest of the nested tables don't. Let's assume a test needs to access the inner most table to verify its content. Instead of looking up the overall 'table' occurrence index over an entire document which can easily become difficult on large complex pages, we would like to first identify the "table1" element by its id and then simply count two table occurrences from it (occurrence index 1) to locate the inner table.

```HTML
<table id="table1">
   <tr>
     <td>
       <table>
         <tr>
           <td>
             <table>
               <tr>
                 <td>Data1</td>
               </tr>
               <tr>
                 <td>Data2</td>
               </tr>
               <tr>
                 <td>Data3</td>
               </tr>
             </table>
           </td>
         </tr>
       </table>
     </td>
     <td>
     </td>
   </tr>
</table>
```

Below is the chained identification code to accomplish that.


#### __[C#]__

    {{region }}

    // Generic chained identification
    FindParam idtable1 = new FindParam("id=table1");
      
    // The table1 tag index is 0
    FindParam innertable = new FindParam("table", 1);
      
    // Get the inner table.
    Element innerTable = Find.ByParam(new FindParam[] { idtable1, innertable });
    Assert.IsNotNull(innertable);
    Assert.AreEqual(3, innerTable.Children[0].Children.Count);
    {{endregion}}

##Defining FindParam Objects Outside Test Code (i.e. FindParam Serialization)##

FindParam objects support serialization including the FindParamCollection. This support allows you to define your FindParam's outside your test code and consume them as data sources. This enables you to be more agile when changes are made to your application by simply updating the xml that defines your FindParam objects. This topic is covered in more detail under <a href="/code-in-test/element-identification-wtc/find-param-as-xml-data" target="_blank">FindParams as External Xml DataSources</a>.

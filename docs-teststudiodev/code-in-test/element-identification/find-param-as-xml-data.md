---
title: FindParam as XML Data
page_title: FindParam as XML Data - Test Studio Dev Documentation
description: FindParam as XML Data
position: 1
---
# FindParams as External XML Data Sources

**Note:** This topics assumes a basic understanding of FindParam objects. It is recommended to read the <a href="/code-in-test/element-identification/finding-page-elements" target="_blank">Finding Page Elements</a> topic first before reading this topic.
 
FindParam's provide a consistent and streamlined approach to describing an element within a markup DOM. They also allow us to encapsulate all the information pertaining to how an element should be located on the page within one object.
 
The information FindParams contain is usually very specific to the web application's UI and DOM. If we desire to keep our test code logic abstract and independent from trivial UI changes that the application might undergo, we ought to keep this information stored in FindParams as abstracted and external to the test code as possible. With Telerik FindParam and FindParamCollection objects support XML Serialization. This feature allow us to extract out all information contained in FindParams or FindParamCollections to external Xml data sources and consume them when needed without having to hard code specific application information into our test logic:
 
By doing so we can:

* Avoid recompilation of test code each time UI/DOM changes are made. Given that the specifics of the web application are stored externally, we can simply edit these external sources to update any information regarding UI or DOM changes.

* Enable the same test logic/code to run against different versions of the same application that differ in UI layout or DOM structure. By versioning the external data sources per each different application version, we can configure our tests to consume different data source versions for each application being tested without having to duplicate test code and worry about maintaining multiple code bases. This approach can dramatically cut down maintenance and support costs especially for product teams that maintain and service multiple versions of the same application. It is also a great approach to take on if you are starting a new project and you think you will end up having to support multiple versions of that product in the future.
 
## Building FindParam Data Sources

We currently don't offer any UI design tools that can help build these data sources directly from your application. Therefore, to build these data source we need to craft our FindParams manually and then using FindParam and FindParamCollection XML serialization methods, store the generated sources to our storage medium of choice (i.e. database, file system ...etc).
The sample below shows an example of how to build an XML file that can be later consumed by your test code to identify elements to use in the automation logic.

````C#        
    // First we build the list of FindParam objects we want serialized
    // and add them to a FindParamCollection object.
    
    FindParam param1 = new FindParam("table", 0);
    FindParam param2 = new FindParam(FindType.Content, "p:test1", "class=mystyle");
    FindParam param3 = new FindParam("id=input1");
    
    // Now add each FindParam defined above to the FindParamCollection
    // and give it a key that you can use to access it with later on.
    FindParamCollection paramCol = new FindParamCollection();
    paramCol.Add("DataTable", param1);
    paramCol.Add("TargetDataCell", param2);
    paramCol.Add("InputTextBox", param3);
    
    // Now you can serialize this list to a string or a file 
    // you can store with the test code.
    paramCol.Save(@"C:\AppParams.xml");
    
    // Or you can serialize to a string to be stored
    // in your choice of storage medium.
    //
    // string serializedParams = paramCol.ToXml();
````

## Consuming the Data Sources

The are three different methods you can use to consume the data source generated above. We can deserialize the data back into a FindParamCollection object and then select one of these FindParams to locate a specific element on the page.

````C#    
    // Given we already have a datasource of FindParam's stored on a different medium,
    // we can deserialize the data back into a FindParamCollection object and then
    // select one of these FindParam's to locate a specific element on the page
    // like this:
    FindParamCollection paramCol = FindParamCollection.LoadFromFile(@"FindElementsFromFile.xml");
    
    // locate my input textbox
    Element inputText = ActiveBrowser.Find.ByParam(paramCol["InputTextBox"]);
    
    // Perform your automation actions on the element.
    ActiveBrowser.Actions.SetText(inputText, "sometext");
````

Alternatively we can can create a Dictionary lookup object from the external datasource.

````C#  
    // FindParams can be completely extracted out of test code and stored in an external xml file. 
    // 
    // This allows you to:
    // 1. Clean out your test code so that it purely contains the testing logic without it being
    //    cluttered with identification of elements.
    // 2. Update your automated tests due to website changes by simply updating the xml file 
    //    without a need to recompile your tests.
    // 3. Flexibility in segmenting and organizing your FindParams for your project. (i.e. an XML file
    //    that contains FindParams for certain versions of the website. Or XML file for each page of your site...etc)
    // 4. Store the FindParams in SQL or use DataSources to retrieve these files.
    //</summary>
    //
    
    // The SupportFiles\FindElementsFromFile.xml shows a sample xml file with two FindParams defined; one for
    // the MainTable and the other for ProgramsTable.
    IDictionary<string, Element> elements = Find.FromFile("FindElementsFromFile.xml");
    
    Assert.IsTrue(elements.Count == 2);
    Assert.IsTrue(elements["MainTable"].ElementType == ElementType.Table);
    Assert.IsTrue(elements["ProgramsTable"].ElementType == ElementType.Table);
    
    // Note:
    // 1. If you have the XML string stored in a DataBase, you can use the Find.FromXml() 
    //    to find these elements directly from the string.
````

Finally we can load the external datasource using a FindParamAttribute.

````C#    
    // The SupportFiles\FindElementsFromFile.xml shows a sample xml file with two FindParams defined; one for
    // the MainTable and the other for ProgramsTable.
    
    // Given that main table is already defined on the class, then I don't want the class FindParam attributes
    // included. In this case, I will explicitly call the Find.All(true). 
    // Otherwise, I wouldn't have needed to call Find.All() given that the Find.Elements["xx"] would make the call for me.
    Find.All(true);
    
    Assert.IsTrue(Find.Elements.Count == 2);
    Assert.IsTrue(Find.Elements["MainTable"].ElementType == ElementType.Table);
    Assert.IsTrue(Find.Elements["ProgramsTable"].ElementType == ElementType.Table);
````

## Managing and Organizing Data Sources for an Entire Application

There are probably many ways you can think of to organize your external data sources for your an entire application. We though want to discuss three approaches you might want to consider. You can organize your external sources:

* **Per Page**: With this approach you build a data source (i.e. an xml file) for each page within your application and then load it using the Find.FromXX() methods.

* **Per TestRegion**: With this approach you build a data source per each region defined within your application. You can then load and find your elements using the TestRegion.Find.FromXX() methods.

* **Per Entire Application**: With this approach you build one data source that represents your entire application. Many users might prefer this approach given that they only have to manage one file or data source for the entire application. Depending on the size of the application and how the application segments logically, this might or might not be good approach to take. If the application is huge, we recommend you break down your data source's into smaller ones. If your application is relatively small, then one datasource might be more efficient way to go.
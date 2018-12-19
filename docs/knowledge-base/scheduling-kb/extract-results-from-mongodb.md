---
title: Extract run results from MongoDB
page_title: Extract run results from MongoDB
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Extract run results from MongoDB

## Data Overview

The latest release of Test Studio introduces a new, more robust approach for storing results of remotely executed test lists. MongoDB is a non-relational, document database designed for ease of development, availability and scale (click <a href="https://docs.mongodb.org/manual/?_ga=1.138748659.1586265271.1432121010" target="_blank">here</a> for more info). It presents objects inside Test Studio as collections of documents of specific type, stored on disk. Each document is stored as a binary type-rich format of <a href="http://www.json.org/" target="_blank">json</a> - BSON.

MongoDB has its own specification for storing and retrieving files, which exceed the BSON limitation of 16MB. It’s called GridFS. Instead of storing a file in a single document, it divides a file into parts, or chunks, and stores each of those chunks as a regular MongoDB document.
A Test Studio document in the context of MongoDB data storage contains three components – _id, Metadata and Data. The _id field is a MongoDB-generated value which is indexed by the MongoDB engine for fast read access. The Metadata object has some document descriptive field, such as LastUpdate time, Schema, Deleted, etc. The Data object contains the actual data that describes the corresponding Test Studio object.

Test Studio keeps its objects in the following collections – projects, testlists, tests, testlistresults, results and GridFS (files and chunks). The Data object of each document contains the Test Studio Id of the respective object, represented as a GUID string.

- *projects* collection:
	
	* references to files, needed for the compilation process (resources, code files, external dependencies)
	* project-specific user settings
<br/>

- *testlists* collection:

	* TestList settings
	* collection of basic info for included Tests

- *tests* collection:

	* more thorough information of a single Test

- *testlistresults* collection:

	* references to the TestList and Project objects
	* top-level information of a TestList run – start/end time, pass/fail status, etc.

- *results* collection:

	* reference to the testlistresults collection (DispatchGroupId) that links to the top-level information for a single TestList run
	* reference to the TestList object
	* detailed information on a TestList run – single Test run result, collection of machines, on which the Tests were run, collections of configurations and counters (for performance TestLists), etc.

![diagram][1]

## MongoDB Query Guidelines

There are various tools for browsing and manipulating the data inside a MongoDB database. The mongo <a href="https://docs.mongodb.org/getting-started/shell/client/" target="_blank">shell</a> (<MongoDB_install_location>\mongo.exe) is an interactive JavaScript interface to MongoDB and is a component of the MongoDB package. You can use the shell to query and update data as well as perform administrative operations. Another tool for data query and manipulation is <a href="http://robomongo.org/" target="_blank">Robomongo</a> – a GUI shell-centric cross-platform MongoDB management tool.

### Sample MongoDB query

One way to dig into the Test Studio database, once some data has been aggregated as a result of remote TestList runs is to use the find() command in the interactive shell.

- Given a Project with an Id = { 00fd176b-750b-4f8a-9e19-d9c9881338c2}, one can search for all results of TestList runs for this project:

	* *db.getCollection('testlistresults').find({"Data.ProjectId":"00fd176b-750b-4f8a-9e19-d9c9881338c2"})*

> This will return a collection of ALL testlistresults documents for the given Project.

- You can drill down into the results collection to get more details of a specific TestList run, e.g. TestList Id = { de09bd95-aa3c-4a88-8d73-1e7a2aad730f }:

	* *db.getCollection('results').find({"Data.__value.TestListId":"de09bd95-aa3c-4a88-8d73-1e7a2aad730f"})*

> This way you’ll get all results documents for the selected TestList.

- Once you have the testlists collection results for a certain Project, you can get the detailed TestList run results from the results collection: 

	* *db.getCollection('results').find({"Data.__value.DispatchGroupId":"9ba18968-1d37-44fa-baad-29f0ce7b8c3b"})*

You can find more general info on the querying the MongoDB database on the MongoDB docs pages - <a href="https://docs.mongodb.org/getting-started/shell/query/" target="_blank">here</a>.


[1]: /img/knowledge-base/scheduling-kb/extract-results-from-mongodb/fig1.png
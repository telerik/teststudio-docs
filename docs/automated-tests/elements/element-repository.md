---
title: Element Repository
page_title: Element Repository
description: Element repository in Test Studio. How elements are stored within a single Test Studio test. What is the Pages.g.cs/Pages.g.vb file? Do I need to merge the Pages.g.cs/Pages.g.vb file created by different developers? How is the Element Repository used during test execution 
position: 3
---
# Element Repository 

**...and what happens when two developers are working in the same test project at the same time?**

To fully understand what the Element Repository is and how it works, we need to start with a discussion on how elements are stored within a single test. __Each test file keeps a definition of all the elements used by that particular test's steps.__ Each regular (non-coded) test step maintains a definition of the element(s) with which it interacts. By "definition" it's meant its friendly name (the name that is displayed in the <a href="/automated-tests/elements/overview" target="_blank">Elements Explorer pane</a>) and the <a href="/automated-tests/elements/elements-find-expression" target="_blank">Find Expression</a> that is used to locate the element on the web page during test execution.

When you convert a regular test step into a coded step, the element definitions are changed into what is called an "external reference." This means the element definitions still reside within the test, but they are no longer tied to a specific test step. Similarly, if you use the <a href="/features/recorder/advanced-recording-tools/dom-explorer" target="_blank">DOM Explorer</a>, select an element, and then select "Add to Project Elements," that element is added to the currently active test as an "external reference".

When a test project is loaded, all the elements from all tests are merged into the Element Repository, which then gets displayed in the <a href="/automated-tests/elements/overview" target="_blank">Elements Explorer pane</a>. It is important to know that this Element Repository is nothing more than an in-memory collection of all the elements based on the current tests content in the project. The repository, as a single collection, and is not persisted to disk. It relies on the individual element definitions that are persisted with each test. During this merge process, any duplicate elements (i.e. the same element according to their Find Expressions) that are used by more than one test are merged and displayed as only one element in the Elements Explorer pane. Under the covers, the Element Repository knows which tests each element is used by.

With this approach there should be no problem having two people working on the same test project at the same time. As soon as person two gets the latest files from the source control repository and reloads the test project, the elements from any newly created tests will automatically get merged into the Element Repository for person two.

### What is the Pages.g.cs/vb file? Do I need to merge the Pages.g.cs/vb file created by different developers? ###

The Pages.g.cs file (or Pages.g.vb file in VB test projects) is normally a hidden file. It is automatically generated by Test Studio and is only used by coded test steps. Test Studio generates this file from the elements contained in the element repository, which are displayed in the Elements Explorer.

You do not, and should not ever change its contents. Any changes you try to make will be lost when Test Studio automatically regenerates this file. It is regenerated:

* When the test project is loaded by Test Studio.

* When you add elements, such as when you record new test steps.

* When you delete elements, such as when you delete a test step or an entire test.

* When the test project is built on your local development box or on a build server.

Since this file is automatically generated, it should not be checked into your source control repository. Test Studio does all the work to generate and maintain this file for you.

### How is the Element Repository used during test execution? ###

When you look at the elements being displayed in the Elements Explorer pane, you will see them in a tree structure. At the root is the web page from which they were recorded. Under that may be a Frame node if the element was contained on the source page that an \<iframe> element references, and/or a Silverlight node if it was recorded from a Silverlight application.

During test execution, the root Page node is not actually used to locate the element. The execution engine only uses the Frame, Silverlight nodes, and the element's Find Expression to locate the correct element to interact with during any test step. This allows the test to continue to work when you need to test in a different testing environment (e.g. a Development server, then a Staging server, then a Production server).

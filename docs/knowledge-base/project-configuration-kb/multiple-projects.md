---
title: Multiple Projects
page_title: Multiple Projects
description: Reusing tests and Helper methods across multiple projects. When multiple projects use the same or similar resources, you may wish to share or integrate these project resources. Here we address four scenarios - Sharing helper methods (standalone code file) between projects, sharing data sources between projects, and importing tests from other projects.
position: 1
---
#Multiple Projects#

When multiple projects use the same or similar resources, you may wish to share or integrate these project resources. Here we address four scenarios: Sharing helper methods between projects, sharing data sources between projects, and importing tests from other projects.

##Sharing Helper Methods Between Projects##

If your projcts use common methods, you may wish to place them in a custom DLL. You can then add references to this utility class in your different projects in <a href="/advanced-topics/coded-samples/general/utility-class-in-standalone" target="_blank">Standalone Test Studio</a> or the <a href="/advanced-topics/coded-samples/general/use-external-dll-in-vs" target="_blank">Visual Studio Plugin</a>.

##Sharing Data Sources Between Projects##

Generally, <a href="/features/data-driven-testing/bind-test-data-source" target="_blank">data sources</a> must be in the same project folder as the tests bound to them. Test Studio creates a copy of the target data source for this purpose, so that after data binding, changes to the original data source do not automatically affect the data source for the test. 

A <a href="/features/data-driven-testing/sql-database-example" target="_blank">SQL database</a>, however, behaves differently: any test configured to connect to a SQL database as a data source will retrieve up-to-date data from that database. So, any number of projects can data bind to the same SQL database and access the same data.

##Importing Tests from Another Project##

All Test Studio projects are file-based. To import tests from one project to another, you can copy the test files (.tstest) from those projects into the target project. Next, manually <a href="/troubleshooting-guide/test-execution-problems-tg/pages-not-defined" target="_blank">update the namespace</a> for any copied code-behind files. Test Studio will automatically detect this new test on restart or Project view refresh. 
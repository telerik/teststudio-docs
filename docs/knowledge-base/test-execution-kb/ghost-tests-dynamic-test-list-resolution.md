---
title: Resolving Ghost Tests in Dynamic Test Lists
description: Learn how to address the issue of ghost tests appearing in Dynamic Test Lists in Progress® Telerik® Test Studio® when using Scheduling.
type: how-to
page_title: Fixing Issues with Ghost Tests in Dynamic Test Lists in Test Studio
slug: ghost-tests-dynamic-test-list-resolution
tags: test-studio,scheduling,dynamic-test-list,mongodb,storage-database
res_type: kb
ticketid: 1686593
---


## Description

When running a Dynamic Test List in Progress® Telerik® Test Studio® via <a href="/automated-tests/scheduling/overview" target="_blank">Scheduling</a>, you may encounter a situation where tests that no longer exist in the local project are executed. These ghost tests may appear because the MongoDB storage database retains files even after they have been deleted from the local project. This issue can cause test failures and discrepancies between the local project and the tests executed remotely.

This knowledge base article also answers the following questions:
- How to remove ghost tests from a Dynamic Test List in Test Studio?
- Why are deleted tests still running in Test Studio Scheduling?
- How to clean up the MongoDB storage database for Test Studio?

## Solution

To resolve this issue, follow one of the approaches below:

### Approach 1: Using MongoDB Compass to Delete Specific Tests

1. Download MongoDB Compass from their <a href="https://www.mongodb.com/try/download/compass" target="_blank">official download page</a>.
2. Connect MongoDB Compass to your Test Studio storage database using the instructions <a href="https://www.mongodb.com/docs/compass/current/connect/" target="_blank">here</a>.
3. Navigate to the `tests` collection in the MongoDB database.
4. Search for and locate the document corresponding to the ghost test using the guidelines <a href="https://www.mongodb.com/docs/compass/current/documents/#manage-documents" target="_blank">here</a>.
5. Delete the identified document to remove the ghost test.

### Approach 2: Use Static Test Lists or Refine Filters

- Replace the Dynamic Test List with a Static Test List if applicable. Static lists do not rely on filters and will contain only the tests explicitly added.
- Modify the filters for the Dynamic Test List to ensure they are more precise and exclude unintended tests.

### Approach 3: Drop the Entire Storage Database

1. Follow the steps outlined <a href="/knowledge-base/scheduling-kb/drop-storage-database" target="_blank">to drop the entire MongoDB storage database</a>.
2. After dropping the database, use <a href="/automated-tests/scheduling/upload-latest-files" target="_blank">the `Upload` button</a> in Test Studio to upload the current state of your project to the Storage database.


> __Note!__ 
> <br>
> Dropping the entire database also __deletes all existing test results__. If you need __to keep the results from previous runs__, consider dropping specific collections only using the instructions <a href="/knowledge-base/scheduling-kb/drop-storage-database#drop-single-collections-from-database" target="_blank">here</a>.

## See Also

- [MongoDB Compass Documentation](https://www.mongodb.com/docs/compass/current/)
- [Dropping the Storage Database](/knowledge-base/scheduling-kb/drop-storage-database)
- [Dynamic Test Lists Overview](/automated-tests/test-lists/test-lists-standalone#dynamic-test-lists)
- [Scheduling Setup in Test Studio](/automated-tests/scheduling/overview)

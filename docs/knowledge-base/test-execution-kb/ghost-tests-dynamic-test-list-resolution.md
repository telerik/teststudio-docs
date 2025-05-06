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

When running a Dynamic Test List in Progress® Telerik® Test Studio® via Scheduling, you may encounter a situation where tests that no longer exist in the local project are executed. These ghost tests may appear because the MongoDB storage database retains files even after they have been deleted from the local project. This issue can cause test failures and discrepancies between the local project and the tests executed remotely.

This knowledge base article also answers the following questions:
- How to remove ghost tests from a Dynamic Test List in Test Studio?
- Why are deleted tests still running in Test Studio Scheduling?
- How to clean up the MongoDB storage database for Test Studio?

## Solution

To resolve this issue, follow one of the approaches below:

### Approach 1: Using MongoDB Compass to Delete Specific Tests

1. Download MongoDB Compass from [their official download page](https://www.mongodb.com/try/download/compass).
2. Connect MongoDB Compass to your Test Studio storage database using the instructions [here](https://www.mongodb.com/docs/compass/current/connect/).
3. Navigate to the `tests` collection in the MongoDB database.
4. Search for and locate the document corresponding to the ghost test using the guidelines [here](https://www.mongodb.com/docs/compass/current/documents/#manage-documents).
5. Delete the identified document to remove the ghost test.

### Approach 2: Use Static Test Lists or Refine Filters

- Replace the Dynamic Test List with a Static Test List if applicable. Static lists do not rely on filters and will contain only the tests explicitly added.
- Modify the filters for the Dynamic Test List to ensure they are more precise and exclude unintended tests.

### Approach 3: Drop the Entire Storage Database

1. Follow the steps outlined [here](https://docs.telerik.com/teststudio/knowledge-base/scheduling-kb/drop-storage-database) to drop the entire MongoDB storage database.
2. After dropping the database, use the "Upload to Storage" button in Test Studio to upload the current state of your project.
3. Note that dropping the database will also delete all existing test results. If you need to retain results, consider dropping specific collections only using the instructions [here](https://docs.telerik.com/teststudio/knowledge-base/scheduling-kb/drop-storage-database#drop-single-collections-from-database).

## See Also

- [MongoDB Compass Documentation](https://www.mongodb.com/docs/compass/current/)
- [Dropping the Storage Database](https://docs.telerik.com/teststudio/knowledge-base/scheduling-kb/drop-storage-database)
- [Dynamic Test Lists Overview](https://docs.telerik.com/teststudio/features/test-lists/dynamic-test-lists/overview)
- [Scheduling Setup in Test Studio](https://docs.telerik.com/teststudio/features/scheduling/overview)

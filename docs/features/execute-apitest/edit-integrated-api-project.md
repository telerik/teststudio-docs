---
title: Edit Tests in Integrated API Project
page_title: Edit Tests in Integrated API Project
description: "Edit API Tests in the Integrated API Project in Test Studio Web project. Modify the insereted API test In a Test Studio web test"
position: 1
---
# Edit Tests in Integrated API Project

The _Create Test/ Edit API Project_ button opens the nested API project under the Test Studio currently active one.

![Edit API project][3]

If this is an empty project proceed with <a href="https://docs.telerik.com/teststudio-apis/features/steps/overview" target="_blank">creating new API tests</a>.

If an existing test is added ensure all external dependencies are manually included. 

## Add Manually the Necessary External References in Nested API project

### Project Level Variables

Any <a href="https://docs.telerik.com/teststudio-apis/features/variables" target="_blank">project level variables</a> in the previously created API project are not related to any of the tests. Having that said, such variables need to be defined again in the nested in Test Studio project.

### Attachments

The <a href="https://docs.telerik.com/teststudio-apis/features/steps/http-request" target="_blank">HTTP request step</a> allows you to attach files to the request body if _form-data_ format is used. If the existing test had such an attachemnt it need to be added manually in the nested in Test Studio project.

### Standalone Code File

If the imported API test uses any functions from a <a href="https://docs.telerik.com/teststudio-apis/features/code-features/code-items" target="_blank">code item</a> in the original project, that one needs to be manually added to the nested in Test Studio project.

If the imported API test has a <a href="https://docs.telerik.com/teststudio-apis/features/code-features/code-behind-files" target="_blank">code-behind file</a> it will be automatically imported as it is associated with the test itself. 

### Referenced Assemblies

If the existing project refers to any <a href="https://docs.telerik.com/teststudio-apis/features/code-features/add-assembly-reference" target="_blank">external assemblies</a> these need to be manually included in the nested in Test Studio project.

[3]: /img/features/execute-apitest/add-api-test-as-step/create-edit.png
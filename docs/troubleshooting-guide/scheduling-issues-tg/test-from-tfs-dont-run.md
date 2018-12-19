---
title: Test from TFS Doesn't Run
page_title: Test from TFS Doesn't Run
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Test from TFS Doesn't Run


## PROBLEM

A scheduled test list with Get Latest from TFS enabled does not run. 

## SOLUTION 1

The first time a project is opened from TFS it is mapped to a local directory. A relative common scenario is to change the remote project location in TFS which will not be reflected in the local copy of the project. Thus when trying to execute a test list using 'Get Latest' option the project could not be found in the previous remote location. As a result no tests execution starts and the following exception is logged in the <a href="/troubleshooting-guide/troubleshooting-tools-tg/using-the-application-log" target="_blank">application log</a>:

```
[date time,Telerik.TestStudio.ExecutionManagerService.exe(6336:125),Execution] FileReaderWriterSync.ReadFileAsync() : EXCEPTION! (see below)
     Outer Exception Type: System.IO.DirectoryNotFoundException
     Message: Could not find a part of the path 'C:\Users\[User Name]\AppData\Local\Temp\Projects\[GUID]\TestLists\My Test List.aiilist'.
     HRESULT: 0x80070003 (Official ID (if app.) = 2147942403, Error Bit = FAILED, Facility = FACILITY_WIN32, Code = ERROR_PATH_NOT_FOUND)
     Call Stack:
          at System.IO.__Error.WinIOError(Int32 errorCode, String maybeFullPath)
          at System.IO.FileStream.Init(String path, FileMode mode, FileAccess access, Int32 rights, Boolean useRights, FileShare share, Int32 bufferSize, FileOptions options, SECURITY_ATTRIBUTES secAttrs, String msgPath, Boolean bFromProxy, Boolean useLongPath, Boolean checkHost)
          at System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share)
          at Telerik.TestStudio.Shared.Storage.Local.FileReaderWriterSync.<ReadFileAsync>d__1.MoveNext()
```

The remote path in TFS for each source control enabled project is stored in the Settings.aiis file and could be changed only manually. The value of "RemotePath" setting in Test Studio project settings file (Settings.aiis) must be updated with the actual TFS project location. For your reference bellow is listed part of a sample Settings.aiis file showing the "RemotePath" setting:

```
    ...
    "SourceControlRepository": {
      "__type": "ArtOfTest.Common.TFSClient.TFSRepositoryInfo",
      "__value": {
        "RemotePath": "$/WebUI_Test_Studio/[Location]/[ProjectName]",
        "ServerType": 1,
        "ServerInfo": {
          "__type": "ArtOfTest.Common.TFSClient.TFSServerInfo",
          "__value": {
            "ServerName": "http://tfsserver.samplecompany.it:portNumber/"
          }
        }
      }
    },
    ...
```


## SOLUTION 2

> Note: Since product version **R2 2017 SP1** such library dependency problem will not be present

-  If the execution machine does not have the necessary TFS components installed, Test Studio cannot log on to TFS to check out the test project. If this is the problem, the following error will appear in the Execution Server application log: 

**Could not load file or assembly 'Microsoft.TeamFoundation.Client'**

In this case you should install Team Explorer 2013 or earlier on the execution machine. It is accessible for download trough a MSDN account.

 To resolve this behavior, ensure that Team Foundation Client is installed on the Scheduling Server and Execution Server machines.

- This behavior may also be caused by the Execution Server using a service account that cannot log on to the TFS repository. Ensure that the Execution Server is setup with the <a href="/features/scheduling-test-runs/change-service-account" target="_blank">correct service account</a>.


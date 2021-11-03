---
title: Docker Container Testing
page_title: Use Docker Container for Test Execution
description: "Docker container testing is with Test Studio. Execute tests in a Docker container. Headless test execution in Docker container."
position: 7
---
# Docker Container Testing with Test Studio

Test Studio test lists can be executed in Headless mode with a Docker container. Read below how to prepare the environment and how to start testing in a Docker container.

## Environmental Prerequisites

The prerequisites from Test Studio and Docker side are listed below. Make sure that you comply with them, before proceeding with the next steps.

* Docker container can run on a physical or virtual machine with Windows installed. 
* Installed Docker on the machine, where tests will be executed.
* Active <a href="/test-studio-editions#test-studio-run-time-add-on" target="_blank">Test Studio Run-Time</a> license and .msi installer for it. The minimum version of Test Studio is 2021 R3.

## Disclaimer

Executing tests in a Docker container has its specifics and limitations. It is better to know about them before you proceed.

* Tests in a Docker container can be executed only in Headless mode, because the container does not have UI. This is the <a href="/automated-tests/headless/headless-test-execution" target="_blank">Chrome Headless browser type</a> in Test Studio. 
* Element's <a href="/automated-tests/elements/find-element-by-image" target="_blank">image find logic</a> does not work in a Docker container.
* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/image-verification" target="_blank">Image verification step</a> fails, when the test is executed in a Docker container.
* <a href="/features/recorder/advanced-recording-tools/element-steps/verifications/text-from-image" target="_blank">Text from image verification step (OCR)</a> fails, when the test is executed in a Docker container.

## Install Docker

Download Docker from the <a href="https://www.docker.com/get-started" target="_blank">official website</a>. Then, follow the instructions and install it on the machine that will be used for executing tests. 

You can refer to the <a href="https://docs.docker.com/get-started/" target="_blank">Docker documentation</a> for commands and questions related with that software.

## Setup Docker Container for Testing

Below are listed the steps to setup a Docker container for testing.

1.&nbsp;Switch Docker to use Windows containers, instead of the default Linux containers. Once you switch it successfully, the option will show as "Switch to Linux containers...", meaning that the current state is Windows containers.
![Switch to Windows containers][1]

2.&nbsp;Pull the <a href="https://hub.docker.com/_/microsoft-windows" target="_blank">official Microsoft Windows Docker image</a> from the Docker Hub. Use the command that is provided in the Docker Hub and make sure to specify the exact built to be pulled. The build must match the Windows build on the current machine.

```
//For Windows build 20H2, use the following command
docker pull mcr.microsoft.com/windows:20H2
```

> Note
> <br>
> The Microsoft Windows image does not support "latest" tag. Please check the documentation on the <a href="https://hub.docker.com/_/microsoft-windows" target="_blank">image's page</a>.

3.&nbsp;Create a container from the offical Microsoft Windows image. To do that, go to **Images** in the Docker desktop application and click on the **Run** button. 
![Create a container][2]

Then, expand the Optional Settings and specify **Host Path** and **Container Path**. The **Host Path** is a folder on the machine, which is available to the Docker container and the **Container Path** is how you will reference this resources from the **Host Path** within the container.
![Optional settings][3]

4.&nbsp;Copy the .msi installer of Test Studio Run-Time and Chrome Enterprise in the **Host Path** folder. They will become available in the **Container Path** in the Docker container and are ready to be installed. Open the Command Line Interface (CLI) of the container and navigate to the **Container Path** folder. 
![Open CLI][4]

Install both Test Studio Run-Time and Chrome browser enterprise edition in passive mode, because there is no UI in the container and active installation can not complete. You can use the following command, but make sure that each installer is finished without errors before you proceed with the next.

```
msiexec.exe /i msiInstallerFileName.msi /passive /le c:\tools\errorLogForThisInstaller.txt
```

> Note
> <br>
> Additional information about the msiexec can be found in the <a href="https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/msiexec" target="_blank">Microsoft documentation</a>.

## Execute Tests

> Note
> <br>
> You can execute test lists only in Headless mode in the Docker container. 

After completing the above steps in this article, the next thing that you need to do is to copy the tests and test lists that you want to execute. Place them in the **Host Path** folder and they will also show in the **Container Path** folder in the Docker container. 

Open the container's Command Line Interface (CLI) and use the <a href="/features/test-runners/artoftest-runner" target="_blank">ArtOfTest.Runner.exe</a> to start the execution. This test runner provide multiple options for execution and output, which are all exaplined in the linked documentation. For example, you can use the commands below to start test list execution.

```
//navigate to the Test Studio installation folder
ArtOfTest.Runner.exe /list="full path to the test list file with extension .aiilist"
```

You can apply specific settings for Docker container test list execution, like the browser type. Since the test list execution is only in Headless mode, you can provide different <a href="/features/test-runners/artoftest-runner#settings-option" target="_blank">settings file to the ArtOfTest.Runner.exe</a>. This means that you don't have to change the <a href="/features/test-lists/test-list-settings" target="_blank">Test List Settings</a> on your original test list and still execute it in Headless mode in the container.


[1]: /img/advanced-topics/build-server/docker-container-testing/fig1.png
[2]: /img/advanced-topics/build-server/docker-container-testing/fig2.png
[3]: /img/advanced-topics/build-server/docker-container-testing/fig3.png
[4]: /img/advanced-topics/build-server/docker-container-testing/fig4.png
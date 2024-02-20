---
title: Connect a Project via Reverse Proxy Server
page_title: Configure a Test Studio Project for Remote Execution via Reverse Proxy Server
description: "Connect the Test Studio project to the configured Scheduling Server via a preconfigured Reverse Proxy server."
position: 0
---
# Connect a Project via Reverse Proxy Server

The setup allows you to connect a project to a Scheduling server hosted in a network behind a Reverse Proxy server. 

## Prerequisites

To configure this specific setup you need to have the following in advance: 

- A ready to use <a href="/automated-tests/scheduling/overview" target="_blank">Scheduling setup</a>. It can be configured for a single machine, or for a multi machine configuration. 

- Dedicated certificates issued for the communication between the Test Studio standalone application and reverse proxy machine. As an example you can check the steps listed <a href="/knowledge-base/scheduling-kb/configure-reverse-proxy#create-certificates" target="_blank">here to create self-signed Root CA, Server and Client certificates</a>.

- A reverse proxy server configured to use TLS and enabled client certificate authentication. You can find <a href="/knowledge-base/scheduling-kb/configure-reverse-proxy#reverse-proxy-configuration" target="_blank">here an example on configuring a nginx server for Windows</a>. 

## Connect the Project to Schedule Test Lists on Remote Execution Machines via Reverse Proxy

Open the Test Studio project on the machine which connects the Scheduling setup via the reverse proxy. Click the **Connect** button from the `Scheduling` ribbon in the **Project** tab.

![Connect][1]

In the **Scheduling Server Settings** dialog, choose **Reverse Proxy (Advanced)** radio button to connect the project to the configured Scheduling server hosted behind the proxy. 

![Reverse proxy connect][1a]

### Communication Key 

The __Communication Key__ lets you import the key generated in the Scheduling Config wizard. The text field remains empty to keep safe the value of the key in use. To indicate a key is in use ensure the **Loaded** status is present.

![Reverse proxy connect-communication key][2a]

>**Tip**
><br> 
><br> In case the communication key is not matching, you need to import the current key in use. Check <a href="/knowledge-base/scheduling-kb/generate-communication-key#generate-new-key" target="_blank">here how to generate a new key and import it for all Scheduling components</a>. 

### Client Certificate 

The __Client Certificate__ lets you insert the client certificate issued for the client machine. Ensure to install the certificate *.PFX on the client machine and add it to the certificate store. Then, the client certificate is stored in the __Current User Personal Certificate Store__. Use the <a href="https://learn.microsoft.com/en-us/dotnet/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate" target="_blank">certificate thumbprint</a> to import it. 

![Reverse proxy connect- certificate][2b]

>**Tip**
><br> 
><br> Check <a href="/knowledge-base/scheduling-kb/configure-reverse-proxy#create-certificates" target="_blank">here an example for issuing self-signed certificates to use for the Reverse Proxy configuration</a>.


The text field remains empty to keep safe the thumbprint of the certificate in use. To indicate a certificate is in use ensure the **Loaded** status is present.

### Reverse Proxy Server Name

Enter the machine name for the machine which hosts the reverse proxy server and the port on which it is configured (the example uses 9009), then click **Connect**.

![Run via proxy][2]

>**Tip**
><br> 
><br> Check <a href="//knowledge-base/scheduling-kb/configure-reverse-proxy#reverse-proxy-configuration" target="_blank">here an example for setting up a Reverse Proxy configuration using nginx for Windows</a>.

There's a confirmation message when the connection is successful. 

![Connection successful message][3a]

## Confirm Connection 

Once the connection is successfully established, click the **Confirm** button to apply the changes in the project. 

![Confirm Reverse proxy connection][3]


[1]: /img/features/scheduling-test-runs/remote-run-all-in-one/fig4.png
[1a]: /img/features/scheduling-test-runs/connect-via-proxy/fig1a.png
[2]: /img/features/scheduling-test-runs/connect-via-proxy/fig2.png
[2a]: /img/features/scheduling-test-runs/connect-via-proxy/fig2a.png
[2b]: /img/features/scheduling-test-runs/connect-via-proxy/fig2b.png
[3a]: /img/features/scheduling-test-runs/connect-via-proxy/fig3a.png
[3]: /img/features/scheduling-test-runs/connect-via-proxy/fig3.png


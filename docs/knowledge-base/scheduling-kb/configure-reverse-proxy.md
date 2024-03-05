---
title: Configure Reverse Proxy Server
page_title: Example Configuration for Reverse Proxy Server
description: Example Configuration for Reverse Proxy Server to use for connecting to the Test Studio Scheduling setup. 
position: 2
---
# Reverse Proxy Server

Test Studio Standalone application allows connection to Scheduling setup configured behind a pre-configured reverse proxy using client and server certificates. The reverse proxy have to use TLS and to have client certificate authentication enabled.

This article guides you through creating the custom certificates and certificate authority and an example configuration of a Windows nginx reverse proxy. 

* [Create Certificates](#create-certificates) 
* [Configure Reverse Proxy Server](#reverse-proxy-configuration)

## Create Certificates 

For this example we use _openssl_ to create self-signed Trusted Root CA, Server and Client certificates. You can use _openssl_ from within Git Bash if you have Git for Windows installed. 

> Using self-signed certificates needs to comply with company policies in place. 

An alternative is to use your own trusted certificates. 

### Create CA Certificate

Use the following commands to issue the Custom Authority certificate: 

1. Enter the following command in the console: 
```openssl genrsa -aes256 -out ts-CA-key.pem -passout pass:"1234" 2048```

where you need to replace _1234_ with a suitable password. 

2. Enter the following command in the console: 
```openssl req -passin pass:"1234" -x509 -sha256 -new -nodes -key ts-CA-key.pem -days 3650 -out ts-CA-cert.pem```

where you need to add the information for which you get prompted. This includes `Common Name` and for the purpose of this example we use __Test Studio CA__ as Common Name

### Create Server Certificate

Follow the steps below:

1. Enter the following command in the console: 
```openssl genrsa -aes256 -out ts-server.key -passout pass:"1234" 2048```

where you need to replace _1234_ with a suitable password.

2. Enter the following command in the console: 
```openssl req -passin pass:"1234" -new -key ts-server.key -out ts-server.csr```

where you need add the information for which you get prompted. This includes `Common Name` and we recommend using the proxy machine domain name. For the purpose of this example we use __ProxyMachineName__ as Common Name.

3. Create a _ts-server.ext_ file with the following content:

	```
	authorityKeyIdentifier=keyid,issuer
	basicConstraints=CA:FALSE
	keyUsage = digitalSignature, nonRepudiation, keyEncipherment, dataEncipherment
	subjectAltName = @alt_names

	[alt_names]
	DNS.0 = ProxyMachineName
	DNS.1 = ProxyMachineName.companyDomain.com
	IP.0 = xxx.xxx.xx.x
	```

	where DNS.0 and DNS.1 hold the machine host name and the full qualified domain name for the machine which hosts the proxy server. IP.0 is the IP address of the proxy server machine in the network from which it will be accessed remotely. 

4. Enter the following command in the console:
```openssl x509 -passin pass:"1234" -req -in ts-server.csr -CA ts-CA-cert.pem -CAkey ts-CA-key.pem -CAcreateserial -out ts-server.crt -days 1825 -sha256 -extfile ts-server.ext```

5. Create a _ts-server.pass_ file which contains the pass phrase for _ts-server.key_. This is _1234_ for this example. 

### Create Client Certificate

1. Enter the following command in the console: 
```openssl genrsa -aes256 -out ts-client.key -passout pass:"1234" 2048```

where you need to replace _1234_ with a suitable password.

2. Enter the following command in the console: 
```openssl req -passin pass:"1234" -new -key ts-client.key -out ts-client.csr```

where you need add the information for which you get prompted. This includes `Common Name` and we recommend using the machine domain name. For the purpose of this example we use __ProxyMachineName__ as Common Name.

3. Create a _ts-client.ext_ file with the following content: 

	```
	authorityKeyIdentifier=keyid,issuer
	subjectKeyIdentifier = hash
	basicConstraints=CA:FALSE
	nsCertType = client, email
	nsComment = "Test Studio Client Certificate"
	keyUsage = digitalSignature, nonRepudiation, keyEncipherment, dataEncipherment
	extendedKeyUsage = clientAuth, emailProtection
	subjectAltName = @alt_names

	[alt_names]
	DNS.0 = ProxyMachineName
	DNS.1 = ProxyMachineName.companyDomain.com
	IP.0 = xxx.xxx.xx.x
	```
where DNS.0 and DNS.1 hold the machine host name and the full qualified domain name for the machine which hosts the proxy server. IP.0 is the IP address of the proxy server machine in the network from which it will be accessed remotely. 

4. Enter the following command in the console: 
```openssl x509 -passin pass:"1234" -req -in ts-client.csr -CA ts-CA-cert.pem -CAkey ts-CA-key.pem -CAcreateserial -out ts-client.crt -days 1825 -sha256 -extfile ts-client.ext```

5. Enter the following command in the console: 
```cat ts-client.key ts-client.crt ts-CA-cert.pem > ts-client.pem```

6. Enter the following command in the console: 
```openssl pkcs12 -passin pass:"1234" -export -out ts-client.pfx -inkey ts-client.key -in ts-client.pem -certfile ts-CA-cert.pem -passout pass:"1234"```

where you need to replace _1234_ with a suitable password.

7. Copy the issued *.PFX file to the client machine where Test Studio uses the proxy server to connect to the Scheduling setup - following the steps of this example outputs a file named _ts-client.PFX_. The install option is in the right mouse button context menu. Once triggered choose to import the certificate for  __Current User__ store and follow the wizard steps. 

>**Note**
><br> 
><br>Installing the client certificate adds the issued CA certificate in the __Trusted Root CA__ store and the client certificate in the __Personal__ Store both under __Current User__ certificates. 



## Reverse Proxy Configuration

For this example we use nginx for Windows. As an alternative you can use any type of reverse proxy configuration 

1. Install <a href="https://nginx.org/en/docs/windows.html" target="_blank">nginx for Windows</a>

2. Configure nginx by changing the contents of the nginx.conf file located in the conf folder. Be sure to __replace "c:/ts-certs/" with the folder where your CA and Server certificates are located__.

	```
	#user  nobody;
	worker_processes  1;

	pid        logs/nginx.pid;

	events {
		worker_connections  1024;
	}

	http {
		include       mime.types;
		default_type  application/octet-stream;

		# Enable large body size due to application specifics
		client_max_body_size 0;

		keepalive_timeout  65;

		# Add server certificate to enable TLS
		# Replace the folder location with the one where you store the certificates
		ssl_certificate      c:/ts-certs/Server/ts-server.crt;
		ssl_certificate_key  c:/ts-certs/Server/ts-server.key;
		ssl_password_file	c:/ts-certs/Server/ts-server.pass;

		# Enable client certificate verification and specify the CA certificate used to issue the client certificate 
		# Replace the folder location with the one where you store the certificates
		ssl_verify_client on;	
		ssl_client_certificate c:/ts-certs/CA/ts-CA-cert.pem;

		# HTTPS server
		# Ensure to keep the headers exactly as listed in the example below
		server {
			listen       9009 ssl default_server;
			server_name  localhost;

			#ssl_session_cache    shared:SSL:1m;
			#ssl_session_timeout  5m;

			ssl_ciphers  HIGH:!aNULL:!MD5;
			ssl_prefer_server_ciphers  on;
			
			# Proxy calls to Test Studio Scheduling service
			# This configuration is meant for the setup when Scheduling service and Proxy server are on the same machine
			# If the proxy server is separate machine, replace localhost with the Scheduling machine host name

			location / {
				proxy_pass http://localhost:8009;
				proxy_pass_request_headers      on;
				proxy_set_header TS-Original-Request-Uri $scheme://$host:$server_port$request_uri;	
			}
			
			# Proxy calls to Test Studio Storage service
			# This configuration is meant for the setup when Scheduling service and Proxy server are on the same machine
			# If the proxy server is separate machine, replace localhost with the Scheduling machine host name

			location /v1 {
				proxy_pass http://localhost:8492;
				proxy_pass_request_headers      on;
				proxy_set_header TS-Original-Request-Uri $scheme://$host:$server_port$request_uri;
			}
			
			# Proxy calls to Test Studio Executive Dashboard service
			# This configuration is meant for the setup when Scheduling service and Proxy server are on the same machine
			# If the proxy server is separate machine, replace localhost with the Scheduling machine host name
			# Executive Dashboard can be then accessed on address https://proxyMachineName:9009/ed

			location /ed/ {
				proxy_pass http://localhost:8085/;
				proxy_pass_request_headers      on;
				
				sub_filter_types application/javascript;
				sub_filter 'href="/'  'href="/ed/';
				sub_filter 'src="/'  'src="/ed/';
				sub_filter '/assets/'  '/ed/assets/';
				sub_filter '+"/api"'  '+"/ed/api"';
				sub_filter_once off;
			}
			
			# Proxy call to test studio runner. Important this endpoint should use this convention /runner/{machineName}
			# Substitute {machineName} with the name of the machine where the runner is located
			#  All Execution machines need to be listed as below with their host names

			location /runner/{machineName}/ {
				proxy_pass http://localhost:55555/;
				proxy_pass_request_headers      on;
				proxy_set_header TS-Original-Request-Uri $scheme://$host:$server_port$request_uri;
			}
		}
	}
	```

3. Start nginx by navigating to its folder in cmd window and run __"start nginx"__. You can reload the server via __"nginx -s reload"__ or stop it with __"nginx -s quit"__.
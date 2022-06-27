---
id: "how-to-self-host-groupdocs-signature-cloud-with-docker"
url: "signature/how-to-self-host-groupdocs-signature-cloud-with-docker"
title: "How to self-host GroupDocs.Signature Cloud with Docker"
productName: "GroupDocs.Signature Cloud"
description: ""
keywords: ""
---

## Overview ##

[Docker](https://docs.docker.com/get-started/overview/) is an open platform that effectively solves three main tasks development, deployment, and running the applications. With Docker, you can isolate your applications from the infrastructure that simplifies software development and delivery. The main building blocs are images and containers. The image includes everything you need to run the application: code or binaries, runtimes dependencies, file system. The container is an isolated process with additional features that you can interact with. The use of containers to deploy applications is called *containerization*.

[Docker Hub](https://hub.docker.com/) is a repository or library of the container images where you can share and find images.

## Self-hosting ##

The GroupDocs.Signature Cloud Container Image available at [https://hub.docker.com/r/groupdocs/signature-cloud](https://hub.docker.com/r/groupdocs/signature-cloud) and enables users to self-host GroupDocs.Signature Cloud.

To run the GroupDocs.Signature Cloud in Docker the Docker itself should be installed on your machine.

### Install Docker ###

Check [Get Started](https://www.docker.com/get-started) section for Docker installation for your platform. After you installed and started Docker on your local machine we can run the container.

*NOTE: When running Docker on Windows make sure to switch to Linux containers by clicking on Docker icon in the tray and selecting "Switch to Linux containers..." (see [https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers) for more details.)*

### Run Container ###

Before running the container you can create two optional folders with files to process and custom fonts that we'll be mounted and available to GroupDocs.Signature Cloud service when we start the container.

To run GroupDocs.Signature Cloud in Docker type one of the following commands:

*NOTE: In case you don't have license keys you can omit LICENSE_PUBLIC_KEY and LICENSE_PRIVATE_KEY parameters. Without license GroupDocs.Signature Cloud will work in evaluation mode.*

{{< tabs tabTotal="2" tabID="1" tabName1="Windows (PowerShell)" tabName2="Linux (bash)" >}} {{< tab tabNum="1" >}}

```javascript

docker run `
    -p 8080:80 `
    -v "${pwd}/data:/data" `
    -e "LICENSE_PUBLIC_KEY#public_key" `
    -e "LICENSE_PRIVATE_KEY#private_key" `
    --name signature_cloud `
    groupdocs/signature-cloud

```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript

docker run \
    -p 8080:80 \
    -v $(pwd)/data:/data \
    -e LICENSE_PUBLIC_KEY#public_key \
    -e LICENSE_PRIVATE_KEY#private_key \
    --name signature_cloud \
    groupdocs/signature-cloud

```

{{< /tab >}} {{< /tabs >}}

The Docker would download GroupDocs.Signature Cloud image from Docker Hub and start a container. While downloading the image the output similar to shown on screenshot would be printed to the console:

*NOTE: I'm running Docker on Windows and will be using PowerShell to run the commands but the experience would be the same in case you're on Linux.*

After the container is started you'll see the following messages that indicate that GroupDocs.Signature Cloud service up and running.

![screenshot](signature/images/1596699080320-548.png)

Now you can work with GroupDocs.Signature Cloud which is hosted on your machine.

### Health-check ###

When the container and GroupDocs.Signature Cloud started you can check service status by calling GET [http:~~/~~/localhost:8080/](http://localhost:8080/). The successful response status (200) will indicate that the service is up and running.

{{< tabs tabTotal="2" tabID="2" tabName1="Windows (PowerShell)" tabName2="Linux (bash)" >}} {{< tab tabNum="1" >}}

```javascript

Invoke-WebRequest -Uri http://localhost:8080/

```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript

curl -i http://localhost:8080/

```

{{< /tab >}} {{< /tabs >}}

At the following screenshot, I'm calling [http:~~/~~/localhost:8080/](http://localhost:8080/) in a separate Powershell window and response indicates that service is alive:

![screenshot](signature/images/health_check.png)

### Using UI ###

After starting, you can use Swagger UI at [http:~~/~~/localhost:8080/swagger/](http://localhost:8080/swagger/) and explore the API. With Swagger UI you can call API methods in your browser.

![screenshot](signature/images/1596699201339-560.png)

### Using SDK ###

We generate our SDKs in different languages so you may check if yours is available at [GitHub](https://github.com/groupdocs-signature-cloud). SDKs require authentication, so predefined CLIENT_ID/CLIENT_SECRET parameters must be set.

The authentication is required in case you're going to use SDK. To enable authentication set CLIENT_ID/CLIENT_SECRET parameters as it shown below.

{{< tabs tabTotal="2" tabID="3" tabName1="Windows (PowerShell)" tabName2="Linux (bash)" >}} {{< tab tabNum="1" >}}

```javascript

docker run `
    -p 8080:80 `
    -v "${pwd}/data:/data" `
    -e "LICENSE_PUBLIC_KEY#public_key" `
    -e "LICENSE_PRIVATE_KEY#private_key" `
    -e "CLIENT_ID#client_id" `
    -e "CLIENT_SECRET#client_secret" `
    --name signature_cloud `
    groupdocs/signature-cloud

```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript

docker run \
    -p 8080:80 \
    -v $(pwd)/fonts:/fonts \
    -v $(pwd)/data:/data \
    -e LICENSE_PUBLIC_KEY#public_key \
    -e LICENSE_PRIVATE_KEY#private_key \
    -e CLIENT_ID#client_id \
    -e CLIENT_SECRET#client_secret \
    --name signature_cloud \
    groupdocs/signature-cloud

```

{{< /tab >}} {{< /tabs >}}

Then, when using SDK, setup the api base url, as shown in examples below:

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java & Android" tabName3="PHP" tabName4="Node.js" tabName5="Python" tabName6="Ruby" >}} {{< tab tabNum="1" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-dotnet-samples
string ClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
string ClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

var configuration = new Configuration(ClientId, ClientSecret)
{
    ApiBaseUrl = "http://localhost:8080"
};
var apiInstance = new InfoApi(configuration);
var response = apiInstance.GetSupportedFileFormats();

```

{{< /tab >}} {{< tab tabNum="2" >}}

```java

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-java-samples
String ClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
String ClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(ClientId, ClientSecret);
configuration.setApiBaseUrl("http://localhost:8080");

InfoApi apiInstance = new InfoApi(configuration);
FormatsResult response = apiInstance.getSupportedFileFormats();

```

{{< /tab >}} {{< tab tabNum="3" >}}

```php

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-php-samples
use GroupDocs\Signature\Model;
use GroupDocs\Signature\Model\Requests;

$ClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$ClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

$configuration = new GroupDocs\Signature\Configuration();
$configuration->setAppSid($ClientId);
$configuration->setAppKey($ClientSecret);
$configuration->setApiBaseUrl("http://localhost:8080");

$infoApi= new GroupDocs\Signature\InfoApi($configuration);

$response = $infoApi->getSupportedFileFormats();

```

{{< /tab >}} {{< tab tabNum="4" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-node-samples
global.signature_cloud = require("groupdocs-signature-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
const config = new Configuration(clientId, clientSecret);
config.apiBaseUrl = "http://localhost:8080";
global.infoApi = signature_cloud.InfoApi.fromConfig(config);

let response = await infoApi.getSupportedFileFormats();

```

{{< /tab >}} {{< tab tabNum="5" >}}

```python

# For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-python-samples
import groupdocs_signature_cloud

client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

configuration = Configuration(client_id, client_secret)
configuration.api_base_url = "http://localhost:8080"

infoApi = groupdocs_signature_cloud.InfoApi.from_config(configuration)

result = infoApi.get_supported_file_formats()

```

{{< /tab >}} {{< tab tabNum="6" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-ruby-samples
require 'groupdocs_signature_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

config = Configuration.new(client_id, client_secret)
config.api_base_url = "http://localhost:8080"

infoApi = GroupDocsSignatureCloud::InfoApi.from_config(config)

result = infoApi.get_supported_file_formats()

```

{{< /tab >}} {{< /tabs >}}

### Enable Google Cloud Storage

By default, a local storage used inside container for file operations. It's possible to connect a Google Cloud storage by setting GOOGLE_APPLICATION_CREDENTIALS and GOOGLE_STORAGE_BUCKET environment variables.

{{< tabs tabTotal="2" tabID="3" tabName1="Windows (PowerShell)" tabName2="Linux (bash)" >}} {{< tab tabNum="1" >}}

```powershell
docker run `
В В В В -p 8080:80 `
В В В В -v "${pwd}/data:/data" `
В В В В -e "GOOGLE_APPLICATION_CREDENTIALS=/data/key.json" `
В В В В -e "GOOGLE_STORAGE_BUCKET=bucket_id" `
В В В В --name signature_cloud `
В В В В groupdocs/signature-cloud
```

{{< /tab >}} {{< tab tabNum="2" >}}

```bash
docker run \
В В В В -p 8080:80 \
В В В В -v $(pwd)/data:/data \
В В В В -e GOOGLE_APPLICATION_CREDENTIALS=/data/key.json \
В В В В -e GOOGLE_STORAGE_BUCKET=bucket_id \
В В В В --name signature_cloud \
В В В В groupdocs/signature-cloud
```

{{< /tab >}} {{< /tabs >}}

### Stop Container ###

To stop the running Docker container, just use Ctrl+C in the same terminal where the container is running. Alternatively, you can stop the container by name.

```javascript

docker stop signature_cloud

```

## Licensing ##

GroupDocs.Signature Cloud can be started in trial and licensed modes. When GroupDocs.Signature Cloud is working in trial mode the following limitations are applied:

* You can sign only two first pages of the document
* Evaluation watermarks added to the output

## DockerHub ##

You can find more information at [DockerHub](https://hub.docker.com/repository/docker/groupdocs/signature-cloud).

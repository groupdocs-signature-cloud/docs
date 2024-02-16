---
id: "quick-start"
url: "signature/quick-start"
title: "Quick Start"
productName: "GroupDocs.Signature Cloud"
weight: 3
description: ""
keywords: ""
toc: True
---

## Create an account

Creating an account is very simple. Go to [https://dashboard.groupdocs.cloud](https://dashboard.groupdocs.cloud/#/) to create a free account.

## Create an API client app

Before you can make any requests to GroupDocs Cloud API you need to get a **Client Id** and a **Client Secret**.
This will will be used to invoke GroupDocs Cloud API. You can get it by creating a new [Application](https://dashboard.groupdocs.cloud/applications).

## Install the SDK of your choice

GroupDocs for Cloud SDK is written in different languages, all you need to get started is adding our [SDK]({{< ref "signature/getting-started/available-sdks.md" >}}) to your existing project.

## Make an API request from the SDK of your choice

Use the **Client Id** and **Client Secret** from the API app client you created in step one and replace in the corresponding code.
Below is an example demonstrating using the Formats API to get all supported file formats in GroupDocs.Signature Cloud.

{{< alert style="info" >}}The GitHub repository for [GroupDocs.Signature Cloud](https://github.com/groupdocs-signature-cloud) has a complete set of examples, demonstrating our API capabilities.{{< /alert >}}

## SDK example

{{< tabs "example1">}} {{< tab "C#" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-dotnet-samples
string MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
string MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyClientId, MyClientSecret);

var apiInstance = new InfoApi(configuration);
var response = apiInstance.GetSupportedFileFormats();

```

{{< /tab >}} {{< tab "Java" >}}

```java

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-java-samples
String MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
String MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(MyClientId, MyClientSecret);

InfoApi apiInstance = new InfoApi(configuration);
FormatsResult response = apiInstance.getSupportedFileFormats();

```

{{< /tab >}} {{< tab "PHP" >}}

```php

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-php-samples
use GroupDocs\Signature\Model;
use GroupDocs\Signature\Model\Requests;

$ClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$ClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

$configuration = new GroupDocs\Signature\Configuration();
$configuration->setAppSid($ClientId);
$configuration->setAppKey($ClientSecret);

$infoApi# new GroupDocs\Signature\InfoApi($configuration);

$response = $infoApi->getSupportedFileFormats();

```

{{< /tab >}} {{< tab "Node.js" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-node-samples
global.signature_cloud = require("groupdocs-signature-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

global.infoApi = signature_cloud.InfoApi.fromKeys(clientId, clientSecret);

let response = await infoApi.getSupportedFileFormats();

```

{{< /tab >}} {{< tab "Python" >}}

```python

# For complete examples and data files, please go to https://github.com/groupdocs-signature_cloud-cloud/groupdocs-signature_cloud-cloud-python-samples
import groupdocs_signature_cloud

client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

infoApi = groupdocs_signature_cloud.InfoApi.from_keys(client_id, client_secret)

result = infoApi.get_supported_file_formats()

```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-ruby-samples
require 'groupdocs_signature_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

infoApi = GroupDocsSignatureCloud::InfoApi.from_keys($client_id, $client_secret)

result = infoApi.get_supported_file_formats()

```

{{< /tab >}} {{< /tabs >}}

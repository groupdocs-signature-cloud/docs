---
id: "quick-start"
url: "signature/quick-start"
title: "Quick Start"
productName: "GroupDocs.Signature Cloud"
weight: 3
description: ""
keywords: ""
---

## Create an account

Creating an account is very simple. Go to [https://dashboard.groupdocs.cloud](https://dashboard.groupdocs.cloud/#/) to create a free account.

## Create an API client app

Before you can make any requests to GroupDocs for Cloud API you need to get APP SID and APP key (secret key). This will will be used to invoke GroupDocs for Cloud API.

You can get it from default Application or create new Application from [My Apps tab of GroupDocs for Cloud Dashboard]({{< ref "total/getting-started/ui-topics/create-new-app-and-get-app-key-and-sid.md" >}}).

## Install the SDK of your choice

GroupDocs for Cloud SDK is written in different languages, all you need to get started is adding our [SDK]({{< ref "signature/getting-started/available-sdks.md" >}}) to your existing project.

## Make an API request from the SDK of your choice

Use the **App SID** and **App key (secret key)** from the API app client you created in step one and replace in the corresponding code. Below is an example demonstrating using the Formats API to get all supported file formats in GroupDocs.Signature Cloud.

{{< alert style="info" >}}The GitHub repository for [GroupDocs.Signature Cloud](https://github.com/groupdocs-signature-cloud) has a complete set of examples, demonstrating our API capabilities.{{< /alert >}}

## SDK Examples

 C#

```csharp

* For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-dotnet-samples
string MyAppKey # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
string MyAppSid # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud

var configuration # new Configuration(MyAppSid, MyAppKey);

var apiInstance # new InfoApi(configuration);
var response # apiInstance.GetSupportedFileFormats();

```

 Java

```java

* For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-java-samples
String MyAppKey # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
String MyAppSid # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud

Configuration configuration # new Configuration(MyAppSid, MyAppKey);

InfoApi apiInstance # new InfoApi(configuration);
FormatsResult response # apiInstance.getSupportedFileFormats();

```

 PHP

```php

* For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-php-samples
use GroupDocs\Signature\Model;
use GroupDocs\Signature\Model\Requests;

$AppSid # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$AppKey # ""; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud

$configuration # new GroupDocs\Signature\Configuration();
$configuration->setAppSid($AppSid);
$configuration->setAppKey($AppKey);

$infoApi# new GroupDocs\Signature\InfoApi($configuration);

$response # $infoApi->getSupportedFileFormats();

```

 Node

```javascript

* For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-node-samples
global.signature_cloud # require("groupdocs-signature-cloud");

global.appSid # "XXXX-XXXX-XXXX-XXXX"; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud
global.appKey # "XXXXXXXXXXXXXXXX"; * Get AppKey and AppSID from https://dashboard.groupdocs.cloud

global.infoApi # signature_cloud.InfoApi.fromKeys(appSid, appKey);

let response # await infoApi.getSupportedFileFormats();

```

 Python

```python

# For complete examples and data files, please go to https://github.com/groupdocs-signature_cloud-cloud/groupdocs-signature_cloud-cloud-python-samples
import groupdocs_signature_cloud

app_sid # "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
app_key # "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud

infoApi # groupdocs_signature_cloud.InfoApi.from_keys(app_sid, app_key)

result # infoApi.get_supported_file_formats()

```

 Ruby

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-ruby-samples
require 'groupdocs_signature_cloud'

$app_sid # "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$app_key # "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud

infoApi # GroupDocsSignatureCloud::InfoApi.from_keys($app_sid, $app_key)

result # infoApi.get_supported_file_formats()

```

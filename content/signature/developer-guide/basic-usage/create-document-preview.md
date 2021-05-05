---
id: "create-document-preview"
url: "signature/create-document-preview"
title: "Create Document Preview"
productName: "GroupDocs.Signature Cloud"
weight: 5
description: ""
keywords: ""
---


GroupDocs.Signature Cloud allows to create document preview images, one per page. Image size and format can be set as options.

## API Usage ##

There are steps that usage of GroupDocs.Signature Cloud consists of:

1. Upload input document into cloud storage
1. Create preview images
1. Download images

For storage operations, like uploading or downloading documents, please refer to the corresponding articles of this manual.

[Swagger UI](https://apireference.groupdocs.cloud/signature/) lets you call this REST API directly from the browser.

## cURL REST Example ##

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}} {{< tab tabNum="1" >}}

```javascript

// First get JSON Web Token
// Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications. Kindly place Client Id in "client_id" and Client Secret in "client_secret" argument.
curl -v "https://api.groupdocs.cloud/connect/token" \
-X POST \
-d "grant_type#client_credentials&client_id#xxxx&client_secret#xxxx" \
-H "Content-Type: application/x-www-form-urlencoded" \
-H "Accept: application/json"

// cURL example to get document information
curl -v "https://api.groupdocs.cloud/v2.0/signature/preview" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"
-d "{
  'FileInfo': {
    'FilePath': 'sample2.pdf'
  },
  'Format': 'jpg'
}"

```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript
{
  "fileInfo": {
    "filePath": "sample2.pdf",
    "storageName": null,
    "versionId": null,
    "password": null
  },
  "size": 129711,
  "pagesCount": 2,
  "pages": [
    {
      "pageNumber": 0,
      "filePath": "sample2_pdf/page_0.png",
      "size": 161205,
      "downloadUrl": "https://api.groupdocs.cloud/v2.0/signature/storage/file/sample2_pdf/page_0.png"
    },
    {
      "pageNumber": 1,
      "filePath": "sample2_pdf/page_1.png",
      "size": 24062,
      "downloadUrl": "https://api.groupdocs.cloud/v2.0/signature/storage/file/sample2_pdf/page_1.png"
    }
  ]
}
{{< /tab >}} {{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](signature/available-sdks).

### SDK Examples ###

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Python" tabName6="Ruby" >}} {{< tab tabNum="1" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-dotnet-samples
string MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
string MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyClientId, MyClientSecret);
var apiInstance = new PreviewApi(configuration);

// Preview settings
var previewSettings = new PreviewSettings
{
 FileInfo = new FileInfo
 {
  FilePath = "sample2.pdf",
  Password = null,
  VersionId = null,
  StorageName = Constants.MyStorage,
 }
};

var request = new PreviewDocumentRequest(previewSettings);

var response = apiInstance.PreviewDocument(request);
Console.WriteLine("Expected response type is PreviewResult: " + response);

```

{{< /tab >}} {{< tab tabNum="2" >}}

```java

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-java-samples
String MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
String MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(MyClientId, MyClientSecret);
PreviewApi apiInstance = new PreviewApi(configuration);

FileInfo fileInfo = new FileInfo();
fileInfo.setFilePath("Signaturedocs\\one-page.docx");

PreviewSettings previewSettings = new PreviewSettings();
previewSettings.setFileInfo(fileInfo);

PreviewDocumentRequest request = new PreviewDocumentRequest(previewSettings);

PreviewResult response = apiInstance.previewDocument(request);
System.out.println("Expected response type is PreviewResult: " + response);

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

$previewApi = new GroupDocs\Signature\PreviewApi($configuration);

$fileInfo = new GroupDocs\Signature\Model\FileInfo();
$fileInfo->setFilePath("signaturedocs\one-page.docx");

$settings = new GroupDocs\Signature\Model\PreviewSettings();
$settings->setFileInfo($fileInfo);

$request = new GroupDocs\Signature\Model\Requests\previewDocumentRequest($settings);
$response = $previewApi->previewDocument($request);

echo "PreviewResult.Pages Count: " . count($response->getPages());
echo "\n";

```

{{< /tab >}} {{< tab tabNum="4" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-node-samples
global.signature_cloud = require("groupdocs-signature-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

global.previewApi = signature_cloud.PreviewApi.fromKeys(clientId, clientSecret);

let fileInfo = new signature_cloud.FileInfo();
fileInfo.filePath = "signaturedocs/one-page.docx";
let settings = new signature_cloud.PreviewSettings();
settings.fileInfo = fileInfo;
let request = new signature_cloud.PreviewDocumentRequest(settings);
let response = await previewApi.previewDocument(request);
console.log("GetDocumentPreview: PagesCount = " + response.pages.length);

```

{{< /tab >}} {{< tab tabNum="5" >}}

```python

# For complete examples and data files, please go to https://github.com/groupdocs-signature_cloud-cloud/groupdocs-signature_cloud-cloud-python-samples
from groupdocs_signature_cloud import *
import groupdocs_signature_cloud

client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

api = groupdocs_signature_cloud.PreviewApi.from_keys(client_id, client_secret)

fileInfo = FileInfo()
fileInfo.file_path = "signaturedocs\\one-page.docx"
fileInfo.password = None
fileInfo.version_id = None
fileInfo.storage_name = Common.myStorage

settings = PreviewSettings()
settings.file_info = fileInfo

request = PreviewDocumentRequest(settings)
response = api.preview_document(request)

print("Page count = " + str(len(response.pages)))

```

{{< /tab >}} {{< tab tabNum="6" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-ruby-samples
require 'groupdocs_signature_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

api = GroupDocsSignatureCloud::PreviewApi.from_keys($client_id, $client_secret)

$settings = GroupDocsSignatureCloud::PreviewSettings.new()

$info = GroupDocsSignatureCloud::FileInfo.new()
$info.file_path = "signaturedocs\\one-page.docx"
$info.password = nil

$settings.file_info = $info
$request = GroupDocsSignatureCloud::PreviewDocumentRequest.new($settings)

# Executing an API.
$response = api.preview_document($request)

puts("Pages count: " + $response.pages.length.to_s)

```

{{< /tab >}} {{< /tabs >}}

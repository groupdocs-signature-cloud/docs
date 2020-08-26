---
id: "delete-barcode-signatures"
url: "signature/delete-barcode-signatures"
title: "Delete Barcode signatures"
productName: "GroupDocs.Signature Cloud"
description: ""
keywords: ""
---

# Introduction #

GroupDocs.Signature Cloud provides a method to delete signature from the signed document. The signature ID is needed to perform the delete, it comes from the result of sign or search operation.

This example shows how to delete Barcode signature.

API Usage

There are steps that usage of GroupDocs.Signature Cloud consists of:

1. Upload input document into cloud storage
1. Delete signatures
1. Download output document

For storage operations, like uploading or downloading documents, please refer to the corresponding articles of this manual.

[Swagger UI](https://apireference.groupdocs.cloud/signature/) lets you call this REST API directly from the browser.

## cURL REST Example ##

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}} {{< tab tabNum="1" >}}

```javascript

// First get JSON Web Token
// Please get your App Key and App SID from https://dashboard.groupdocs.cloud/#/apps. Kindly place App Key in "client_secret" and App SID in "client_id" argument.
curl -v "https://api.groupdocs.cloud/connect/token" \
-X POST \
-d "grant_type#client_credentials&client_id#xxxx&client_secret#xxxx" \
-H "Content-Type: application/x-www-form-urlencoded" \
-H "Accept: application/json"

// cURL example to get document information
curl -v "https://api.groupdocs.cloud/v2.0/signature/delete" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"
-d "{
  'FileInfo': {
    'FilePath': 'signedBarcode_one-page.docx'
  },
  'Options': [
    {
      'SignatureType': 'Barcode',
      'SignatureId': '4cb67aa8-835d-4877-8a5d-5a9ad015a098'
    }
  ]
}"

```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript

{
  "fileInfo": {
    "filePath": "signedBarcode_one-page.docx",
    "storageName": null,
    "versionId": null,
    "password": null
  },
  "size": 1360026,
  "succeeded": [
    {
      "barcodeType": "Code128",
      "text": "123456789012",
      "format": null,
      "signatureType": "Barcode",
      "pageNumber": 1,
      "signatureId": "4cb67aa8-835d-4877-8a5d-5a9ad015a098",
      "isSignature": true,
      "createdOn": "2020-07-23T07:26:42.7549544+00:00",
      "modifiedOn": "2020-07-23T07:36:03.9037414+00:00",
      "top": 0,
      "left": 0,
      "width": 0,
      "height": 0
    }
  ],
  "failed": []
}

{{< /tab >}} {{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### SDK Examples ###

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Python" tabName6="Ruby" >}} {{< tab tabNum="1" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-dotnet-samples
string MyAppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
string MyAppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyAppSid, MyAppKey);
var apiInstance = new SignApi(configuration);

// Search barcode signature to get ID
var searchBarcodeOptions = new SearchBarcodeOptions
{
    SignatureType = SignatureTypeEnum.Barcode,
    MatchType = SearchBarcodeOptions.MatchTypeEnum.Contains,
    Text = "123456789012",
    BarcodeType = "Code128",
    AllPages = true
};
// Search settings.
var searchSettings = new SearchSettings
{
    FileInfo = new FileInfo
    {
        FilePath = "signedBarcode_one-page.docx",
    },
    Options = new List<SearchOptions> { searchBarcodeOptions }
};
// Call api method with request.
var searchResult = apiInstance.SearchSignatures(new SearchSignaturesRequest(searchSettings));

// Delete options
var options = new DeleteOptions
{
    SignatureType = DeleteOptions.SignatureTypeEnum.Barcode,
    SignatureId = searchResult.Signatures[0].SignatureId
};
// Delete settings
var deleteSettings = new DeleteSettings
{
    FileInfo = new FileInfo
    {
        FilePath = "signedBarcode_one-page.docx"
    },
    Options = new List<DeleteOptions> { options }
};
// Create request
var request = new DeleteSignaturesRequest(deleteSettings);
// Call api method with request
var response = apiInstance.DeleteSignatures(request);

```

{{< /tab >}} {{< tab tabNum="2" >}}

```java

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-java-samples
String MyAppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
String MyAppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(MyAppSid, MyAppKey);
SignApi apiInstance = new SignApi(configuration);

FileInfo fileInfo = new FileInfo();
fileInfo.setFilePath("Signaturedocs\\signedBarcodeOne_page.docx");

InfoSettings infoSettings = new InfoSettings();
infoSettings.setFileInfo(fileInfo);

SearchBarcodeOptions options = new SearchBarcodeOptions();
options.setSignatureType(SignatureTypeEnum.BARCODE);
options.setAllPages(true);
SearchSettings searchSettings = new SearchSettings();
searchSettings.setFileInfo(fileInfo);
searchSettings.addOptionsItem(options);

SearchSignaturesRequest request = new SearchSignaturesRequest(searchSettings);
SearchResult  searchResult = apiInstance.searchSignatures(request);

DeleteOptions deleteOptions = new DeleteOptions();
deleteOptions.setSignatureType(DeleteOptions.SignatureTypeEnum.BARCODE);
deleteOptions.setSignatureId(searchResult.getSignatures().get(0).getSignatureId());

DeleteSettings deleteSettings = new DeleteSettings();
deleteSettings.setFileInfo(fileInfo);
deleteSettings.addOptionsItem(deleteOptions);

DeleteResult deleteResult = apiInstance.deleteSignatures(new DeleteSignaturesRequest(deleteSettings));

```

{{< /tab >}} {{< tab tabNum="3" >}}

```php

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-php-samples
use GroupDocs\Signature\Model;
use GroupDocs\Signature\Model\Requests;

$AppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$AppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud

$configuration = new GroupDocs\Signature\Configuration();
$configuration->setAppSid($AppSid);
$configuration->setAppKey($AppKey);

$apiInstance = new GroupDocs\Signature\SignApi($configuration);

$fileInfo = new GroupDocs\Signature\Model\FileInfo();
$fileInfo->setFilePath("signaturedocs\signedBarcodeOne_page.docx");

// Search
$settings = new GroupDocs\Signature\Model\SearchSettings();
$settings->setFileInfo($fileInfo);

$options = new GroupDocs\Signature\Model\SearchBarcodeOptions();
$options->setPage(1);
$options->setAllPages(false);
$options->setSignatureType(GroupDocs\Signature\Model\OptionsBase::SIGNATURE_TYPE_BARCODE);

$settings->setOptions([$options]);

$request = new GroupDocs\Signature\Model\Requests\SearchSignaturesRequest($settings);
$response = $apiInstance->searchSignatures($request);

// Delete
$deleteSettings = new GroupDocs\Signature\Model\DeleteSettings();
$deleteSettings->setFileInfo($fileInfo);

$deleteOptions = new GroupDocs\Signature\Model\DeleteOptions();
$deleteOptions->setSignatureType(GroupDocs\Signature\Model\DeleteOptions::SIGNATURE_TYPE_BARCODE);
$deleteOptions->setSignatureId($response->getSignatures()[0]->getSignatureId());

$deleteSettings->setOptions([$deleteOptions]);

$request = new GroupDocs\Signature\Model\Requests\DeleteSignaturesRequest($deleteSettings);
$response = $apiInstance->deleteSignatures($request);

```

{{< /tab >}} {{< tab tabNum="4" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-node-samples
global.signature_cloud = require("groupdocs-signature-cloud");

global.appSid = "XXXX-XXXX-XXXX-XXXX"; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
global.appKey = "XXXXXXXXXXXXXXXX"; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud

global.signApi = signature_cloud.SignApi.fromKeys(appSid, appKey);

let fileInfo = new signature_cloud.FileInfo();
fileInfo.filePath = "signaturedocs/signedBarcodeOne_page.docx";

// Search
let opts = new signature_cloud.SearchBarcodeOptions();
opts.signatureType = signature_cloud.OptionsBase.SignatureTypeEnum.Barcode;
opts.matchType = signature_cloud.SearchBarcodeOptions.MatchTypeEnum.Contains;
opts.allPages = true;

let settings = new signature_cloud.SearchSettings();
settings.fileInfo = fileInfo;
settings.options = [opts];

let request = new signature_cloud.SearchSignaturesRequest(settings);
let response = await signApi.searchSignatures(request);

console.log("signatureId = " + response.signatures[0].signatureId);

// Delete
let deleteOpts = new signature_cloud.DeleteOptions();
deleteOpts.signatureType = signature_cloud.DeleteOptions.SignatureTypeEnum.Barcode;
deleteOpts.signatureId = response.signatures[0].signatureId;

let deleteSettings = new signature_cloud.DeleteSettings();
deleteSettings.fileInfo = fileInfo;
deleteSettings.options = [deleteOpts];

request = new signature_cloud.DeleteSignaturesRequest(deleteSettings);
response = await signApi.deleteSignatures(request);

```

{{< /tab >}} {{< tab tabNum="5" >}}

```python

# For complete examples and data files, please go to https://github.com/groupdocs-signature_cloud-cloud/groupdocs-signature_cloud-cloud-python-samples
from groupdocs_signature_cloud import *
import groupdocs_signature_cloud

app_sid = "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
app_key = "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud

api = groupdocs_signature_cloud.SignApi.from_keys(app_sid, app_key)

fileInfo = FileInfo()
fileInfo.file_path = "signaturedocs\\signedBarcodeOne_page.docx"

# Search
opts = SearchBarcodeOptions()
opts.page = 1
opts.signature_type = 'Barcode'

settings = SearchSettings()
settings.options = [opts]
settings.file_info = fileInfo

request = SearchSignaturesRequest(settings)
response = api.search_signatures(request)

# Delete
opts = DeleteOptions()
opts.page = 1
opts.signature_type = 'Barcode'
opts.signature_id = response.signatures[0].signature_id

settings = DeleteSettings()
settings.options = [opts]
settings.file_info = fileInfo

request = DeleteSignaturesRequest(settings)
response = api.delete_signatures(request)

```

{{< /tab >}} {{< tab tabNum="6" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-ruby-samples
require 'groupdocs_signature_cloud'

$app_sid = "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$app_key = "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud

api = GroupDocsSignatureCloud::SignApi.from_keys($app_sid, $app_key)

$info = GroupDocsSignatureCloud::FileInfo.new()
$info.file_path = "signaturedocs\\signedBarcodeOne_page.docx"

# Search
$opts = GroupDocsSignatureCloud::SearchBarcodeOptions.new()
$opts.signature_type = "Barcode"
$opts.all_pages = true

$settings = GroupDocsSignatureCloud::SearchSettings.new()
$settings.options = [$opts]
$settings.file_info = $info

$request = GroupDocsSignatureCloud::SearchSignaturesRequest.new($settings)
$response = api.search_signatures($request)

# Delete
$deleteOpts = GroupDocsSignatureCloud::DeleteOptions.new()
$deleteOpts.signature_type = "Barcode"
$deleteOpts.signature_id = $response.signatures[0].signature_id

$deleteSettings = GroupDocsSignatureCloud::DeleteSettings.new()
$deleteSettings.options = [$deleteOpts]
$deleteSettings.file_info = $info

$request = GroupDocsSignatureCloud::DeleteSignaturesRequest.new($deleteSettings)
$response = api.delete_signatures($request)

```

{{< /tab >}} {{< /tabs >}}


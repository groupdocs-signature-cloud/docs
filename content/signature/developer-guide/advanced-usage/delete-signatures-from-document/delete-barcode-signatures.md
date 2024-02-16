---
id: "delete-barcode-signatures"
url: "signature/delete-barcode-signatures"
title: "Delete Barcode signatures"
productName: "GroupDocs.Signature Cloud"
description: ""
keywords: ""
toc: True
---


GroupDocs.Signature Cloud provides a method to delete signature from the signed document. The signature ID is needed to perform the delete, it comes from the result of sign or search operation.

## API usage

There are steps that usage of GroupDocs.Signature Cloud consists of:

1. Upload input document into cloud storage
1. Delete signatures
1. Download output document

For storage operations, like uploading or downloading documents, please refer to the corresponding articles of this manual.

[Swagger UI](https://apireference.groupdocs.cloud/signature/) lets you call this REST API directly from the browser.

## cURL example

{{< tabs "example1">}} {{< tab "Request" >}}

```javascript

// First get JSON Web Token
// Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications. Kindly place Client Id in "client_id" and Client Secret in "client_secret" argument.
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

{{< /tab >}} {{< tab "Response" >}}

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
```
{{< /tab >}} {{< /tabs >}}

## SDK examples

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](/signature/available-sdks).



{{< tabs "example2">}} {{< tab "C#" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-dotnet-samples
string MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
string MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyClientId, MyClientSecret);
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

{{< /tab >}} {{< tab "Java" >}}

```java

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-java-samples
String MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
String MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(MyClientId, MyClientSecret);
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

{{< /tab >}} {{< tab "Node.js" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-node-samples
global.signature_cloud = require("groupdocs-signature-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

global.signApi = signature_cloud.SignApi.fromKeys(clientId, clientSecret);

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

{{< /tab >}} {{< tab "Python" >}}

```python

# For complete examples and data files, please go to https://github.com/groupdocs-signature_cloud-cloud/groupdocs-signature_cloud-cloud-python-samples
from groupdocs_signature_cloud import *
import groupdocs_signature_cloud

client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

api = groupdocs_signature_cloud.SignApi.from_keys(client_id, client_secret)

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

{{< /tab >}} {{< tab "Ruby" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-ruby-samples
require 'groupdocs_signature_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

api = GroupDocsSignatureCloud::SignApi.from_keys($client_id, $client_secret)

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


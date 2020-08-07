---
id: "search-for-barcode-signatures"
url: "signature/search-for-barcode-signatures"
title: "Search for Barcode signatures"
productName: "GroupDocs.Signature Cloud"
description: ""
keywords: ""
---

# Introduction #

GroupDocs.Signature Cloud provides an easy and straightforward way to find all Barcode signatures that are present in a document

API Usage

There are steps that usage of GroupDocs.Signature Cloud consists of:

1. Upload input document into cloud storage
1. Search signatures

For storage operations, like uploading or downloading documents, please refer to the corresponding articles of this manual.

[Swagger UI](https://apireference.groupdocs.cloud/signature/) lets you call this REST API directly from the browser.

## cURL REST Example ##

 Request

```javascript

// First get JSON Web Token
// Please get your App Key and App SID from https://dashboard.groupdocs.cloud/#/apps. Kindly place App Key in "client_secret" and App SID in "client_id" argument.
curl -v "https://api.groupdocs.cloud/connect/token" \
-X POST \
-d "grant_type#client_credentials&client_id#xxxx&client_secret#xxxx" \
-H "Content-Type: application/x-www-form-urlencoded" \
-H "Accept: application/json"

// cURL example to get document information
curl -v "https://api.groupdocs.cloud/v2.0/signature/search" \
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
      'AllPages': true,
      'SignatureType': 'Barcode'
    }
  ]
}"

```

 Response

```javascript

{
  "fileInfo": {
    "filePath": "signedBarcode_one-page.docx",
    "storageName": null,
    "versionId": null,
    "password": null
  },
  "size": 1360015,
  "signatures": [
    {
      "barcodeType": "Code128",
      "text": "123456789012",
      "format": "Portable Network Graphic",
      "signatureType": "Barcode",
      "pageNumber": 1,
      "signatureId": "114bc076-f734-4edf-9ce4-2277725a6ea5",
      "isSignature": true,
      "createdOn": "2020-07-22T07:45:01.6812929+00:00",
      "modifiedOn": "2020-07-22T07:45:01.6812929+00:00",
      "top": 100,
      "left": 100,
      "width": 300,
      "height": 100
    }
  ]
}

```

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### SDK Examples ###

 C#

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-dotnet-samples
string MyAppKey = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
string MyAppSid = ""; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyAppSid, MyAppKey);
var apiInstance = new SignApi(configuration);

// Search options.
var options = new SearchBarcodeOptions
{
    SignatureType = SignatureTypeEnum.Barcode,
    MatchType = SearchBarcodeOptions.MatchTypeEnum.Contains,
    Text = "123456789012",
    BarcodeType = "Code128",
    Page = 1,
    AllPages = true,
    PagesSetup = new PagesSetup
    {
        EvenPages = false,
        FirstPage = true,
        LastPage = false,
        OddPages = false,
        PageNumbers = new List<int?> {1}
    }
};
// Search settings.
var searchSettings = new SearchSettings
{
    FileInfo = new FileInfo
    {
        FilePath = "signedBarcode_one-page.docx"
    },
    Options = new List<SearchOptions> { options }
};
// Create request.
var request = new SearchSignaturesRequest(searchSettings);
// Call api method with request.
var response = apiInstance.SearchSignatures(request);

```

 Java

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

options.setPage(1);
options.setAllPages(true);

PagesSetup pagesSetup = new PagesSetup();
pagesSetup.setEvenPages(false);
pagesSetup.setFirstPage(true);
pagesSetup.setLastPage(false);
pagesSetup.setOddPages(false);
pagesSetup.addPageNumbersItem(1);
options.setPagesSetup(pagesSetup);

options.setBarcodeType("Code128");
options.setText("123456789012");
options.setMatchType(MatchTypeEnum.CONTAINS);

SearchSettings searchSettings = new SearchSettings();
searchSettings.setFileInfo(fileInfo);
searchSettings.addOptionsItem(options);

SearchSignaturesRequest request = new SearchSignaturesRequest(searchSettings);

SearchResult  response = apiInstance.searchSignatures(request);

```

 PHP

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
$fileInfo->setPassword("");

$settings = new GroupDocs\Signature\Model\SearchSettings();
$settings->setFileInfo($fileInfo);

$options = new GroupDocs\Signature\Model\SearchBarcodeOptions();
$options->setPage(1);
$options->setAllPages(false);
$options->setSignatureType(GroupDocs\Signature\Model\OptionsBase::SIGNATURE_TYPE_BARCODE);

$settings->setOptions([$options]);

$request = new GroupDocs\Signature\Model\Requests\SearchSignaturesRequest($settings);
$response = $apiInstance->searchSignatures($request);

```

 Node

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-node-samples
global.signature_cloud = require("groupdocs-signature-cloud");

global.appSid = "XXXX-XXXX-XXXX-XXXX"; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud
global.appKey = "XXXXXXXXXXXXXXXX"; // Get AppKey and AppSID from https://dashboard.groupdocs.cloud

global.signApi = signature_cloud.SignApi.fromKeys(appSid, appKey);

let fileInfo = new signature_cloud.FileInfo();
fileInfo.filePath = "signaturedocs/signedBarcodeOne_page.docx";

let opts = new signature_cloud.SearchBarcodeOptions();
opts.signatureType = signature_cloud.OptionsBase.SignatureTypeEnum.Barcode;
opts.matchType = signature_cloud.SearchBarcodeOptions.MatchTypeEnum.Contains;
opts.allPages = true;

let settings = new signature_cloud.SearchSettings();
settings.fileInfo = fileInfo;
settings.options = [opts];

let request = new signature_cloud.SearchSignaturesRequest(settings);
let response = await signApi.searchSignatures(request);

```

 Python

```python

# For complete examples and data files, please go to https://github.com/groupdocs-signature_cloud-cloud/groupdocs-signature_cloud-cloud-python-samples
from groupdocs_signature_cloud import *
import groupdocs_signature_cloud

app_sid = "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
app_key = "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud

api = groupdocs_signature_cloud.SignApi.from_keys(app_sid, app_key)

fileInfo = FileInfo()
fileInfo.file_path = "signaturedocs\\signedBarcodeOne_page.docx"

opts = SearchBarcodeOptions()
# set signature properties
opts.page = 1
opts.signature_type = 'Barcode'

settings = SearchSettings()
settings.options = [opts]
settings.file_info = fileInfo

request = SearchSignaturesRequest(settings)
response = api.search_signatures(request)

```

 Ruby

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-ruby-samples
require 'groupdocs_signature_cloud'

$app_sid = "XXXX-XXXX-XXXX-XXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud
$app_key = "XXXXXXXXXXXXXXXX" # Get AppKey and AppSID from https://dashboard.groupdocs.cloud

api = GroupDocsSignatureCloud::SignApi.from_keys($app_sid, $app_key)

$info = GroupDocsSignatureCloud::FileInfo.new()
$info.file_path = "signaturedocs\\signedBarcodeOne_page.docx"

$opts = GroupDocsSignatureCloud::SearchBarcodeOptions.new()
$opts.signature_type = "Barcode"
$opts.all_pages = true

$settings = GroupDocsSignatureCloud::SearchSettings.new()
$settings.options = [$opts]
$settings.file_info = $info

$request = GroupDocsSignatureCloud::SearchSignaturesRequest.new($settings)

# Executing an API.
$response = api.search_signatures($request)

```


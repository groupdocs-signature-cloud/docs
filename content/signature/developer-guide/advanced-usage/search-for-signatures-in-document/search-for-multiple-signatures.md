---
id: "search-for-multiple-signatures"
url: "signature/search-for-multiple-signatures"
title: "Search for multiple signatures"
productName: "GroupDocs.Signature Cloud"
description: ""
keywords: ""
---

# Introduction #

Sometimes you may want to search for electronic signatures of different types simultaneously. GroupDocs.Signature Cloud allows searching documents for different signature types in an easy and intuitive way. In common words the idea is to pass collection of desired signature types to Search method.

API Usage

There are steps that usage of GroupDocs.Signature Cloud consists of:

1. Upload input document into cloud storage
1. Search signatures

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
curl -v "https://api.groupdocs.cloud/v2.0/signature/search" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"
-d "{
  'FileInfo': {
    'FilePath': 'signaturedocs/signedCollectionsOne_page.docx'
  },
  'Options': [
    {
      'AllPages': true,
      'SignatureType': 'Barcode'
    },
    {
      'AllPages': true,
      'SignatureType': 'QRCode'
    }
  ]
}"

```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript

{
  "fileInfo": {
    "filePath": "signaturedocs/signedCollectionsOne_page.docx",
    "storageName": null,
    "versionId": null,
    "password": null
  },
  "size": 1360032,
  "signatures": [
    {
      "barcodeType": "Code128",
      "text": "123456789012",
      "format": "Portable Network Graphic",
      "signatureType": "Barcode",
      "pageNumber": 1,
      "signatureId": "e0df7708-fd89-40c1-94f5-46bf75a8748b",
      "isSignature": true,
      "createdOn": "2020-07-14T07:46:47.1162335+00:00",
      "modifiedOn": "2020-07-14T07:46:47.1162335+00:00",
      "top": 100,
      "left": 100,
      "width": 300,
      "height": 100
    }
  ]
}

{{< /tab >}} {{< /tabs >}}

## SDKs ##

The API is completely independent of your operating system, database system or development language. We provide and support API SDKs in many development languages in order to make it even easier to integrate. You can see our available SDKs list [here](https://github.com/groupdocs-signature-cloud).

### SDK Examples ###

{{< tabs tabTotal="6" tabID="10" tabName1="C#" tabName2="Java" tabName3="PHP" tabName4="Node.js" tabName5="Python" tabName6="Ruby" >}} {{< tab tabNum="1" >}}

```csharp

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-dotnet-samples
string MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
string MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

var configuration = new Configuration(MyClientId, MyClientSecret);
var apiInstance = new SignApi(configuration);

// Barcode Search options.
var barcodeOptions = new SearchBarcodeOptions
{
    SignatureType = SignatureTypeEnum.Barcode,
    MatchType = SearchBarcodeOptions.MatchTypeEnum.Contains,
    Text = "123456789012",
    BarcodeType = "Code128",
    AllPages = false,
    Page = 1,
    PagesSetup = new PagesSetup
    {
        EvenPages = false,
        FirstPage = true,
        LastPage = false,
        OddPages = false,
        PageNumbers = new List<int?> {1}
    }
};
// QRCode search options.
var qrCodeOptions = new SearchQRCodeOptions
{
    SignatureType = SignatureTypeEnum.QRCode,
    MatchType = SearchQRCodeOptions.MatchTypeEnum.Contains,
    Text = "GroupDocs.Signature Cloud",
    QRCodeType = "Aztec",
    AllPages = false,
    Page = 1,
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
        FilePath = "signedCollection_one-page.docx"
    },
    Options = new List<SearchOptions> { barcodeOptions, qrCodeOptions }
};
// Create request.
var request = new SearchSignaturesRequest(searchSettings);
// Call api method with request.
var response = apiInstance.SearchSignatures(request);

```

{{< /tab >}} {{< tab tabNum="2" >}}

```java

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-java-samples
String MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
String MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(MyClientId, MyClientSecret);
SignApi apiInstance = new SignApi(configuration);

FileInfo fileInfo = new FileInfo();
fileInfo.setFilePath("Signaturedocs\\signedCollectionOne_page.docx");

InfoSettings infoSettings = new InfoSettings();
infoSettings.setFileInfo(fileInfo);

SearchBarcodeOptions barcodeOptions = new SearchBarcodeOptions();
barcodeOptions.setSignatureType(SignatureTypeEnum.BARCODE);

barcodeOptions.setPage(1);
barcodeOptions.setAllPages(true);

PagesSetup pagesSetup = new PagesSetup();
pagesSetup.setEvenPages(false);
pagesSetup.setFirstPage(true);
pagesSetup.setLastPage(false);
pagesSetup.setOddPages(false);
pagesSetup.addPageNumbersItem(1);
barcodeOptions.setPagesSetup(pagesSetup);

barcodeOptions.setBarcodeType("Code128");
barcodeOptions.setText("123456789012");
barcodeOptions.setMatchType(MatchTypeEnum.CONTAINS);

SearchDigitalOptions digitalOptions = new SearchDigitalOptions();
digitalOptions.setSignatureType(SignatureTypeEnum.DIGITAL);
digitalOptions.setPage(1);
digitalOptions.setAllPages(true);

pagesSetup = new PagesSetup();
pagesSetup.setEvenPages(false);
pagesSetup.setFirstPage(true);
pagesSetup.setLastPage(false);
pagesSetup.setOddPages(false);
pagesSetup.addPageNumbersItem(1);
digitalOptions.setPagesSetup(pagesSetup);

SearchSettings searchSettings = new SearchSettings();
searchSettings.addOptionsItem(barcodeOptions);
searchSettings.addOptionsItem(digitalOptions);
searchSettings.setFileInfo(fileInfo);

SearchSignaturesRequest request = new SearchSignaturesRequest(searchSettings);

SearchResult  response = apiInstance.searchSignatures(request);

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

$apiInstance = new GroupDocs\Signature\SignApi($configuration);

$fileInfo = new GroupDocs\Signature\Model\FileInfo();
$fileInfo->setFilePath("signaturedocs/signedCollectionsOne_page.docx");
$fileInfo->setPassword("");

$settings = new GroupDocs\Signature\Model\SearchSettings();
$settings->setFileInfo($fileInfo);

// Search QrCode options
$QrCodeoptions = new GroupDocs\Signature\Model\SearchQRCodeOptions();
$QrCodeoptions->setPage(1);
$QrCodeoptions->setAllPages(false);
$QrCodeoptions->setSignatureType(GroupDocs\Signature\Model\OptionsBase::SIGNATURE_TYPE_QR_CODE);
$QrCodeoptions->setQRCodeType("Aztec");

// Search Barcode options
$barcodeOptions = new GroupDocs\Signature\Model\SearchBarcodeOptions();
$barcodeOptions->setPage(1);
$barcodeOptions->setAllPages(false);
$barcodeOptions->setSignatureType(GroupDocs\Signature\Model\OptionsBase::SIGNATURE_TYPE_BARCODE);
$barcodeOptions->setBarcodeType("Code128");
$barcodeOptions->setText("123456789012");

$settings->setOptions([$QrCodeoptions, $barcodeOptions]);

$request = new GroupDocs\Signature\Model\Requests\SearchSignaturesRequest($settings);
$response = $apiInstance->searchSignatures($request);

```

{{< /tab >}} {{< tab tabNum="4" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-node-samples
global.signature_cloud = require("groupdocs-signature-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

global.signApi = signature_cloud.SignApi.fromKeys(clientId, clientSecret);

let fileInfo = new signature_cloud.FileInfo();
fileInfo.filePath = "signaturedocs/signedCollection_One_page.docx";

let BarcodeOpts = new signature_cloud.SearchBarcodeOptions();
BarcodeOpts.signatureType = signature_cloud.OptionsBase.SignatureTypeEnum.Barcode;
BarcodeOpts.matchType = signature_cloud.SearchQRCodeOptions.MatchTypeEnum.Contains;
BarcodeOpts.allPages = true;

let Digitalopts = new signature_cloud.SearchDigitalOptions();
Digitalopts.signatureType = signature_cloud.OptionsBase.SignatureTypeEnum.Digital;

let settings = new signature_cloud.SearchSettings();
settings.fileInfo = fileInfo;
settings.options = [BarcodeOpts, Digitalopts];

let request = new signature_cloud.SearchSignaturesRequest(settings);
let response = await signApi.searchSignatures(request);

```

{{< /tab >}} {{< tab tabNum="5" >}}

```python

# For complete examples and data files, please go to https://github.com/groupdocs-signature_cloud-cloud/groupdocs-signature_cloud-cloud-python-samples
from groupdocs_signature_cloud import *
import groupdocs_signature_cloud

client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

api = groupdocs_signature_cloud.SignApi.from_keys(client_id, client_secret)

fileInfo = FileInfo()
fileInfo.file_path = "signaturedocs\\signedCollectionOne_page.docx"

Digitalopts = SearchDigitalOptions()
Digitalopts.signature_type = 'Digital'

Barcodeopts = SearchBarcodeOptions()
Barcodeopts.page = 1
Barcodeopts.signature_type = 'Barcode'

settings = SearchSettings()
settings.options = [Digitalopts,Barcodeopts]
settings.file_info = fileInfo

request = SearchSignaturesRequest(settings)
response = api.search_signatures(request)

```

{{< /tab >}} {{< tab tabNum="6" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-ruby-samples
require 'groupdocs_signature_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

api = GroupDocsSignatureCloud::SignApi.from_keys($client_id, $client_secret)

$info = GroupDocsSignatureCloud::FileInfo.new()
$info.file_path = "signaturedocs\\signedCollectionOne_page.docx"

$BarcodeOpts = GroupDocsSignatureCloud::SearchBarcodeOptions.new()
$BarcodeOpts.signature_type = "Barcode"
$BarcodeOpts.all_pages = true

$BarcodeOpts = GroupDocsSignatureCloud::SearchQRCodeOptions.new()
$BarcodeOpts.signature_type = "QRCode"
$BarcodeOpts.all_pages = true

$settings = GroupDocsSignatureCloud::SearchSettings.new()
$settings.options = [$BarcodeOpts, $BarcodeOpts]
$settings.file_info = $info

$request = GroupDocsSignatureCloud::SearchSignaturesRequest.new($settings)

# Executing an API.
$response = api.search_signatures($request)

```

{{< /tab >}} {{< /tabs >}}


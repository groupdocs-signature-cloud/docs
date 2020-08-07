---
id: "verify-barcode-signatures"
url: "signature/verify-barcode-signatures"
title: "Verify Barcode signatures"
productName: "GroupDocs.Signature Cloud"
description: ""
keywords: ""
---

# Introduction #

GroupDocs.Signature Cloud provides a method to verify if the signatures with given properties are present in a document. The result of verify method contains boolean value IsSuccess (true or false).

This example shows how to verify Barcode signature.

API Usage

There are steps that usage of GroupDocs.Signature Cloud consists of:

1. Upload input document into cloud storage
1. Verify signatures

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
curl -v "https://api.groupdocs.cloud/v2.0/signature/verify" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"
-d "{
  'FileInfo': {
    'FilePath': 'signaturedocs/signedBarcode_one-page.docx'
  },
  'Options': [
    {
      'AllPages': true,
      'SignatureType': 'Barcode',
      'BarcodeType': 'Code128',
      'Text': '123456789012',
      'MatchType': 'Contains'
    }
  ]
}"

```

 Response

```javascript

{
  "fileInfo": {
    "filePath": "signaturedocs/signedBarcode_one-page.docx",
    "storageName": null,
    "versionId": null,
    "password": null
  },
  "size": 1360009,
  "isSuccess": true
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

// Verify options.
var options = new VerifyBarcodeOptions
{
    SignatureType = SignatureTypeEnum.Barcode,
    MatchType = VerifyTextOptions.MatchTypeEnum.Contains,
    Text = "123456789012",
    BarcodeType = "Code128",
    Page = 1,
    AllPages = true
};
// Verify settings
var verifySettings = new VerifySettings
{
    FileInfo = new FileInfo
    {
        FilePath = "signedBarcode_one-page.docx"
    },
    Options = new List<VerifyOptions> { options }
};
// Create request
var request = new VerifySignaturesRequest(verifySettings);
// Call api method with request
var response = apiInstance.VerifySignatures(request);

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

VerifyBarcodeOptions options = new VerifyBarcodeOptions();
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

VerifySettings verifySettings = new VerifySettings();
verifySettings.setFileInfo(fileInfo);
verifySettings.addOptionsItem(options);

VerifySignaturesRequest request = new VerifySignaturesRequest(verifySettings);

VerifyResult  response = apiInstance.verifySignatures(request);

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

$settings = new GroupDocs\Signature\Model\VerifySettings();
$settings->setFileInfo($fileInfo);

$options = new GroupDocs\Signature\Model\VerifyBarcodeOptions();
$options->setPage(1);
$options->setAllPages(false);
$options->setSignatureType(GroupDocs\Signature\Model\OptionsBase::SIGNATURE_TYPE_BARCODE);
$options->setBarcodeType("Code128");
$options->setText("123456789012");

$padding = new GroupDocs\Signature\Model\Padding();
$padding->setAll(5);

$pagesSetup = new GroupDocs\Signature\Model\PagesSetup();
$pagesSetup->setEvenPages(false);
$pagesSetup->setFirstPage(true);
$pagesSetup->setLastPage(false);
$pagesSetup->setOddPages(false);
$pagesSetup->setPageNumbers([1]);
$options->setPagesSetup($pagesSetup);

$settings->setOptions([$options]);

$request = new GroupDocs\Signature\Model\Requests\VerifySignaturesRequest($settings);
$response = $apiInstance->verifySignatures($request);

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

let opts = new signature_cloud.VerifyBarcodeOptions();
opts.signatureType = signature_cloud.OptionsBase.SignatureTypeEnum.Barcode;
opts.barcodeType = 'Code39Standard';
opts.text = '123456789012';
opts.matchType = signature_cloud.VerifyBarcodeOptions.MatchTypeEnum.Contains;

opts.page = 1;
opts.allPages = true;

let settings = new signature_cloud.VerifySettings();
settings.fileInfo = fileInfo;
settings.options = [opts];

let request = new signature_cloud.VerifySignaturesRequest(settings);
let response = await signApi.verifySignatures(request);

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

opts = VerifyBarcodeOptions()
opts.signature_type = 'Barcode'
opts.text = '123456789012'
opts.barcode_type = 'Code128'
opts.match_type = 'Contains'

opts.page = 1

settings = VerifySettings()
settings.options = [opts]
settings.file_info = fileInfo

request = VerifySignaturesRequest(settings)
response = api.verify_signatures(request)

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

$opts = GroupDocsSignatureCloud::VerifyBarcodeOptions.new()
$opts.signature_type = "Barcode"
$opts.barcode_type = "Code128"
$opts.text = "123456789012"
$opts.match_type = "Contains"
$opts.page = 1

$settings = GroupDocsSignatureCloud::VerifySettings.new()
$settings.options = [$opts]
$settings.file_info = $info

$request = GroupDocsSignatureCloud::VerifySignaturesRequest.new($settings)

# Executing an API.
$response = api.verify_signatures($request)

```

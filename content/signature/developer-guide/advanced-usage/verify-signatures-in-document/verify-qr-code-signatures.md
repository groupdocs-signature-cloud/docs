---
id: "verify-qr-code-signatures"
url: "signature/verify-qr-code-signatures"
title: "Verify QR-code signatures"
productName: "GroupDocs.Signature Cloud"
description: ""
keywords: ""
toc: True
---

GroupDocs.Signature Cloud provides a method to verify if the signatures with given properties are present in a document. The result of verify method contains boolean value IsSuccess (true or false).

## API usage

There are steps that usage of GroupDocs.Signature Cloud consists of:

1. Upload input document into cloud storage
1. Verify signatures

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
curl -v "https://api.groupdocs.cloud/v2.0/signature/verify" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"
-d "{
  'FileInfo': {
    'FilePath': 'signaturedocs/signedQRCode_one-page.docx'
  },
  'Options': [
    {
      'AllPages': true,
      'SignatureType': 'QRCode',
      'QRCodeType': 'Aztec',
      'Text': 'GroupDocs.Signature Cloud',
      'MatchType': 'Contains'
    }
  ]
}"

```

{{< /tab >}} {{< tab "Response" >}}

```javascript

{
  "FileInfo": {
    "FilePath": "string",
    "StorageName": "string",
    "VersionId": "string",
    "Password": "string"
  },
  "Size": 0,
  "IsSuccess": true
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

// Verify options
var options = new VerifyQRCodeOptions
{
    SignatureType = SignatureTypeEnum.QRCode,
    MatchType = VerifyTextOptions.MatchTypeEnum.Contains,
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
// Verify settings
var verifySettings = new VerifySettings
{
    FileInfo = new FileInfo
    {
        FilePath = "signedQRCode_one-page.docx"
    },
    Options = new List<VerifyOptions> { options }
};
// Create request
var request = new VerifySignaturesRequest(verifySettings);
// Call api method with request
var response = apiInstance.VerifySignatures(request);

```

{{< /tab >}} {{< tab "Java" >}}

```java

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-java-samples
String MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
String MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(MyClientId, MyClientSecret);
SignApi apiInstance = new SignApi(configuration);

FileInfo fileInfo = new FileInfo();
fileInfo.setFilePath("Signaturedocs\\signedQRCode_one-page.docx");

InfoSettings infoSettings = new InfoSettings();
infoSettings.setFileInfo(fileInfo);

VerifyQRCodeOptions options = new VerifyQRCodeOptions();
options.setSignatureType(SignatureTypeEnum.QRCODE);

options.setPage(1);
options.setAllPages(true);
PagesSetup pagesSetup = new PagesSetup();

pagesSetup.setEvenPages(false);
pagesSetup.setFirstPage(true);
pagesSetup.setLastPage(false);
pagesSetup.setOddPages(false);
pagesSetup.addPageNumbersItem(1);
options.setPagesSetup(pagesSetup);

options.setQrCodeType("Aztec");
options.setText("John Smith");
options.setMatchType(MatchTypeEnum.CONTAINS);

VerifySettings verifySettings = new VerifySettings();
verifySettings.setFileInfo(fileInfo);
verifySettings.addOptionsItem(options);

VerifySignaturesRequest request = new VerifySignaturesRequest(verifySettings);

VerifyResult  response = apiInstance.verifySignatures(request);

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
$fileInfo->setFilePath("signaturedocs\signedQRCodeOne_page.docx");
$fileInfo->setPassword("");

$settings = new GroupDocs\Signature\Model\VerifySettings();
$settings->setFileInfo($fileInfo);

$options = new GroupDocs\Signature\Model\VerifyQRCodeOptions();
$options->setPage(1);
$options->setAllPages(false);
$options->setSignatureType(GroupDocs\Signature\Model\OptionsBase::SIGNATURE_TYPE_QR_CODE);
$options->setQRCodeType("Aztec");
$options->setText("John Smith");

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

{{< /tab >}} {{< tab "Node.js" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-node-samples
global.signature_cloud = require("groupdocs-signature-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

global.signApi = signature_cloud.SignApi.fromKeys(clientId, clientSecret);

let fileInfo = new signature_cloud.FileInfo();
fileInfo.filePath = "signaturedocs/signedQRcodeOne_page.docx";

let opts = new signature_cloud.VerifyQRCodeOptions();
opts.signatureType = signature_cloud.OptionsBase.SignatureTypeEnum.QRCode;
opts.qRCodeType = 'Aztec';
opts.text = 'GroupDocs.Signature Cloud';
opts.matchType = signature_cloud.VerifyQRCodeOptions.MatchTypeEnum.Contains;
opts.allPages = true;

let settings = new signature_cloud.VerifySettings();
settings.fileInfo = fileInfo;
settings.options = [opts];

let request = new signature_cloud.VerifySignaturesRequest(settings);
let response = await signApi.verifySignatures(request);

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
fileInfo.file_path = "signaturedocs\\signedQRCodeOne_page.docx"

opts = VerifyQRCodeOptions()
opts.signature_type = 'QRCode'
opts.text = 'GroupDocs.Signature Cloud'
opts.qr_code_type = 'Aztec'
opts.match_type = 'Contains'

opts.page = 1

settings = VerifySettings()
settings.options = [opts]
settings.file_info = fileInfo

request = VerifySignaturesRequest(settings)
response = api.verify_signatures(request)

```

{{< /tab >}} {{< tab "Ruby" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-ruby-samples
require 'groupdocs_signature_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

api = GroupDocsSignatureCloud::SignApi.from_keys($client_id, $client_secret)

$info = GroupDocsSignatureCloud::FileInfo.new()
$info.file_path = "signaturedocs\\signedQRCodeOne_page.docx"

$opts = GroupDocsSignatureCloud::VerifyQRCodeOptions.new()
$opts.signature_type = "QRCode"
$opts.text = "John Smit"
$opts.qr_code_type = "Aztec"
$opts.page = 1

$settings = GroupDocsSignatureCloud::VerifySettings.new()
$settings.options = [$opts]
$settings.file_info = $info

$request = GroupDocsSignatureCloud::VerifySignaturesRequest.new($settings)

# Executing an API.
$response = api.verify_signatures($request)

```

{{< /tab >}} {{< /tabs >}}


---
id: "verify-digital-signatures"
url: "signature/verify-digital-signatures"
title: "Verify digital signatures"
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
    'FilePath': 'signaturedocs/signedDigital_sample2.pdf'
  },
  'Options': [
    {
      'AllPages': true,
      'SignatureType': 'Digital',
      'CertificateFilePath': 'signaturedocs/temp.pfx',
      'Password': '1234567890'
    }
  ]
}"

```

{{< /tab >}} {{< tab "Response" >}}

```javascript

{
  "fileInfo": {
    "filePath": "signaturedocs/signedDigital_sample2.pdf",
    "storageName": null,
    "versionId": null,
    "password": null
  },
  "size": 242705,
  "isSuccess": true
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
var options = new VerifyDigitalOptions
{
    SignatureType = SignatureTypeEnum.Digital,
    CertificateFilePath = "temp.pfx",
    Password = "1234567890",
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
        FilePath = "signedDigital_sample2.pdf"
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
fileInfo.setFilePath("Signaturedocs\\signedDigital_sample2.pdf");

InfoSettings infoSettings = new InfoSettings();
infoSettings.setFileInfo(fileInfo);

VerifyDigitalOptions options = new VerifyDigitalOptions();
options.setSignatureType(SignatureTypeEnum.DIGITAL);
options.setPage(1);
options.setAllPages(true);

PagesSetup pagesSetup = new PagesSetup();
pagesSetup.setEvenPages(false);
pagesSetup.setFirstPage(true);
pagesSetup.setLastPage(false);
pagesSetup.setOddPages(false);
pagesSetup.addPageNumbersItem(1);
options.setPagesSetup(pagesSetup);

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
$fileInfo->setFilePath("signaturedocs\signedDigitalOne_page.docx");
$fileInfo->setPassword("");

$settings = new GroupDocs\Signature\Model\VerifySettings();
$settings->setFileInfo($fileInfo);

$options = new GroupDocs\Signature\Model\VerifyDigitalOptions();
$options->setPage(1);
$options->setAllPages(false);
$options->setSignatureType(GroupDocs\Signature\Model\OptionsBase::SIGNATURE_TYPE_DIGITAL);

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
fileInfo.filePath = "signaturedocs/signedDigital_sample2.pdf";

let opts = new signature_cloud.VerifyDigitalOptions();
opts.signatureType = signature_cloud.OptionsBase.SignatureTypeEnum.Digital;

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
fileInfo.file_path = "signaturedocs\\signedDigitalOne_page.docx"

opts = VerifyDigitalOptions()
opts.signature_type = 'Digital'
opts.page = 1
opts.all_pages = True

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
$info.file_path = "signaturedocs\\signedDigitalOne_page.docx"

$opts = GroupDocsSignatureCloud::VerifyDigitalOptions.new()
$opts.signature_type = "Digital"

$settings = GroupDocsSignatureCloud::VerifySettings.new()
$settings.options = [$opts]
$settings.file_info = $info

$request = GroupDocsSignatureCloud::VerifySignaturesRequest.new($settings)

# Executing an API.
$response = api.verify_signatures($request)

```

{{< /tab >}} {{< /tabs >}}


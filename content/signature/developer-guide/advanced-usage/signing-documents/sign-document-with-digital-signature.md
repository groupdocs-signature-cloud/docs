---
id: "sign-document-with-digital-signature"
url: "signature/sign-document-with-digital-signature"
title: "Sign document with digital signature"
productName: "GroupDocs.Signature Cloud"
description: ""
keywords: ""
---

# Introduction #

A digital electronic signature is a scheme for verifying the document's authenticity. A valid digital signature gives a recipient very strong reason to believe that the document was created or updated by a known sender and that the document was not altered by unknown source. For documents, the digital signature is represented by certificate with private (to sign) and public (to verify) keys. Most often certificates of various public key cryptography standards are used for this purpose, for example PFX format (see specification [here](https://en.wikipedia.org/wiki/PKCS_12)). These digital signature certificates could be obtained from the operation system or generated manually with proper tools or trusted sources.

Digital signature as certificate file of PFX format allows to sign document after each creation or change with certificate and specify several optional parameters like subject, title, reason, contact etc. Most document viewers or editors support digital signatures verification that allows users to ensure document is from trusted source. Office documents format such as Word processing documents (DOC, DOCX, ODT, OTT), Spreadsheet files (XLSX, XLS, ODS, OTS) support digital signature without any visual appearance on document pages. PDF document format supports digital signature with alternative visual appearance on specific document page with custom image and labels. Picture below shows how digital signature looks by default on PDF document page..

![image](signature/images/image2020-2-10_18_40_38.png)

GroupDocs.Signature Cloud supports creation of digital signature based on existing PFX certificate. It allows to adjust digital signature properties in the document:

* Certificate source from FilePath;
* Certificate password;
* Contact, Reason and Location properties to set additional description;
* Visible property to specify whether signature should be visible on document page or not;
* XAdES type to specify whether e-signature should be of Xml Advanced Electronic Signature type.

## API Usage ##

There are steps that usage of GroupDocs.Signature Cloud consists of:

1. Upload input document into cloud storage and other files, like digital certificate or image stamp
1. Sign document
1. Download output document

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
curl -v "https://api.groupdocs.cloud/v2.0/signature/create" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"
-d "{
  'FileInfo': {
    'FilePath': 'signaturedocs/sample2.pdf'
  },
  'Options': [
    {
      'AllPages': true,
      'SignatureType': 'Digital',
      'ImageFilePath': 'signaturedocs/signature.jpg',
      'CertificateFilePath': 'signaturedocs/temp.pfx',
      'Password': '1234567890',
      'Left': 100,
      'Top': 100,
      'Width': 200,
      'Height': 200
    }
  ],
  'SaveOptions': {
    'OutputFilePath': 'signaturedocs/signedDigital_sample2.pdf'
  }
}"

```

{{< /tab >}} {{< tab tabNum="2" >}}

```javascript
{
  "fileInfo": {
    "filePath": "signaturedocs/signedDigital_sample2.pdf",
    "storageName": null,
    "versionId": null,
    "password": null
  },
  "size": 242705,
  "downloadUrl": "https://api-qa.groupdocs.cloud/v2.0/signature/storage/file/signaturedocs/signedDigital_sample2.pdf",
  "succeeded": [
    {
      "comments": "",
      "isValid": false,
      "signTime": "2020-07-21T10:10:24.8866737+00:00",
      "signatureType": "Digital",
      "pageNumber": 1,
      "signatureId": "62cde234-3004-4c00-882a-e51c231fd205",
      "isSignature": true,
      "createdOn": "2020-07-21T10:10:27.5765385+00:00",
      "modifiedOn": "2020-07-21T10:10:27.5765385+00:00",
      "top": 492,
      "left": 100,
      "width": 200,
      "height": 200
    },
    {
      "comments": "",
      "isValid": false,
      "signTime": "2020-07-21T10:10:27.7705402+00:00",
      "signatureType": "Digital",
      "pageNumber": 2,
      "signatureId": "41a0ac7b-10e6-4bde-93e8-337f0509db43",
      "isSignature": true,
      "createdOn": "2020-07-21T10:10:28.1215393+00:00",
      "modifiedOn": "2020-07-21T10:10:28.1215393+00:00",
      "top": 492,
      "left": 100,
      "width": 200,
      "height": 200
    }
  ],
  "failed": []
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
var apiInstance = new SignApi(configuration);
// Sign options
var options = new SignDigitalOptions
{
    SignatureType = SignatureTypeEnum.Digital,
    ImageFilePath = "signature.jpg",
    CertificateFilePath = "temp.pfx",
    Password = "1234567890",
    Left = 100,
    Top = 100,
    Width = 200,
    Height = 200,
    LocationMeasureType = SignImageOptions.LocationMeasureTypeEnum.Pixels,
    SizeMeasureType = SignImageOptions.SizeMeasureTypeEnum.Pixels,
    RotationAngle = 0,
    HorizontalAlignment = SignImageOptions.HorizontalAlignmentEnum.None,
    VerticalAlignment = SignImageOptions.VerticalAlignmentEnum.None,
    Margin = new Padding {All = 5},
    MarginMeasureType = SignImageOptions.MarginMeasureTypeEnum.Pixels,
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
// Sign settings.
var signSettings = new SignSettings
{
    FileInfo = new Sdk.Model.FileInfo
    {
        FilePath = "sample2.pdf"
    },
    SaveOptions = new SaveOptions { OutputFilePath = "signedDigital_sample2.pdf", SaveFormat = "pdf" },
    Options = new List<SignOptions> { options }
};
// Create request.
var request = new CreateSignaturesRequest(signSettings);
// Call api method with request.
var response = apiInstance.CreateSignatures(request);

```

{{< /tab >}} {{< tab tabNum="2" >}}

```java

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-java-samples
String MyClientSecret = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
String MyClientId = ""; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

Configuration configuration = new Configuration(MyClientId, MyClientSecret);
SignApi apiInstance = new SignApi(configuration);

FileInfo fileInfo = new FileInfo();
fileInfo.setFilePath("Signaturedocs\\sample2.pdf");
fileInfo.setPassword(null);
fileInfo.setVersionId(null);
fileInfo.setStorageName(Constants.MYStorage);

InfoSettings infoSettings = new InfoSettings();
infoSettings.setFileInfo(fileInfo);

SignDigitalOptions options = new SignDigitalOptions();
options.setSignatureType(SignatureTypeEnum.DIGITAL);

// set signature properties
options.setImageFilePath("Signaturedocs\\signature.jpg");
options.setCertificateFilePath("Signaturedocs\\temp.pfx");
options.setPassword("1234567890");

// set signature position on a page
options.setLeft(100);
options.setTop(100);
options.setWidth(200);
options.setHeight(200);
options.setLocationMeasureType(LocationMeasureTypeEnum.PIXELS);
options.setSizeMeasureType(SizeMeasureTypeEnum.PIXELS);
options.setRotationAngle(0);
options.setHorizontalAlignment(HorizontalAlignmentEnum.NONE);
options.setVerticalAlignment(VerticalAlignmentEnum.NONE);

Padding padding = new Padding();
padding.setAll(5);
options.setMargin(padding);
options.setMarginMeasureType(MarginMeasureTypeEnum.PIXELS);

*set pages for signing (each of these page settings could be used singly)
options.setPage(1);
options.setAllPages(true);

PagesSetup pagesSetup = new PagesSetup();
pagesSetup.setEvenPages(false);
pagesSetup.setFirstPage(true);
pagesSetup.setLastPage(false);
pagesSetup.setOddPages(false);
pagesSetup.addPageNumbersItem(1);
options.setPagesSetup(pagesSetup);

SaveOptions saveOptions = new SaveOptions();
saveOptions.setOutputFilePath("Signaturedocs\\signedDigital_sample2.pdf");

SignSettings signSettings = new SignSettings();
signSettings.setFileInfo(fileInfo);
signSettings.addOptionsItem(options);
signSettings.setSaveOptions(saveOptions);

CreateSignaturesRequest request = new CreateSignaturesRequest(signSettings);

SignResult response = apiInstance.createSignatures(request);

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
$fileInfo->setFilePath("signaturedocs\one-page.docx");
$fileInfo->setPassword("");

$settings = new GroupDocs\Signature\Model\SignSettings();
$settings->setFileInfo($fileInfo);

$saveOptions = new GroupDocs\Signature\Model\SaveOptions();
$saveOptions->setOutputFilePath("signaturedocs\signedDigitalOne_page.docx");
$settings->setSaveOptions($saveOptions);

$options = new GroupDocs\Signature\Model\SignDigitalOptions();
$options->setPage(1);
$options->setAllPages(false);
$options->setSignatureType(GroupDocs\Signature\Model\OptionsBase::SIGNATURE_TYPE_DIGITAL);
$options->setImageFilePath("signaturedocs\\signature.jpg");
$options->setCertificateFilePath("signaturedocs\\temp.pfx");
$options->setPassword("1234567890");
$options->setLeft(100);
$options->setTop(100);
$options->setWidth(300);
$options->setHeight(100);
$options->setLocationMeasureType(GroupDocs\Signature\Model\SignTextOptions::LOCATION_MEASURE_TYPE_PIXELS);
$options->setSizeMeasureType(GroupDocs\Signature\Model\SignTextOptions::SIZE_MEASURE_TYPE_PIXELS);
$options->setRotationAngle(0);
$options->setHorizontalAlignment(GroupDocs\Signature\Model\SignTextOptions::HORIZONTAL_ALIGNMENT_NONE);
$options->setVerticalAlignment(GroupDocs\Signature\Model\SignTextOptions::VERTICAL_ALIGNMENT_NONE);

$padding = new GroupDocs\Signature\Model\Padding();
$padding->setAll(5);
$options->setMargin($padding);
$options->setMarginMeasureType(GroupDocs\Signature\Model\SignTextOptions::MARGIN_MEASURE_TYPE_PIXELS);

$pagesSetup = new GroupDocs\Signature\Model\PagesSetup();
$pagesSetup->setEvenPages(false);
$pagesSetup->setFirstPage(true);
$pagesSetup->setLastPage(false);
$pagesSetup->setOddPages(false);
$pagesSetup->setPageNumbers([1]);
$options->setPagesSetup($pagesSetup);

$settings->setOptions([$options]);

$request = new GroupDocs\Signature\Model\Requests\createSignaturesRequest($settings);
$response = $apiInstance->createSignatures($request);

```

{{< /tab >}} {{< tab tabNum="4" >}}

```javascript

// For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-node-samples
global.signature_cloud = require("groupdocs-signature-cloud");

global.clientId = "XXXX-XXXX-XXXX-XXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
global.clientSecret = "XXXXXXXXXXXXXXXX"; // Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

global.signApi = signature_cloud.SignApi.fromKeys(clientId, clientSecret);

let fileInfo = new signature_cloud.FileInfo();
fileInfo.filePath = "signaturedocs/sample2.pdf";

let opts = new signature_cloud.SignDigitalOptions();
opts.signatureType = signature_cloud.OptionsBase.SignatureTypeEnum.Digital;
opts.imageFilePath = "signaturedocs/signature.jpg";
opts.certificateFilePath = "signaturedocs/temp.pfx";
opts.password = "1234567890";

let settings = new signature_cloud.SignSettings();
settings.fileInfo = fileInfo;
settings.options = [opts];

settings.saveOptions = new signature_cloud.SaveOptions();
settings.saveOptions.outputFilePath = "signaturedocs/signedDigital_sample2.pdf";

let request = new signature_cloud.CreateSignaturesRequest(settings);
let response = await signApi.createSignatures(request);

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
fileInfo.file_path = "signaturedocs\\one-page.docx"

opts = SignDigitalOptions()
opts.signature_type = 'Digital'
opts.image_file_path = "signaturedocs\\signature.jpg"
opts.certificate_file_path = "signaturedocs\\temp.pfx"
opts.password = '1234567890'

# set signature position on a page
opts.left = 100
opts.top = 100
opts.width = 200
opts.height = 100
opts.location_measure_type = "Pixels"
opts.size_measure_type = "Pixels"
opts.rotation_angle = 0
opts.horizontal_alignment = "None"
opts.vertical_alignment = "None"
opts.margin = Padding()
opts.margin.all = 5
opts.margin_measure_type = "Pixels"

opts.page = 1

settings = SignSettings()
settings.options = [opts]
settings.save_options = SaveOptions()
settings.save_options.output_file_path = "signaturedocs\\signedDigitalOne_page.docx"
settings.file_info = fileInfo

request = CreateSignaturesRequest(settings)
response = api.create_signatures(request)

```

{{< /tab >}} {{< tab tabNum="6" >}}

```ruby

# For complete examples and data files, please go to https://github.com/groupdocs-signature-cloud/groupdocs-signature-cloud-ruby-samples
require 'groupdocs_signature_cloud'

$client_id = "XXXX-XXXX-XXXX-XXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud
$client_secret = "XXXXXXXXXXXXXXXX" # Get ClientId and ClientSecret from https://dashboard.groupdocs.cloud

api = GroupDocsSignatureCloud::SignApi.from_keys($client_id, $client_secret)

$info = GroupDocsSignatureCloud::FileInfo.new()
$info.file_path = "signaturedocs\\one-page.docx"

$opts = GroupDocsSignatureCloud::SignDigitalOptions.new()
$opts.signature_type = 'Digital'
$opts.image_file_path = "signaturedocs\\signature.jpg"
$opts.certificate_file_path = "signaturedocs\\temp.pfx"
$opts.password = '1234567890'

$settings = GroupDocsSignatureCloud::SignSettings.new()
$settings.options = [$opts]

$settings.save_options = GroupDocsSignatureCloud::SaveOptions.new()
$settings.save_options.output_file_path = "signaturedocs\\signedDigitalOne_page.docx"
$settings.file_info = $info

$request = GroupDocsSignatureCloud::CreateSignaturesRequest.new($settings)

# Executing an API.
$response = api.create_signatures($request)

```

{{< /tab >}} {{< /tabs >}}
